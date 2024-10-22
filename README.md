# Exp-14-Implement-Hash-Function
## AIM:
To implement a simple hash function in C to convert a string into a fixed-size hash value using basic hashing techniques.

## ALGORITHM:
Step 1:
Initialize a hash value (e.g., to 0 or a large prime number).

Step 2:
For each character in the input string , Multiply the current hash value by a constant (e.g., a prime number).

Step 3:
Add the ASCII value of the character to the hash and apply a modulo operation to keep the hash value within bounds if necessary.

Step 4:
Return the computed hash value.

Step 5:
Test the hash function with different strings to observe how the output varies.

## PROGRAM :
```C
#include <stdio.h>
#include <string.h>

// Simple hash function using the DJB2 algorithm (one of the popular hash functions)
unsigned long hashFunction(const char *str) {
    unsigned long hash = 5381;  // Initial hash value (chosen prime number)
    int c;
    
    while ((c = *str++)) {
        // hash * 33 + c (ASCII value of the current character)
        hash = ((hash << 5) + hash) + c;
    }
    
    return hash;
}

int main() {
    char input[256];
    
    // Input the string to be hashed
    printf("Enter the string to hash: ");
    fgets(input, sizeof(input), stdin);
    input[strcspn(input, "\n")] = 0;  // Remove the newline character
    
    // Generate the hash
    unsigned long hashValue = hashFunction(input);
    
    // Print the hash value
    printf("Hash value of '%s' is: %lu\n", input, hashValue);
    
    return 0;
}
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/4d223c20-87ad-4f1e-a351-eaa1c2fdc1b5)

## RESULT:
Thus, the hash function has been successfully implemented in C.
