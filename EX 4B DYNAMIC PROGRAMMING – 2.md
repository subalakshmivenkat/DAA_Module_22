# EX 4B DYNAMIC PROGRAMMING – 2
## DATE:
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..
## Algorithm
1. Create a table lookup to store lengths of matching characters.
2. Compare each character of X with each character of Y.
3. If characters match, update the lookup value and track the maximum length and ending position.
4. After filling the table, the longest common substring is found at the tracked position.
5. Extract and print the substring from X using the recorded indices. 

## Program:
```
/*
Program to implement the longest common substring problem
Developed by: Subalakshmi V
Register Number:  212222040162
*/
```
```
def LCS(X, Y, m, n):
    maxLength = 0
    endingIndex = m
    lookup = [[0 for x in range(n + 1)] for y in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i - 1] == Y[j - 1]:
                lookup[i][j] = lookup[i - 1][j - 1] + 1
                if lookup[i][j] > maxLength:
                    maxLength = lookup[i][j]
                    endingIndex = i
    return X[endingIndex - maxLength: endingIndex]

X = input()
Y = input()
m = len(X)
n = len(Y)
print('The longest common substring is', LCS(X, Y, m, n))
```
## Output:
![image](https://github.com/user-attachments/assets/59fec08f-e836-426b-a3ea-39848a34d4b3)

## Result:
Thus the program was executed successfully for finding the longest common substring .
