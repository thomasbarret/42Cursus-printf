# 42Cursus - PrintF

This repository contains the **PrintF** project for **42Cursus**, where you will recreate a simplified version of the `printf` function from the standard C library. The goal is to understand variable argument lists and how formatted output works in C.

---

## Repository Structure

```plaintext
.
├── Makefile          # Build system to compile the project
├── ft_printf.h       # Header file containing function prototypes
├── ft_printf.c       # Main printf function
├── ft_printchar.c    # Function to print a character
├── ft_printstr.c     # Function to print a string
├── ft_printnbr.c     # Function to print an integer
├── ft_printunbr.c    # Function to print an unsigned integer
├── ft_printhex.c     # Function to print a hexadecimal number
└── ft_printptr.c     # Function to print a pointer address
```

---

## Overview

This project focuses on creating a custom implementation of the `printf` function, supporting the following conversion specifiers:
- `%c` : Print a single character.
- `%s` : Print a string.
- `%d` or `%i` : Print an integer.
- `%u` : Print an unsigned integer.
- `%x` : Print a number in hexadecimal format (lowercase).
- `%X` : Print a number in hexadecimal format (uppercase).
- `%p` : Print a pointer address.

---

## Functions Implemented

| **Function**         | **Description**                                      |
|----------------------|------------------------------------------------------|
| `ft_printf`          | Main function that handles the format string and manages the conversion specifiers. |
| `ft_printchar`       | Handles the `%c` specifier to print a single character. |
| `ft_printstr`        | Handles the `%s` specifier to print a string. |
| `ft_printnbr`        | Handles the `%d` or `%i` specifiers to print an integer. |
| `ft_printunbr`       | Handles the `%u` specifier to print an unsigned integer. |
| `ft_printhex`        | Handles the `%x` specifier to print a hexadecimal number in lowercase. |
| `ft_printptr`        | Handles the `%p` specifier to print a pointer address. |

---

## How to Compile and Use

1. **Compile the Project**  
   Use the provided `Makefile` to build the project:  
   ```bash
   make
   ```
   This will generate the `libftprintf.a` static library.

2. **Link the Library**  
   To use the `ft_printf` function in your project, include the `ft_printf.h` header and link with the compiled static library:  
   ```c
   #include "ft_printf.h"

   int main(void) {
       ft_printf("Hello, %s! The number is %d.\n", "42", 100);
       return (0);
   }
   ```
   Compile with:  
   ```bash
   gcc -Wall -Wextra -Werror main.c -L. -lftprintf
   ```

3. **Clean Up**  
   Use the `make clean` command to remove object files or `make fclean` to remove the static library.

---

## Example

```c
#include "ft_printf.h"

int main() {
    ft_printf("Hello, %s! I have %d apples and %u oranges.\n", "World", 42, 10);
    ft_printf("Hex: %x | Pointer: %p\n", 255, (void *)0x1234ABCD);
    return 0;
}
```

**Output:**
```
Hello, World! I have 42 apples and 10 oranges.
Hex: ff | Pointer: 0x1234abcd
```