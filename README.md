# Compiler-Lab


README for a Simple Calculator Using Flex on Windows



# Simple Calculator Using Flex and Bison on Windows

This project implements a basic calculator using Flex and Bison on Windows, capable of performing addition, subtraction, multiplication, and division.

## Features

- Performs basic arithmetic operations:
  - Addition (`+`)
  - Subtraction (`-`)
  - Multiplication (`*`)
  - Division (`/`)
- Supports integer and floating-point numbers.
- Basic error handling for invalid inputs.

## Prerequisites

Make sure you have the following installed:

- Flex: Lexical analyzer generator.
- Bison: Parser generator.
- GCC: C compiler for compiling the generated code.

### Installation on Windows

1. Install Flex and Bison using Win flex-bison (Windows distribution of Flex and Bison). Download from [SourceForge](https://sourceforge.net/projects/winflexbison/).

2. Install GCC:
   - Use MinGW to install GCC. Download from [MinGW](http://www.mingw.org/).

3. Add `flex`, `bison`, and `gcc` to your system PATH.

## How to Run

### Step 1: Write the Flex and Bison Files
Ensure you have two files:
- calc.l: The Flex file for tokenizing input.
- calc.y: The Bison file to define parsing and the structure of the calculator.

### Step 2: Generate and Compile the Code

1. Open a Command Prompt or PowerShell and navigate to your project directory.
   
2. Run Bison to generate the parser code:
   ```bash
   bison -d calc.y
   ```

   This will generate the `calc.tab.c` and `calc.tab.h` files.

3. Run Flex to generate the lexical analyzer:
   ```bash
   flex calc.l
   ```

   This will generate the `lex.yy.c` file.

4. Compile the generated files with GCC:
   ```bash
   gcc lex.yy.c calc.tab.c -o calc.exe
   ```

### Step 3: Run the Calculator

After compiling, run the calculator by typing:
```bash
./calc.exe
```

## Usage

You can enter arithmetic expressions, and the calculator will output the result:

```bash
Enter expression: 10 + 5
Result: 15

Enter expression: 20 * 3
Result: 60

Enter expression: 8 / 2
Result: 4
```

### Error Handling

The calculator will display an error message for invalid inputs such as malformed expressions or unsupported operators.

## Code Structure

- calc.l: The Flex file containing the lexical rules for recognizing numbers and operators.
- calc.y: The Bison file defining the grammar and rules for parsing expressions.


