# Prefix Sum

## Introduction

Prefix Sum is a method to quickly find the sum of elements in an array from the start up to any position.

## How It Works

Given an array **A**, the prefix sum array **P** is built as follows:

\[ P[i] = A[i] + P[i-1] \]

where:

- **P[0] = A[0]** (first element remains the same)
- **P[i]** stores the sum of all elements from index **0 to i** in **A**.

## Example

### Given Array:

A = [4, 5, 6, 7]

### Prefix Sum Array:

P(A) = [4, 9, 15, 22]

### Explanation:

- P[0] = A[0] = 4
- P[1] = A[1] + P[0] = 5 + 4 = 9
- P[2] = A[2] + P[1] = 6 + 9 = 15
- P[3] = A[3] + P[2] = 7 + 15 = 22

## Implementation in C++

```cpp
#include <iostream>
#include <vector>
using namespace std;

vector<int> prefixSum(vector<int>& arr) {
    vector<int> prefix(arr.size());
    prefix[0] = arr[0];
    for (size_t i = 1; i < arr.size(); i++) {
        prefix[i] = prefix[i - 1] + arr[i];
    }
    return prefix;
}

int main() {
    vector<int> A = {4, 5, 6, 7};
    vector<int> P = prefixSum(A);

    for (int val : P) {
        cout << val << " ";
    }
    return 0;
}
```

## Uses

- Quickly find sum of elements from the start up to any index
- Helps in solving subarray sum problems efficiently

## Time Complexity

- **Building Prefix Sum Array:** \(O(n)\)
- **Finding Range Sum:** \(O(1)\) (after preprocessing)
