# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M5
# IAPR-5- Module 5 - FoC
9. Implementation of recursion.
10. Implementation of programs using pointer arithmetic.
# Ex.No:21
  Implement a C program to demonstrate call by value and call by reference by swapping two integers using separate functions.

## Aim:
 To implement a C program that illustrates the difference between call by value and call by reference by swapping two integer variables using two separate functions.
## Algorithm:
Step 1: Start<br>
Step 2: Include the standard input-output library: #include<stdio.h>.<br>
Step 3: Declare two functions:<br>
  - `swapv(int, int)` for swapping using call by value <br> 
  - `swapr(int *, int *)` for swapping using call by reference<br>
Step 4: In the `main()` function, declare two integer variables `a` and `b` and initialize them with values (e.g., 10 and 20).<br>
Step 5: Print the values of `a` and `b` before calling `swapv()`.<br>
Step 6: Call the function `swapv(a, b)` and print the values of `a` and `b` after the function call to show that call by value does not change the original values.<br>
Step 7: Print the values of `a` and `b` before calling `swapr()`.<br>
Step 8: Call the function `swapr(&a, &b)` using the addresses of `a` and `b`.<br>
Step 9: Print the values of `a` and `b` after the `swapr()` function call to show that call by reference successfully swaps the original values.<br>
Step 10: Inside `swapv(x, y)` function:<br>
  - Step 10.1: Swap the values of `x` and `y` using a temporary variable.  <br>
  - Step 10.2: Print the swapped values (formal parameters).<br>
Step 11: Inside `swapr(*x, *y)` function:<br>
  - Step 11.1: Swap the values pointed to by `x` and `y`.  <br>
  - Step 11.2: Print the swapped values (affects actual parameters).<br>
Step 12: Stop<br>
## Program:
```
#include <stdio.h>
void swapv(int x,int y){int t=x;x=y;y=t;printf("Inside swapv: %d %d\n",x,y);}
void swapr(int *x,int *y){int t=*x;*x=*y;*y=t;printf("Inside swapr: %d %d\n",*x,*y);}
int main(){
    int a=10,b=20;
    printf("Before swapv: %d %d\n",a,b);
    swapv(a,b);
    printf("After swapv: %d %d\n",a,b);
    printf("Before swapr: %d %d\n",a,b);
    swapr(&a,&b);
    printf("After swapr: %d %d\n",a,b);
    return 0;
}
```
## Output:
<img width="212" height="163" alt="image" src="https://github.com/user-attachments/assets/296cb543-3586-44d8-873d-cd3d7e1af015" />

## Result: 
  Thus, the program was implemented and executed successfully, and the required output was obtained.


# Ex.No:22
  Implement a C program to generate the Fibonacci series using a recursive function. The program should accept a positive integer n and display the first n terms of the Fibonacci sequence.
## Aim:
  To implement a C program that uses a recursive function to generate and display the Fibonacci series for a given number of terms.
## Algorithm:
Step 1: Start<br>
Step 2: Include the standard input-output library: #include<stdio.h>.<br>
Step 3: Declare a recursive function `fibo(int x)` that returns the Fibonacci number at position `x`.  <br>
Step 4: In the `main()` function, declare variables `n` and `i`.  <br>
Step 5: Prompt the user to enter a positive integer `n`.  <br>
Step 6: Read the value of `n`.  <br>
Step 7: Display a message indicating that the Fibonacci series of `n` terms will be printed.  <br>
Step 8: Use a `for` loop from `i = 0` to `i < n` to:  <br>
  - Step 8.1: Call the recursive function `fibo(i)`  <br>
  - Step 8.2: Print the returned Fibonacci value  <br>
Step 9: Define the recursive function `fibo(x)` as follows:  <br>
 - Step 9.1: If `x == 0` or `x == 1`, return `x`.  <br>
 - Step 9.2: Otherwise, return `fibo(x - 1) + fibo(x - 2)`.  <br>
Step 10: Stop<br>
## Program:
```
#include <stdio.h>
int fibo(int x){ return (x<=1)?x:fibo(x-1)+fibo(x-2); }
int main(){
    int n; scanf("%d",&n);
    for(int i=0;i<n;i++) printf("%d ",fibo(i));
    return 0;
}
```
## Output:
<img width="240" height="53" alt="image" src="https://github.com/user-attachments/assets/6d15d12b-09c3-4316-ae20-697a43f68e66" />

## Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# Ex.No:23
   Implement a C program to demonstrate recursion by printing a sequence of even or odd numbers from a given lower limit to an upper limit, with each recursive call progressing by 2.
## Aim:
  To implement a C program that uses a recursive function to print even or odd numbers in a specified range based on the starting value provided by the user.
