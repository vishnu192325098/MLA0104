1) Breadth First Search (BFS)
 BFS(Graph, Start)
    Create empty set Visited
    Create Queue Q

    Add Start to Visited
    Enqueue Start into Q

    While Q is not empty
        Node ← Dequeue(Q)
        Print Node

        For each Neighbor of Node
            If Neighbor not in Visited
                Add Neighbor to Visited
                Enqueue Neighbor into Q


2)Depth First Search (DFS)
DFS(Graph, Node, Visited)
    Add Node to Visited
    Print Node

    For each Neighbor of Node
        If Neighbor not in Visited
            DFS(Graph, Neighbor, Visited)

3. Uniform Cost Search (UCS)
UCS(Graph, Start, Goal)
    Create Priority Queue PQ
    Insert (0, Start) into PQ

    While PQ is not empty
        (Cost, Node) ← Remove minimum cost node

        If Node = Goal
            Return Cost

        For each Neighbor of Node
            NewCost ← Cost + EdgeCost(Node, Neighbor)
            Insert (NewCost, Neighbor) into PQ

4. Greedy Best First Search (GBFS)
GBFS(Graph, Start, Goal, Heuristic)
    Create Priority Queue PQ
    Insert Start with Heuristic(Start)

    While PQ is not empty
        Node ← Remove node with minimum heuristic value

        If Node = Goal
            Return Success

        Mark Node as Visited

        For each Neighbor of Node
            If Neighbor not Visited
                Insert Neighbor with Heuristic(Neighbor)

5. A* Search Algorithm
A_Star(Graph, Start, Goal, Heuristic)
    Create Priority Queue OPEN
    Add Start to OPEN

    g(Start) ← 0
    f(Start) ← g(Start) + Heuristic(Start)

    While OPEN is not empty
        Current ← Node with lowest f value

        If Current = Goal
            Return Path

        For each Neighbor of Current
            Tentative_g ← g(Current) + Cost(Current, Neighbor)

            If Tentative_g < g(Neighbor)
                Parent(Neighbor) ← Current
                g(Neighbor) ← Tentative_g
                f(Neighbor) ← g(Neighbor) + Heuristic(Neighbor)

                Add Neighbor to OPEN


6. Minimax Algorithm
MINIMAX(Node, Depth, MaximizingPlayer)

    If Depth = 0 OR Node is Terminal
        Return Evaluation(Node)

    If MaximizingPlayer
        Best ← -∞

        For each Child of Node
            Value ← MINIMAX(Child, Depth-1, False)
            Best ← max(Best, Value)

        Return Best

    Else
        Best ← +∞

        For each Child of Node
            Value ← MINIMAX(Child, Depth-1, True)
            Best ← min(Best, Value)

        Return Best

7. Alpha-Beta Pruning
ALPHA_BETA(Node, Depth, Alpha, Beta, MaximizingPlayer)

    If Depth = 0 OR Node is Terminal
        Return Evaluation(Node)

    If MaximizingPlayer
        Value ← -∞

        For each Child of Node
            Value ← max(Value,
                        ALPHA_BETA(Child, Depth-1,
                                   Alpha, Beta, False))

            Alpha ← max(Alpha, Value)

            If Alpha ≥ Beta
                Break

        Return Value

8. Forward Chaining
FORWARD_CHAINING(Facts, Rules)

    Repeat
        NewFactAdded ← False

        For each Rule
            If all Conditions are true
               AND Conclusion not already known

                Add Conclusion to Facts
                NewFactAdded ← True

    Until NewFactAdded = False

    Return Facts


9. Backward Chaining
BACKWARD_CHAINING(Goal)

    If Goal is a known Fact
        Return True

    If no Rule produces Goal
        Return False

    For each Rule that concludes Goal
        If all Premises are true
            using BACKWARD_CHAINING
            Return True

    Return False

10. Propositional Logic
INPUT P, Q

AND_Result ← P AND Q
OR_Result ← P OR Q
NOT_P ← NOT P
Implication ← (NOT P) OR Q
Biconditional ← (P = Q)

Display all results

11. Hill Climbing Algorithm
HILL_CLIMBING(Start)

    Current ← Start

    Repeat
        Neighbor ← Best Neighbor of Current

        If Value(Neighbor) ≤ Value(Current)
            Return Current

        Current ← Neighbor

12. Water Jug Problem
WATER_JUG(Jug1, Jug2, Goal)

    Start with (0,0)

    While Goal not reached
        Fill Jug1
        Fill Jug2
        Empty Jug1
        Empty Jug2
        Pour Jug1 → Jug2
        Pour Jug2 → Jug1

        Mark visited states

    Return Solution Path

13. 8-Puzzle Problem
EIGHT_PUZZLE(Start, Goal)

    OPEN ← Start State
    CLOSED ← Empty

    While OPEN not empty
        Current ← Remove Best State

        If Current = Goal
            Return Solution

        Generate all possible moves

        Add new states to OPEN
        Add Current to CLOSED

14. Missionaries and Cannibals Problem
MISSIONARIES_CANNIBALS(Start, Goal)

    OPEN ← Start State

    While OPEN not empty
        Current ← Remove State

        If Current = Goal
            Return Solution

        Generate Valid Successor States

        Add Successors to OPEN

15. Tic-Tac-Toe Using Minimax
TIC_TAC_TOE(Board)

    While Game not Over
        If AI Turn
            BestMove ← MINIMAX(Board)
            Make Move

        Else
            User Makes Move

    Display Winner

16. Cryptarithmetic Problem
CRYPTARITHMETIC(Equation)

    Assign digits to letters

    While assignment exists
        Check Constraints

        If Equation satisfied
            Return Solution

        Try next assignment

17. N-Queens Problem
N_QUEENS(Board, Row)

    If Row = N
        Print Solution
        Return

    For each Column
        If Position Safe
            Place Queen

            N_QUEENS(Board, Row+1)

            Remove Queen

18. AO* Algorithm
AO_STAR(Start)

    Mark Start as Unsolved

    Repeat
        Select Best Partial Path

        Expand Node

        Compute Cost

        Mark Solved Nodes

    Until Start is Solved

    Return Solution Graph

19. Expert System
EXPERT_SYSTEM()

    Input User Query

    Match Query with Knowledge Base

    Apply Rules

    Display Conclusion

20. Decision Tree Learning
DECISION_TREE(Data)

    If all examples belong to same class
        Return Leaf Node

    Select Best Attribute

    Split Data

    For each subset
        Build Subtree recursively

    Return Tree
