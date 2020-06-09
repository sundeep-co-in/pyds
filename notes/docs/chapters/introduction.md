# CH 1: Introduction

---

## Notes
<div style="padding: 1%;background-color: #f2fafc;margin-bottom: 1%"></div>

*find the complexity of any given algorithm*

#### 1.1 Variables

Variables are names (x and y) of the placeholders for representing data.

#### 1.2 Data Types

A set of data with predefined values, example: integer, floating point, unit number, character, string, etc. In memory we combine 2 bytes (16 bits) and call it an integer. Similarly, 4 bytes (32 bits) for float.

* System defined data types (Primitive data types) `int`, `float`, `char`, `double`, `bool`, etc.
* User defined data types `structures`, `union`, `classes`

#### 1.3 Data Structures

A special format for organizing and storing data so that it can be used efficiently. Example `arrays`, `files`, `linked list`, `stacks`, `queues`, `trees`, `graphs` and so on.

* Linear data structure: Linked List, Stacks and Queues.
* Non-linear data structure: Trees and Graphs.

#### 1.4 Abstract Data Types (ADTs)

When we combine the data structures with their operations.
An ADT has two parts:

  * Declaration of data
  * Declaration of operations.
 
Few examples are `Linked Lists`, `Stacks`, `Queues`, `Priority Queues`, `Binary Trees`, `Dictionaries`, `Disjoint Sets (Union and Find)`, `Hash Tables`, `Graphs` and many others.

#### 1.5 What is an Algorithm?
#### 1.6 Why the Analysis of Algorithms?

The step-by-step unambiguous instructions to solve a given problem. Criteria:

* Correctness (*Does the algorithm give solution to the problem in a finite number of steps?*)
* Efficiency (*How much resources - memory and time - does it take to execute?*)

Helps us to determine which algorithm is most efficient in terms of time and space consumed.

#### 1.8 What is Running Time Analysis?

The process of determining how processing time increases as the size of the problem (input size) increases. Common types:

* Size of an array
* Polynomial degree
* Number of elements in a matrix
* Number of bits in the binary representation of the input
* Vertices and edges in a graph

#### 1.9 How to compare Algorithms

Let us assume that we express the running time of a given algorithm as a function of the input size **n** (i.e. <code>f(n)</code>) and compare these different functions corresponding to running times. This kind of comparison is independent of machine time, programming style, etc.

#### 1.10 What is rate of growth?

The rate at which the running time increases as a function of input is called *rate of growth*. 
<br/><code>n<sup>4</sup> + 2n<sup>2</sup> + 100n + 500 ~ n<sup>4</sup></code>

#### 1.11 Commonly Used Rates of Growth

Time Complexity | Name | Example
--- | --- | ---
1 | Constant | Adding an element to the front of the linked list
log n | Logarithmic | Finding an element in a sorted array
n | Linear | Finding an element in a unsorted array
n log n | Linear Logarithmic | Sorting n items by divide-n-conquer `MergeSort`
n<sup>2</sup> | Quadratic | Shortest path between two nodes in a graph
n<sup>3</sup> | Cubic | Matrix Multiplication
2<sup>n</sup> | Exponential | The Towers of Hanoi problem

#### 1.12 Types of Analysis

Algorithm can be represented with multiple expressions: one for the case where it takes less time (*best case*) and another for the case where it takes more time (*worst case*).

* **Worst case**: Defines the input for which the algorithm takes a long time (slowest time to complete).<br/><code>f(n) = n<sup>2</sup> + 500</code>
* **Best case**: Defines the input for which the algorithm takes the least time (fastest time to complete).<br/><code>f(n) = n + 100n + 500</code>
* **Average case**: Run the algorithm many times, using many different inputs that come from some distribution that generates these inputs, compute the total running time (by adding the individual times), and divide by the number of trails. `Lower Bound <= Average Time <= Upper Bound`

#### 1.13 Big-O Notation

Represented as `f(n) = O(g(n))`, where `g(n)` gives the maximum rate of growth for `f(n)` at larger values of n. n<sub>0</sub>, called as **threshold**, is the point from which we need to consider the rate of growth for a given algorithm. Defined as  <code>O(g(n)) = {f(n): positive constants c and n<sub>0</sub> such that 0 <= f(n) <= cg(n) for all n >= n<sub>0</sub>}</code>

#### 1.15 Omega-Ω Notation

This notation gives the tighter lower bound of the given algorithm and we represent it as `f(n) = Ω(g(n))`. That means, at larger values of n, the tighter lower bound of `f(n)` is `g(n)`. 2n = Ω(n), n<sup>3</sup> = Ω(n<sup>3</sup>), logn = Ω(logn) as <code>Ω(g(n)) = {f(n): positive constants c and n<sub>0</sub> such that 0 <= cg(n) <= f(n) for all n >= n<sub>0</sub>}</code>

#### 1.16 Theta-Θ Notation

This notation decides whether the upper and lower bounds of a given function (*algorithm*) are the same. If the upper bound (O) and the lower bound (Ω) give the same result, then the Θ notation will also have the same rate of growth. Defined as <code>Θ(g(n)) = {f(n): there exist positive constants c<sub>1</sub>, c<sub>2</sub> and n<sub>0</sub> such that 0 <= c<sub>1</sub>g(n) <= f(n) <= c<sub>2</sub>g(n) for all n >= n<sub>0</sub>}</code>

For analysis (*best*, *worst* and *average*) case, we try to give the upper bound (O) and lower bound (Ω) and average running time (Θ). We generally focus on upper bound (O). g(n) is the asymptotic curve for f(n).

#### 1.18 Guidelines for Asymptotic Analysis

