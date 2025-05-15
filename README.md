# HILL CIPHER
HILL CIPHER
EX. NO: 3 AIM:
 

IMPLEMENTATION OF HILL CIPHER
 
## To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.
## PROGRAM:

'''

       #include <stdio.h>
        #include <string.h>
        
        #define SIZE 2 
        
        void encrypt(char plaintext[], int key[SIZE][SIZE]) {
            int cipher[SIZE], i, j;
            char encryptedText[SIZE + 1];
        
            int textVector[SIZE] = {plaintext[0] - 'A', plaintext[1] - 'A'};
        
            for (i = 0; i < SIZE; i++) {
                cipher[i] = 0;
                for (j = 0; j < SIZE; j++)
                    cipher[i] += key[i][j] * textVector[j];
                cipher[i] %= 26;  
                encryptedText[i] = cipher[i] + 'A';
            }
            encryptedText[SIZE] = '\0';
        
            printf("Encrypted Text: %s\n", encryptedText);
        }
        
        int main() {
            int key[SIZE][SIZE];
            char plaintext[SIZE + 1];
        
            printf("Enter a 2-letter plaintext (UPPERCASE): ");
            scanf("%s", plaintext);
        
            printf("Enter 2x2 key matrix (4 numbers): ");
            for (int i = 0; i < SIZE; i++)
                for (int j = 0; j < SIZE; j++)
                    scanf("%d", &key[i][j]);
        
            encrypt(plaintext, key);
        
            return 0;
        }

'''


## OUTPUT:
![image](https://github.com/user-attachments/assets/239f5415-39e4-4610-84f4-301d7f108259)


## RESULT
