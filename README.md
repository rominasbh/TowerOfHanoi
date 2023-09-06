# TowerOfHanoi

Problem: 
Solve the tower of hanoi game for the graph G=(V,E) with V={Start, A1,A2,A3,Dest} and E={(Start,Dest), (Dest, A1), (A1,Dest), (A1,A2), (A2,A1), (A2,A3), (A3,A2)}. (a) Design an algorithm and determine the time and space complexities of moving n disks from start to dest. (b) implement this algorithm whereby your program prints out each of the moves of very disk. show the output for n=1,2,3,4,5,6,7,8,9 and 10. (if the output is too long, print out only the first 100 and the last 100 moves.)
--------------------------------
The graph represents a modified Tower of Hanoi problem. Normally, the Tower of Hanoi problem has three pegs (i.e., vertices) and the problem requires moving all the disks from the start peg to the destination peg using the intermediary peg. However, the graph you've described has 5 vertices (pegs): Start, A1, A2, A3, and Dest. This means you're working with a generalized version of the problem.

Based on the edges (transitions) , we can make some observations:

You can move directly from Start to Dest.
From Dest, you can move to A1, but from A1, you can also move directly back to Dest. This allows A1 to serve as an auxiliary space similar to the classical Tower of Hanoi.
A1 and A2 have bi-directional transitions.
A2 and A3 also have bi-directional transitions.

-------------------------------

Algorithm :
Let's construct an algorithm to move n disks from Start to Dest using the graph.

If n = 1, move the disk directly from Start to Dest and return.
To move n disks from Start to Dest:
Move n-1 disks from Start to A1 (using Dest, A2, and A3 as auxiliary).
Move the n-th disk directly from Start to Dest.
Move the n-1 disks from A1 to Dest (using Start, A2, and A3 as auxiliary).
For the recursive calls, we'd need to adapt the algorithm to fit the source and destination pegs as per the situation.

--------------------------------
Time Complexity:
For the classical Tower of Hanoi, the time complexity is O(2^n - 1). Given the structure of your graph, the complexity might be similar but we need to analyze it. Each time you need to move n disks, you need to first move n-1 disks twice (once to the auxiliary peg and once back). Hence, the recurrence relation might look like:
T(n) = 2T(n-1) + 1

However, this is the same recurrence relation as the classical Tower of Hanoi. Hence, the time complexity remains O(2^n - 1).

---------------------------------
Space Complexity:
The space complexity is related to the depth of the recursion. In this case, it is O(n) since we make recursive calls n times.

---------------------------------
Implementation:
in code section

This code will print the moves for n from 1 to 10. If the number of moves exceeds 200, it'll only print the first 100 and last 100 moves.
