#include <stdio.h>
#include <stdlib.h>
#include <time.h>


void generatePassword(int length) {
    const char characterPool[] = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789!@#$%^&*()_-+=[]{}";
    int poolSize = sizeof(characterPool) - 1;
    
   
    srand(time(NULL));
    
    for (int i = 0; i < length; i++) {
        int randomIndex = rand() % poolSize;
        char randomChar = characterPool[randomIndex];
        printf("%c", randomChar);
    }
    
    printf("\n");
}

int main() {
    int passwordLength;
    
    printf("Enter the desired length of the password: ");
    scanf("%d", &passwordLength);
    
    printf("Generated password: ");
    generatePassword(passwordLength);
    
    return 0;
}