## Algorithm:
Step 1: Start<br>
Step 2: Include the standard input-output library: #include<stdio.h>. <br>
Step 3: Declare a recursive function `printEvenOdd(int cur, int limit)` to print numbers from `cur` to `limit` with a step of 2.<br>
Step 4: In the `main()` function, declare two integer variables: `lowerLimit` and `upperLimit`.<br>
Step 5: Prompt the user to enter the lower limit of the range.<br>
Step 6: Read and store the lower limit.<br>
Step 7: Prompt the user to enter the upper limit of the range.<br>
Step 8: Read and store the upper limit.<br>
Step 9: Display a message indicating that the even/odd numbers in the given range will be printed.<br>
Step 10: Call the recursive function `printEvenOdd(lowerLimit, upperLimit)`.<br>
Step 11: Inside the function `printEvenOdd(cur, limit)`:<br>
  - Step 11.1: If `cur > limit`, terminate the recursion.  <br>
  - Step 11.2: If `cur == limit`, print the value without a trailing comma.  <br>
  - Step 11.3: Otherwise, print the current value followed by a comma.  <br>
  - Step 11.4: Recursively call `printEvenOdd(cur + 2, limit)` to print the next number.<br>
Step 12: Stop<br>
## Program:
```
#include <stdio.h>
void printEO(int cur,int limit){
    if(cur>limit) return;
    printf("%d ",cur);
    printEO(cur+2,limit);
}
int main(){
    int l,u; scanf("%d%d",&l,&u);
    printEO(l,u);
    return 0;
}
```
## Output:
<img width="220" height="81" alt="image" src="https://github.com/user-attachments/assets/eee400d9-b846-4dea-8abe-a0337ba96aa3" />

## Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# Ex.No:24
   Implement a C program that dynamically allocates memory using calloc(), accepts integer inputs from the user, computes their sum, and prints the sum.
## Aim:
  To implement a C program that dynamically allocates memory for an array of integers using calloc(), accepts elements from the user, computes their sum, and displays the sum.
## Algorithm:
Step 1: Start<br>
Step 2: Include the standard input-output library: #include<stdio.h>. <br>
Step 3:<br>
  a. Declare a pointer `ptr` to `int`.  <br>
  b. Declare integers `n`, `i`, and `sum` (initialize `sum = 0`).<br>
Step 4: Read the integer `n` from the user (the number of integers to be stored).<br>
Step 5: Use the `calloc()` function to allocate memory for `n` integers:  <br>
  `ptr = calloc(n, sizeof(int))`<br>
Step 6: If `ptr` is not `NULL`, continue to the next step; otherwise, memory allocation failed (the program exits).<br>
Step 7: For each `i` from `0` to `n - 1`:  <br>
  a. Read an integer from the user. <br> 
  b. Store it at memory location `ptr + i`.<br>
Step 8: For each `i` from `0` to `n - 1`:  <br>
  a. Access the value stored at `ptr + i`.  <br>
  b. Add it to `sum`.<br>
Step 9: Print the value of `sum`.<br>
Step 10: Call `free(ptr);` to release the memory allocated by `calloc()`.<br>
Step 11: Stop<br>
## Program:
```
#include <stdio.h>
#include <stdlib.h>
int main(){
    int n,*p,sum=0; scanf("%d",&n);
    p=(int*)calloc(n,sizeof(int));
    for(int i=0;i<n;i++){ scanf("%d",&p[i]); sum+=p[i]; }
    printf("Sum=%d\n",sum);
    free(p);
    return 0;
}
```
## Output:
<img width="158" height="86" alt="image" src="https://github.com/user-attachments/assets/db410ce6-40f5-49c6-ae6e-20ef333e0a17" />

## Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# Ex.No:25
   Implement a C program that reads a set of integers into an array and displays the array elements using a user-defined function.
## Aim:
  To implement a C program that reads integers into an array and displays the elements using a user-defined function.
## Algorithm:
Step 1: Start<br>
Step 2: Include the standard input-output library: #include<stdio.h>. <br>
Step 3: Declare the function prototype: `void displayArray(int *arr, int size);`<br>
Step 4: In the `main()` function, declare an integer array of size 5 and a loop variable.<br>
Step 5: Prompt the user to enter the required number of integers.<br>
Step 6: Read the integers from the user and store them in the array using a loop.<br>
Step 7: Call the `displayArray` function, passing the array and its size as arguments.<br>
Step 8: Define the function `displayArray(int *arr, int size)` to print the array elements:  <br>
  - Loop through the array using either pointer arithmetic (`*(arr + i)`) or array indexing (`arr[i]`).  <br>
  - Print each element.<br>
Step 9: Return to the `main()` function after displaying the array.<br>
Step 10: Stop<br>
## Program:
```
#include <stdio.h>
void display(int *a,int n){ for(int i=0;i<n;i++) printf("%d ",*(a+i)); }
int main(){
    int arr[5]; for(int i=0;i<5;i++) scanf("%d",&arr[i]);
    display(arr,5);
    return 0;
}
```
## Output:
<img width="161" height="56" alt="image" src="https://github.com/user-attachments/assets/e9ab01a4-ae59-4612-8287-795bc3d1ba62" />

## Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.
