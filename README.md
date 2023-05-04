Download Link: https://assignmentchef.com/product/solved-csci1913-lab-3
<br>
This assignment asks you to write a Python function that sorts a tuple of integers using the techniques of functional programming. This is the last Python lab for this course. We’re not done with Python yet: there is still a Python project yet to be assigned, there will be questions about Python on the first midterm, and one question about Python on the final.

<ol>

 <li></li>

</ol>

We say that a sequence of integers is <em>sorted</em> if it has elements <em>e</em>₀, <em>e</em>₁ …, <em>e</em>ⱼ₋₁ in that order, and also <em>e</em>₀ ≤ <em>e</em>₁ … ≤ <em>e</em>ⱼ₋₁. We can sort such a sequence <em>S</em> using the following algorithm.

<ol>

 <li>If <em>S</em> has no elements, then it is already sorted, so return <em>S</em>.</li>

 <li>Choose the largest element <em>m</em> from <em>S</em>. If <em>m</em> appears more than once in <em>S</em>, then choose any appearance of <em>m</em>.</li>

 <li>Make a new sequence that is like <em>S</em>, except that the first appearance of <em>m</em> is removed.</li>

 <li>Sort the new sequence by applying this algorithm recursively.</li>

 <li>Return the result of adding <em>m</em> to the end of the sorted sequence.</li>

</ol>

For example, suppose that the algorithm is implemented by the Python function Sort, which takes a tuple of integers as its argument. We can trace the algorithm like this, where + is Python’s concatenation operator, and ⇒ means <em>returns</em>.

Sort((1, 2, 3, 1)) ⇒  Sort((1, 2, 1)) + (3,)

⇒  Sort((1, 1)) + (2,) + (3,)

⇒  Sort((1,)) + (1,) + (2,) + (3,)

⇒  Sort(()) + (1,) + (1,) + (2,) + (3,)

⇒  () + (1,) + (1,) + (2,) + (3,)

⇒  (1, 1, 2, 3)

The algorithm does not change the values of variables after they are assigned, and does not use mutable data structures. As a result, it can be implemented using the techniques of functional programming that were discussed in the lectures.

<ol>

 <li></li>

</ol>

You must implement the sorting algorithm described in the previous section by defining the following Python functions. You must use the same names for the functions as are shown here, but you may use different parameter names if you like. Throughout, assume that T is a tuple of integers. The tuple may contain negative integers, zeroes, positive integers, or some mixture of these.

Sort(T)

Return a new tuple that is like T, except that its elements are sorted (see above). It works by calling Maximum and Remove somehow.

Maximum(T)

Assume that T has at least one element. Return the largest element from T, an integer. Hint: use a ‘‘helper’’ function to do most of the work.

Remove(T, E)

Return a new tuple that is like T, except that the first appearance of its element E is removed. If E does not appear in T, then Remove must return a tuple that is like T.

Some of these functions may be written easily using higher-order functions such as lambda, filter, map, and reduce. However, I won’t tell you which ones can be written this way, or which higherorder functions you should use. You need not use higher-order functions if you don’t want to.

All these functions <em>must</em> be written in a functional, recursive style, and your code must demonstrate that you know how to write in such a style. As a result, you will receive <strong>ZERO POINTS</strong> for this lab if your functions do any of the following things.

Use one or more global variables.

Use a loop, such as for or while.

Assign a value to a variable more than once.

Use mutable data structures, such as lists or dictionaries.

Also, you must not use operators or predefined functions that do things you are asked to write yourself—so you must not call a predefined sort function from the Python library. If you write additional ‘‘helper’’ functions, then they must not do these things either.

<ol start="3">

 <li></li>

</ol>

The file <a href="http://127.0.0.1:30030/_api/html/tests3.py"><strong>tests3.py</strong></a> on Canvas contains a series of tests. Each test calls a function from your program, then prints what the function returns. Each test also has a comment that says what it should print, and how many points it is worth.

To grade your work, the TA’s will run the tests using your functions. If a test prints exactly what it should, without error, then you will receive all the points for that test. However, if a test does anything else, then you will receive no points for that test. Your score for this lab is the sum of points you receive for all the tests.