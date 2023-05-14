#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_BOOKS 100

typedef struct book {
    char title[50];
    char author[50];
    int year;
} Book;

void add_book(Book library[], int *num_books);
void search_book(Book library[], int num_books);
void remove_book(Book library[], int *num_books);

int main() {
    Book library[MAX_BOOKS];
    int num_books = 0;
    int choice;

    do {
        printf("\nLibrary Management System\n");
        printf("1. Add a book\n");
        printf("2. Search for a book\n");
        printf("3. Remove a book\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                add_book(library, &num_books);
                break;
            case 2:
                search_book(library, num_books);
                break;
            case 3:
                remove_book(library, &num_books);
                break;
            case 4:
                printf("Exiting library management system...\n");
                break;
            default:
                printf("Invalid choice.\n");
        }
    } while (choice != 4);

    return 0;
}

void add_book(Book library[], int *num_books) {
    if (*num_books >= MAX_BOOKS) {
        printf("Error: library is full.\n");
        return;
    }

    printf("\nEnter book details:\n");
    printf("Title: ");
    scanf("%s", library[*num_books].title);
    printf("Author: ");
    scanf("%s", library[*num_books].author);
    printf("Year: ");
    scanf("%d", &library[*num_books].year);

    printf("Book added to library.\n");
    (*num_books)++;
}

void search_book(Book library[], int num_books) {
    char title[50];
    printf("\nEnter book title to search for: ");
    scanf("%s", title);

    int i, found = 0;
    for (i = 0; i < num_books; i++) {
        if (strcmp(library[i].title, title) == 0) {
            printf("Book found:\n");
            printf("Title: %s\n", library[i].title);
            printf("Author: %s\n", library[i].author);
            printf("Year: %d\n", library[i].year);
            found = 1;
            break;
        }
    }

    if (!found) {
        printf("Book not found.\n");
    }
}

void remove_book(Book library[], int *num_books) {
    char title[50];
    printf("\nEnter book title to remove: ");
    scanf("%s", title);

    int i, found = 0;
    for (i = 0; i < *num_books; i++) {
        if (strcmp(library[i].title, title) == 0) {
            found = 1;
            break;
        }
    }

    if (!found) {
        printf("Book not found.\n");
        return;
    }

    // Shift books after the removed book to fill the gap
    for (; i < *num_books - 1; i++) {
        strcpy(library[i].title, library[i + 1].title);
        strcpy(library[i].author, library[i + 1].author);
        library[i].year = library[i + 1].year;
    }

    printf("Book removed");
}
