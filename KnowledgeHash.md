Table of Contents
=================
 
   * [Heap](#heap)
   * [Stack](#stack)
      * [Functions](#functions)
      * [基本用法](#基本用法)
      * [Monotonous Stack](#monotonous-stack)
      * [Expample](#expample)
   * [Queue](#queue)
   * [Linked List](#linked-list)
   * [Tree](#tree)
      * [Binary Search Tree](#binary-search-tree)
         * [TreeSet](#treeset)
      * [Binary Tree](#binary-tree)
      * [Binary Indexed Tree](#binary-indexed-tree)
      * [Segment Tree](#segment-tree)
   * [Union Find](#union-find)
      * [UnionFind基础操作](#unionfind基础操作)
      * [UnionFind follow up](#unionfind-follow-up)
   * [Trie](#trie)
      * [applications](#applications)
      * [why not using a hashmap to store string](#why-not-using-a-hashmap-to-store-string)
      * [Model](#model)
      * [sample peoblems](#sample-peoblems)
      * [考点](#考点)
   * [Deque](#deque)
   * [Graph](#graph)
   * [Topological Sort](#topological-sort)
      * [Topological Sort - BFS](#topological-sort---bfs)
      * [Topological Sort - DFS](#topological-sort---dfs)
   * [Array](#array)
      * [Array](#array-1)
   * [Two Pointers](#two-pointers)
   * [Binary Search](#binary-search)
      * [Basics](#basics)
      * [二分思想](#二分思想)
   * [Sort](#sort)
      * [Quick Sort](#quick-sort)
   * [Collections](#collections)
      * [methods](#methods)
      * [ArrayList](#arraylist)
   * [Hash](#hash)
   * [Map](#map)
   * [Hash Table](#hash-table)
      * [HashSet](#hashset)
   * [Basics](#basics-1)
      * [Math](#math)
      * [String](#string)
      * [Bit Manipulation](#bit-manipulation)
   * [DP](#dp)
      * [Technique](#technique)
      * [分类](#分类)
      * [Sequence DP](#sequence-dp)
      * [记忆化搜索 Memoization](#记忆化搜索-memoization)
      * [Minimax](#minimax)
      * [Optimization problems](#optimization-problems)
      * [Double Sequence](#double-sequence)
      * [存状态](#存状态)
   * [Search](#search)
      * [Breadth-first Search](#breadth-first-search)
      * [Depth-first Search](#depth-first-search)
   * [Backtracking](#backtracking)
   * [Reservoir Sampling](#reservoir-sampling)
   * [Geometry](#geometry)
   * [Brainteaser](#brainteaser)
   * [Red Black Tree](#red-black-tree)
   * [Approach](#approach)
      * [Greedy](#greedy)
      * [Divide and Conquer](#divide-and-conquer)
      * [Recursion](#recursion)
   * [Design](#design)
   * [Data Structure](#data-structure)
   * [Problem Sets](#problem-sets)
      * [Two Pointer](#two-pointer)
      * [Min/Max Heap](#minmax-heap)
      * [Stack](#stack-1)
      * [Windows Problem](#windows-problem)
      * [Sweep Line](#sweep-line)

# Heap

# Stack

## Functions
- peek(), pop(), push()
- Stack<XXX> stack = new Stack<>();

## 基本用法
- 用来暂且保存有效信息
- 翻转stack
- stack优化DFS, 变成非递归

## Monotonous Stack
- 找每个元素左边或者右边 第一个比它自身小/大的元素
- 用单调栈来维护
- 维护monotonous stack 是题目需要, 而不是stack本身性质. 比如, 题目需要stack.peek() O(1), 加上需要单调递增/递减的性质, 就用起来了stack.

## Expample
MaxTree, Largest Rectangle In Histogram, Maximal Rectangle (in 2D array)


# Queue
- Functions: peek(), poll(), add()/offer(), remove(object)
- queue = new LinkedList<...>()
- PriorityQueue: new Comparator 很重要
- 看到Min/Max就要想到heap. 如果给出的数组没有排序, 先排序, 然后用heap. PrioirtyQueue是用Binary Heap做出来的
- 看到median 想到heap

# Linked List
- No concept of size(), it's all pointers: node.next.next
- how to set head/dummy, and return dummy.next as result.
- iterate over linked list
- Don't get mixed up with Java LinkedList. Here we are talking about linked list concept, not the Java data structure LinkedList

# Tree

## Binary Search Tree
- If BST not given, can use TreeSet
- All left nodes are less than current node.val; all right nodes are greater than curr node.val
- Use DFS to traverse: divide and conquer. Similarly, usually can convert the DFS solution to interative solution.
- Use stack to traverse iteratively

### TreeSet
- 如果BST treenode没给, 可以用TreeSet
- TreeSet还是一个set, 存values, 而好处是可以用 treeSet.ceiling(x)找到 最小的大于x的值
- 其实就是这个value/node的parent

## Binary Tree
- Complete binary tree: all levels are filled, except maybe the last level. 最后一个level可能是缺node的(不是说最右下角缺node, 别忘了!)
- Balenced bianry tree: has the minimum posible maximum height(depth) for left nodes; for given leaf nodes, the leaf nodes will be placed at greatest height possible.
- 一个child tree的nodes总量是 2 ^ h - 1; 那么一个child tree + root 的nodes 总量就是 2 ^ h了.

## Binary Indexed Tree

## Segment Tree

# Union Find
- 集合合并，查找元素在集合里面
- Find and Union functions
- Time Complexity: log(n)
- 在UnionFind function里维护不同的状态, expose with public helper functions

## UnionFind基础操作
- 查询两个元素是否在同一个集合内
- 合并两个元素所在的集合

## UnionFind follow up
- 查询某个元素所在集合的元素个数
- 查询当前集合的个数


# Trie
- 一个字母一个字母查找，快速判断前缀

## applications
- Autocomplete
- Spell check
- IP routing
- T9 text prediction (old NOKIA phone)
- solve world game

## why not using a hashmap to store string
- Trie can help find all strings with prefix
- Trie can enumerate a data set of strings in lexicographical order
- Trie saves space because of the prefix
- Trie can potentially faster than hashMap, when there are logs collisions for the map.

## Model
- children map: Map<Character, TrieNode>. Also can use char[26], but it's more scalable to us a map.
- always have isEnd which marks a end of a particular string

## sample peoblems
- insert
- search
- exist of prefix
- node when the prefix end

## 考点
- 一个一个字母遍历
- 需要节约空间
- 查找前缀


# Deque
- linear collection that supports insertion and removal at both ends. Pronounced 'deck'
- It's a queue && stack
- new ArrayDeque<Integer>()
- head/top: offerFirst(), pollFirst(), peekFirst()
- tail/bottom: offerLast(), pollLast(), peekLast() 
- 双端queue: 维护一个候选可能的最大值集合
- ex: Sliding WIndow Maximum

# Graph


# Topological Sort
- Sort vertices in a graph
- Run DFS, output reverse of finishing times of vertices (stored in a list) 
- G graph has a cycle? If there is a back edge, there is a cycle
- Job Schedule/ Course Schedule: should not have cycle, so acyclic

## Topological Sort - BFS
- https://www.youtube.com/watch?v=_LuIvEi_kZk
- Can be used to return the topologically sorted list
- The final sorted list will not include the element on a cycle; these vertices won't reduce to in-degree 0.
- 给一个graph of nodes
- 目标是根据edge 的 direction, 把这个graph 里面的 node sort 一个list
- 如果有cycle, 这个item就不会被放在最后的list 里面. 比如: 如果两个课互相是dependency, 就变成了cyclic dependency.
- 注意, 有些有cycle的题目里面要求直接fail掉, 因为有了cycle, topological sort的结果是缺element的, 也许对某个场景来说就是没有意义的.
- 相比DFS, BFS 更容易理解和walk through


## Topological Sort - DFS
- https://youtu.be/AfSk24UTFS8?t=42m
- 还是要先构建好 edges = map<node, list of node>; 或者edges = List[arraylist];
- dfs到底, 再没有其他child node的时候, 把这个node加进stack (垫底)
- 最终按照stack的顺序, pop()出来的顺序 (reverse) 就是正确的topological sort
- 这个比BFS有时候要灵活一些: 可以detect cycle on the fly, 而BFS的做法会到最后再结算cycle是否存在




# Array
- Arrays.asList([1,2,3]);

# Two Pointers

# Binary Search

## Basics
- 记得二分的template
- 往往不会有个数组让我们二分, 但是同样是要去找满足某个条件的最大/最小值
- 二分是个思想, 不是简单的array二分公式.
- 有时候在index上二分, mid是index; 但是有时候, 会在数值上二分, 那么mid就是value, 忌讳不要死板地套用nums[mid]

## 二分思想
- 按值二分，需要怎么二分性
- 找到可能的解的范围
- 猜答案
- 检验答案 (match/if/else ...)
- 调整搜索范围
- Find Peak Element II

# Sort

## Quick Sort

# Collections

## methods
- Collections.sort()

## ArrayList
- Integer[] array = {1, 2, 3};
- new ArrayList(Arrays.asList(array))

# Hash

# Map

# Hash Table

## HashSet
- contains: O(1)
- set.add(...) returns false if there is duplicate. This operation won't change the existing set.
- Build HashSet<List> set, and the set will automatically compare the equivalence of the lists within at each list element level.

# Basics

## Math
- 转换成string
- % mod, 除法
- Integer.MAX_VALUE, Integer.MIN_VALUE; if overflow, use long
- Integer.valueOf(number), where number is int


## String
- s.toCharArray()
- String.valueOf(charArrary)
- sb = new StringBuffer()
- sb.reverse(), sb.append(), sb.deleteCharAt(), sb.length(), sb.setCharAt(index, char)
- Character.isDigit(x)
- 遇到找string的相关问题: 考虑string的重复性

## Bit Manipulation
- Bit OR |, AND &, XOR ^
- Bit shift: <<, >>
- A << 1: binary of A shifted left for 1 bit, which result in value x 2
- A >> 1: divide by integer 2. Note: decimals are ignored in the result.
- bit shift is a lot faster than reqular 'times' operation.
- 32 bit number: leading bit = 1, negative numbjer; leading bit = 0, positive number.
- >> add leading '1' if the 32 bit number originally has leading '1'.
- Java/python: logical shift >>>, always add leading '0' regardless of the sign of the 32-bit number. That is, it may turn a negative number to positive, if the leading bit is originally '1'
- Because with '( )', make sure to surround the desired operation
- & 0000 = clean up; | ABC = assign ABC
- A^B=C, then A = B^C
- bits可以用来表示不同的状态, 比如2bit可以表示4种状态: 00, 01, 10, 11
- Math.pow(2, h) = 2 << (h - 1); 2 << 1就是把所有bits往左移动一位, 也就是 * 2 
- Also, 1 << h = 2 ^ h; 1 << h 就是 2 * 2 * 2* ....乘h次.

# DP

## Technique
- 滚动数组
- 记忆化搜索

## 分类
- 网格坐标
- 序列类
- 划分类
- 区间类(range DP)
- 背包类
- 双序列
- 博弈
- combos

## 区间类(range DP)
- dp[i][j] 表示 [i~j]之间的状态
- 求一段区间的解: max/min/count
- 转移方程通过区间更新: len = x
- 从大到小的更新

### 三把斧
- 中间劈开
- 砍断首或尾
- Range区间作为iteration的根本

## Sequence DP
- DP[]存的是以 1-based index的状态
- 需要知道dp[n] 的状态, 但是最大坐标是[n-1], 所以int[n+1]
- dp[0]往往是有特殊状态的


## 记忆化搜索 Memoization
- 本质是DP, 所有DP也都是为了解决重复计算
- 从大到小搜索, 其实是暴利解决的思路, 只是在深入到底的的过程中存了状态, 不需要重复计算.
- 什么时候用记忆化搜索: 1. 状态转移特别麻烦，不是顺序性; 2. 初始化状态不是很容易找到; 3. 从大到小

## Minimax


## Optimization problems
- memoization && subproblems
- Fibonacci
- Shortest paths
- guessing && DAG View

## Double Sequence
- Sequence problem, have dp[] length of n + 1.
- Look at last index for clues
- Usually can start for loop at index = 0, and we handle the init conditions within the for loop (ex: assign particular value or skip i=0 rows)
- Rolling array (curr, prev pointer) to optimize space; note the rolling dimension should be apply at the top-for loop.

## 存状态
- 复杂的dp, 有时候会需要存一个状态: 拿/不拿, 放1/0, 输/赢
- 通常加上一个维度


# Search


## Breadth-first Search
Track queue size, use the queue as in rotation

## Depth-first Search
- backtracking: do not repeatly visit a node
- DFS traverse O(n)

# Backtracking
- Finding all (or some) solutions to some computational problems, notebaly constraint satisfaction problems
- It attemps to build/find all candidates and abandon partial candidate when the candidates appears not to be suitable(backtracking, backing off from wrong candidates)



# Reservoir Sampling

# Geometry

# Brainteaser

# Red Black Tree


# Approach

## Greedy

## Divide and Conquer

## Recursion
- ex: dfs
- always find the entry point or terminating point
- watch out for the return or result of recursed function

# Design



# Data Structure
- Union Find
- Trie
- Heap: PriorityQueue[Java]. Made of: Binary Heap
- Hash: HashMap[Java]. Made of: HashMap
- TreeMap: TreeMap[Java]. Balanced Binary Tree
- TreeSet: TreeSet[Java]. Balanced Binary Tree

# Problem Sets

## Two Pointer

## Min/Max Heap
- 见到需要维护一个集合的最小值/最大值的时候要想到用堆
- 第k小的元素，Heap用来维护当前候选集合
- 见到数组要想到先排序

## Stack
- Monotonous stack的运用: 找左边和右边第一个比它大的元素
- 递归转非递归

## Windows Problem
- 加一个数
- 删一个数

## Sweep Line
- 见到区间需要排序就可以考虑扫描线
- 事件往往是以区间的形式存在
- 区间两端代表事件的开始和结束
- 需要排序
- Meeting Room I, II
