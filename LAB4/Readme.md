MA3206: Artificial Intelligence - Assignment 4
Task 1 & Task 2: Graph Scheduling Algorithms (Greedy vs. A* Search)
================================================================================


Description
-----------
This project implements scheduling algorithms to solve a complex assignment 
dependency problem modeled as a Directed Acyclic Graph (DAG). It features two 
primary components:
1. Task 1: Four distinct Greedy heuristics (Cost, Depth, Frequency, Topological) 
   that attempt to optimize daily schedules locally.
2. Task 2: An optimal A* Search algorithm utilizing a custom reverse-reachability 
   heuristic to guarantee the lowest possible total food cost globally.

Dependencies
------------
- Python 3.x
- matplotlib (for generating analytical comparison plots)
- numpy

Installation: `pip install matplotlib numpy`

How to Run
----------
Execute the Python scripts provided for Task 1 and Task 2. Both scripts are 
hardcoded with 6 distinct network topologies (Test Cases) designed to stress-test 
the algorithms against distractor paths, bottlenecks, and parallel widths.

A* Search Architecture (Task 2)
-------------------------------
To guarantee an optimal schedule, the A* algorithm is defined as follows:
- State (n): A frozenset of successfully completed assignments.
- g(n): The exact, cumulative food cost incurred from Day 1 to the current state.
- h(n): An admissible heuristic calculated by performing a Reverse BFS from the 
  target outputs. It sums the minimum required food costs for only the 
  "strictly necessary" remaining tasks, effectively pruning useless distractor 
  nodes from the search tree.