* **Loops**: The running time of a loop is the running time of the statements inside the loop (*including tests*) multiplied by the number of iterations.
`Total time = a constant c x n = cn = O(n)`
* **Nested Loops**: Total running time is the product of the sizes of all the loops.<br/><code>Total time = c x n x n = cn<sup>2</sup> = O(n<sup>2</sup>)</code>
* **Consecutive statements**: Add the time complexities of each statement.<br/><code>Total time = c<sub>0</sub> + c<sub>1</sub>n + c<sub>2</sub>n<sup>2</sup> = O(n<sup>2</sup>)</code>
* **If-then-else statements**: Worst-case running time: the test, plus either the *then* part *or* the else part.<br/><code>Total time = c<sub>0</sub> + c<sub>1</sub> * n = O(n)</code>
* **Logarithmic complexity**: An algorithm is `O(logn)` if it takes a constant time to cut the problem size by a fraction (usually by <sup>1</sup>/<sub>2</sub>). <code>Total time = log(2<sup>k</sup>) = klog2 = O(logn)</code> An example: binary search (*finding a word in a dictionary of n pages*) (**1**) Look at the center point in the dictionary (**2**) Is the word towards the left or right of the center? (**3**) Repeat the process with the left or right part of the dictionary until the word is found.

#### 1.21 Master Theorem for Divide and Conquer Recurrences

Divide and conquer algorithms divide the problem into sub-problems, each of which is a part of the original problem, and then perform some additional work to compute the final answer. Example: for a merge sort algorithm, running time equation could be <code>T(n) = 2T(<sup>n</sup>/<sub>2</sub>) + O(n)</code>

#### 1.26 Amortized Analysis

Amortized analysis is a worst-case analysis, but for a sequence of operations rather than for individual operations. It generally applies to a method that consists of a sequence of operations, where the vast majority of the operations are cheap, but some of the operations are expensive.

When one event in a sequence affects the cost of later events:

* One particular task may be expensive.
* But it may leave data structure in a state that the next few operations become easier.

**Example**: Let us consider an array of elements from which we want to find the k<sup>th</sup> smallest element. We can solve this problem using sorting. After sorting the given array, we just need to return the k<sup>th</sup> element from it. The cost of performing the sort (*assuming comparison based sorting algorithm*) is `O(nlogn)`. If we perform *n* such selections then the average cost of each selection is `O(nlogn/n) = O(logn)`. This clearly indicates that sorting once is reducing the complexity of subsequent operations. Hence, while the recurrence relation looks exponential, the solution to the recurrence relation here gives a different result.

---
## Examples
<div style="padding: 1%;background-color: #f2fafc;margin-bottom: 1%"></div>

#### Functions by decreasing order of growth.

Function | Rate of Growth
-------- | --------------
(n + 1)! | O(n!)
n!       | O(n!)
4<sup>n</sup> | O(4<sup>n</sup>)
n * 3<sup>n</sup> | O(n3<sup>n</sup>)
3<sup>n</sup> + n<sup>2</sup> + 20n | O(3<sup>n</sup>)
(<sup>3</sup>/<sub>2</sub>)<sup>n</sup> | O((<sup>3</sup>/<sub>2</sub>)<sup>n</sup>)
4n<sup>2</sup> | O(n<sup>2</sup>)
4<sup>lgn</sup> | O(n<sup>2</sup>)
n<sup>2</sup> + 200 | O(n<sup>2</sup>)
20n + 500 | O(n)
2<sup>lgn</sup> | O(n)
n<sup>2/3</sup> | O(n<sup>2/3</sup>)
1 | O(1)

---
## Problems
<div style="padding: 1%;background-color: #f2fafc;margin-bottom: 1%"></div>

#### Problem-28: Write a recursive function for the running time T(n) of the function given below.

```python

def function(n):
    count = 0
    if n <= 0:
        return
    for i in range(0, n):           # Outer loop executes n times
        for j in range(0, n):       # Inner loop executes n times
            count = count + 1
    function(n-3)                   # Recursive call
    print(count)

function(20)

```

The recursive for this call is <code>T(n) = T(n-3) + cn<sup>2</sup></code> for some constant c > 0. Using Substraction and Conquer master theorem, we get <code>T(n) = Θ(n<sup>3</sup>)</code>

#### Problem-34: Consider the following program.

```python

def Fib(n):
    if n == 0: return 0
    elif n == 1: return 1
    else: return Fib(n-1) + Fib(n-2)

print(Fib(3))

```

The recurrence relation for the running time of this program is: `T(n) = T(n-1) + T(n-2) + c`. Note T(n) has two recurrence calls indicating a binary tree. Each step recursively calls the program for n reduced by 1 and 2, so the depth of the recurrence tree is O(n). The number of leaves at depth n is 2<sup>n</sup> since this is a full binary tree, and each leaf takes at least O(1) computations for the constant factor. Running time is clearly exponential in n and it is O(2<sup>n</sup>).

#### Problem-38: What is the running time of the following recursive function?

```python

def function(n):
    if n <= 0:
        return 0
    for i in range(0, 3):
        function(n-1)

function(20)

```

<code>T(n) = c + 3T(n-1), if n > 1 = Θ(3<sup>n</sup>)</code>

#### Problem-49: Find the complexity of the below function.

```python

count = 0

def logarithms(n):
    i = 1
    global count
    while i <= n:
        j = n
        while j > 0:
            j = j // 2              # this loop executes logn times
            count = count + 1
            i = i * 2               # this loop executes logn times
    return count

print(logarithms(10))

```

<code>T(n) = O(logn * logn) = O(log<sup>2</sup>n)</code>