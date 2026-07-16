*This project has been created as part of the 42 curriculum by ryeong.*

# Project: push_swap
*more details can be asked during evaluation*

## Description
Your given 2 stacks, `a` and `b` along with a random list of numbers that must be sorted. **The goal is to sort the numbers into stack `a` in ascending order.** After which a list of operations used to sort the numbers is printed.

Used for visualizing the sorting:

https://push-swap-visualizer.vercel.app/

### Available Operations
`sa` (swap a): Swap the first 2 elements at the top of stack a.
Do nothing if there is only one element or none.

`sb` (swap b): Swap the first 2 elements at the top of stack b.
Do nothing if there is only one element or none.

`ss` : sa and sb at the same time.

---

`pa` (push a): Take the first element at the top of b and put it at the top of a.
Do nothing if b is empty.

`pb` (push b): Take the first element at the top of a and put it at the top of b.
Do nothing if a is empty.

---

`ra` (rotate a): Shift up all elements of stack a by 1.
The first element becomes the last one.

`rb` (rotate b): Shift up all elements of stack b by 1.
The first element becomes the last one.

`rr` : ra and rb at the same time.

---

`rra` (reverse rotate a): Shift down all elements of stack a by 1.
The last element becomes the first one.

`rrb` (reverse rotate b): Shift down all elements of stack b by 1.
The last element becomes the first one.

`rrr` : rra and rrb at the same time.

### Explanation and Justification of Algorithms Used

I used multiple algorithms depending on the number list size.

#### 1-3 numbers: Hardcoded Sort
---
I hardcoded the most efficient sort for all possible combinations as every combination only needs 1 or 2 operations at most. 

There are only 6 total combinations at 3 numbers so not much effort was required for high benefit.

#### 4-40 numbers: Selection Sort
---
Starts by taking the lowest number and places it at the leftmost unsorted position then moves on to the next highest. Repeats until sorted.

A very simple sorting algorithm but becomes inefficient very quickly at higher numbers due the time needed scales quadraticly. O(n<sup>2</sup>
)

![Visualization of selection sort](https://miro.medium.com/v2/1*5WXRN62ddiM_Gcf4GDdCZg.gif)

#### 41+ numbers: Binary Radix Sort
---

Sorts numbers by the least significant binary digit first and groups all the numbers based on the digit. Then move on to the next digit and repeat until sorted.

More efficient on higher number lists as the time needed scales linearly. O(n + k)

![Visualization of radix sort](https://miro.medium.com/v2/resize:fit:1400/1*EwTFPdvMoGtCrwKwWMqvJg.gif)

## Instructions
### Run Program:

```
./push_swap <any list of numbers of your choosing>
```
Example:
```
./push_swap 1 3 5 +9 20 -4 50 60 04 08
```

Numbers:
- cannot have duplicates
- cannot contain characters other than '0'-'9' and singular '+' or '-' before the number itself.
- must be within the integer limits.
- must be seperated by a single space.

### Count number of operations in Program:
```
./push_swap <any list of numbers of your choosing> | wc -l
```
Example:
```
./push_swap 1 3 5 +9 20 -4 50 60 04 08 | wc -l
```
This will just give the total number of operations instead of printing the list of operations.

### Running together with the checker:
```
ARG="<any list of numbers of your choosing>"; ./push_swap $ARG | ./checker_linux $ARG
```
Example:
```
ARG="3 4 6 8 9 74 -56 +495"; ./push_swap $ARG | ./checker_linux $ARG
```

## Resources
#### Readme
- https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax


#### General
- https://42-cursus.gitbook.io/guide/2-rank-02/push_swap/building-the-thing // borrowed its error checklist to handle the possible input scenarios. (site is now dead as of 2026-02-25)
- https://push-swap-visualizer.vercel.app/ // for visual feedback (Note: I did not make this)

### Declaration of AI Use
- Assist in memory leak solving
- Assist in shortening code to fit within 25 lines.
- Counseling for algorithm selection.
- Assist in algorithm optimization ideas.