# Structify-Assignment
Repo for Git submission of Structify Interview question- Coding round


# Chord Intersection Counter

This program counts the number of intersections between chords in a circle given a list of radian measures for chord endpoints and their corresponding identifiers.

## Algorithm

The algorithm works as follows:

1. **Input**: We parse the input lists of radian measures and identifiers, pairing each starting point (`s_x`) with its corresponding ending point (`e_x`) into a dictionary called `chords`. The keys are unique identifiers for each chord, and the values are lists containing the start and end radian values.

2. **Sort Chords**: We sort the chords by their starting radian measures to prepare for a sweep-line algorithm. This is important because the order of start points affects the counting of intersections.

3. **Count Intersections**:
   - We use a sweep-line technique, conceptually sweeping a line around the circle from the smallest to the largest radian value.
   - We maintain a list of active chords that have started but not yet ended as the sweep-line moves.
   - For each new chord we encounter, we count how many active chords it intersects with. This is based on the principle that if a chord starts while another chord is active, they intersect.
   - We then add the new chord to the list of active chords.
   - Chords are removed from the active list once we pass their end point in the sweep.

4. **Return Count**: After the sweep is complete, we return the total count of intersections.

## Big O Runtime Estimation

The algorithm's time complexity is O(N log N), where N is the number of chords. This estimation is due to the following:

- Sorting the chords by their starting points has a complexity of O(N log N), which is the most time-consuming part of the algorithm.
- Iterating through the sorted chords to count intersections involves operations that, in aggregate, contribute to a linear O(N) complexity.
- Since sorting is the most significant operation, it dictates the overall time complexity of the algorithm.

## How to Run

To run the script, you can run the ipynb or py code. The function is designed to operate with two arguments- 'radiants' and 'identifiers'. 
You can create a new line of code to initialise these two arguments and use it for the function call. The function returns the number of intersections. 

## Note
The example 2 given in the assignment contains the naming of "s1", "s2", "e1" and "e2", however i have stuck to the nomenclature given in the problem description of "s_1", "s_2", "se_1" and "e_2" to parse the key and index. If i were to parse two different types of inputs, i was to take a different - more generalized way to extract the key and index. I stuck to the nomenclature given in the problem statement.

