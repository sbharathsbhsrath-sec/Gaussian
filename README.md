# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Input the augmented matrix of the system of linear equations.
2. Perform forward elimination to convert the matrix into an upper triangular form using row operations.
3. Check for division by zero by ensuring that each pivot element is non-zero before elimination.
4. Apply back substitution to compute the values of the unknown variables and display the solution.

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: bharaths
RegisterNumber: 212225230031
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
n=int(input())
a=np.zeros((n,n+1))
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
x=np.zeros(n)
for i in range(n):
    if a[i][i]==0:
        print('divide by zero detected')
        exit()
        
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range (n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print("X%d = %0.2f" % (i,x[i]),end=' ')
```

## Output:
<img width="874" height="488" alt="image" src="https://github.com/user-attachments/assets/ad5283dc-521c-406f-8cd9-9b73fd59448c" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

