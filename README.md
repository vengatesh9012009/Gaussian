# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Start the program and read the augmented matrix.
2. Check the pivot element;if it is zero,stop the program.
3. Perform forword elimination without swapping rows,then use back substitution.
4. Display the solution and stop the program.

## Program:
```
/*
 '''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: VENGATESH S
RegisterNumber: 26018307
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
   for j in range(n+1):
     a[i][j]=float(input())
for i in range(n):
   if a[i][j]==0.0:
      sys.exit('Divide by zero detected!')
   for j in range(i+1,n):
      ratio=a[j][i]/a[i][i]
      for k in range(n+1):
          a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
   x[i]=a[i][n]
   for j in range(i+1,n):
      x[i]=x[i]-a[i][j]*x[j]
   x[i]=x[i]/a[i][i]
for i in range(n):
   print('X%d = %0.2f' %(i,x[i]),end=' ')     
*/
```

## Output:
<img width="400" height="400" alt="{8FC01A17-D4FB-4F12-952A-A12E0ABC62F7}" src="https://github.com/user-attachments/assets/fce24254-d100-4e96-b1f7-ec16f4f9408d" />
<img width="400" height="400" alt="{C8086C63-A582-4031-ACA6-802FF8C29F35}" src="https://github.com/user-attachments/assets/28942102-6f54-41f6-8db6-0857cdaefe60" />
<img width="400" height="400" alt="{631F4B25-1C3F-410B-ABA1-0B8884CA45FD}" src="https://github.com/user-attachments/assets/65693c59-f474-420c-93bb-a0be1e7ffaec" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

