# Vector calculator

## Description

This program is a command-line vector calculator made in C. It lets the user create and store three-component vectors (x,y,z) and perform basic vector operations.

The calculator supports vector addition, vector subtraction, and scalar multiplication.  Vectors can also be both loaded from and saved to CSV files.

Vector storage also uses dynamic memory so that the program is not limited to a fixed number of vectors, and does not take up more space than needed.

## Build instructions

The project can be built using the included Makefile.

```bash
make
```

To remove the executable (.exe), object files (.o), and dependency (.d) files:

```bash
make clean
```

## Running the program

Run the vector calculator with:

```bash
./myveclab
```

To show the program help information:

```bash
./myveclab -h
```

After starting the program, commands are entered at the `minimat>` prompt.

## Supported commands

### Create or replace a vector

```text
a = 1 2 3
```

Commas can also be used between vector values:

```text
a = 1,2,3
```

### Displaying a vector

```text
a
```

### Add two vectors

```text
a + b
```

The result can also be stored in another vector:

```text
c = a + b
```

### Subtract two vectors

```text
a - b
```

The result can also be stored:

```text
c = a - b
```

### Scalar multiplication

A vector can be multiplied by a scalar in either order:

```text
a * 2
```

or

```text
2 * a
```

The result can also be stored:

```text
b = a * 2
```

### Listing stored vectors

```text
list
```

### Clear stored vectors

```text
clear
```

This removes all currently stored vectors and frees the dynamically allocated memory.

### Load vectors from a file

```text
load filename
```

For example:

```text
load vectors.csv
```

The file uses CSV format, with one vector per line:

```text
a,1,2,3
b,4,5,6
```

If a loaded vector has the same name as a vector already in memory, then the existing vector is replaced.

### Save vectors to a file

```text
save filename
```

For example:

```text
save vectors.csv
```

All currently stored vectors are written to the file (in CSV format). An existing file with the same name is overwritten.

### Exit the program

```text
quit
```

## Dynamic memory

The original vector calculator used a fixed-size array (10 vectors max). The updated version uses dynamic memory so that vector storage can increase as needed.

The program track the number of vectors currently stored and how much memory is currently allocated. When more space is needed, the vector array allocates more memory.

Memory is released (freed) when the `clear` command is used and again when the program exits to ensure that allocated memory does not remain unused.

## Notes

Spaces are required around the `=`, `+`, `-`, and `*` operators for the vector calculator to properly detect these commands.

CSV filenames are entered exactly as they should be opened or saved. The program does not automatically add a `.csv` extension.