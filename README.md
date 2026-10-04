# C-Lang-Prac

**A curated collection of C language practice programs for beginners and intermediate learners**

![GitHub license](https://img.shields.io/github/license/imaakarsh/C-Lang-Prac) ![GitHub stars](https://img.shields.io/github/stars/imaakarsh/C-Lang-Prac?style=social) ![GitHub last commit](https://img.shields.io/github/last-commit/imaakarsh/C-Lang-Prac)

[Demo (Windows)](#usage) • [Issues](https://github.com/imaakarsh/C-Lang-Prac/issues) • [Pull Requests](https://github.com/imaakarsh/C-Lang-Prac/pulls)

## Table of Contents

1. [Overview](#overview)
2. [Features](#features)
3. [Tech Stack](#tech-stack)
4. [Project Structure](#project-structure)
5. [Getting Started](#getting-started)
   - [Prerequisites](#prerequisites)
   - [Installation](#installation)
   - [Configuration](#configuration)
6. [Usage](#usage)
7. [Development](#development)
8. [Troubleshooting & FAQ](#troubleshooting--faq)
9. [Roadmap](#roadmap)
10. [Contributing](#contributing)
11. [License & Credits](#license--credits)

## Overview

**C-Lang-Prac** is a sandbox of small, self-contained C programs that illustrate core language concepts—arrays, pointers, control flow, functions, recursion, and more. Each source file (`*.c`) is paired with a pre-compiled Windows executable (`*.exe`) for quick testing, while the source remains fully portable to any C compiler.

The repository is ideal for:

- Students learning C fundamentals.
- Instructors looking for ready-made examples.
- Developers who need quick reference snippets.

Current version: **v1.0.0** (April 2026)

## Features

| Category | Example Files | Description | Status |
|----------|---------------|-------------|--------|
| **Basic I/O** | `hello.c`, `ch.c` | Print "Hello, World!" and character handling. | Stable |
| **Control Flow** | `if.c` (not present but can be added), `break.c`, `continue.c` | Demonstrates `if/else`, `break`, `continue`. | Stable |
| **Loops** | `forloop.c`, `while.c` (future) | `for`, `while`, `do-while` loops. | Stable |
| **Functions** | `function.c`, `pointersfunctioncall.c` | Function definitions, return values, argument passing. | Stable |
| **Arrays** | `array.c`, `array-pointers.c` | Static arrays, pointer arithmetic, element access. | Stable |
| **Pointers** | `pointers.c`, `pinter1.c` | Basic pointer usage, dereferencing, address arithmetic. | Stable |
| **Recursion** | `recursion.c` | Classic factorial / Fibonacci examples. | Stable |
| **Mathematical** | `factorial.c`, `sum.c`, `sq-area.c` | Simple arithmetic calculations. | Stable |
| **File Structure** | `.vscode/` folder | VS Code configuration for easy compilation/debugging. | Stable |
| **Pre-compiled Binaries** | `*.exe` files | Ready-to-run executables for Windows users. | Stable |

## Tech Stack

| Layer | Tool / Technology | Reason |
|-------|-------------------|--------|
| **Language** | C (C99) | Portable, low-level learning. |
| **Compiler** | GCC (MinGW) on Windows, `gcc`/`clang` on Linux/macOS | Free, widely available. |
| **IDE / Editor** | Visual Studio Code (`.vscode/` settings) | Provides IntelliSense and build tasks. |
| **Build System** | Simple `gcc` command line (no external build system required). |
| **Version Control** | Git + GitHub | Collaboration & history. |

## Project Structure

The repository follows a flat, convention-over-configuration layout:

```
C-Lang-Prac/
├─ .vscode/                # VS Code launch configurations & include paths
│   ├─ c_cpp_properties.json
│   └─ *.c (sample files for quick testing)
├─ *.c                     # Individual practice source files
├─ *.exe                   # Pre-compiled binaries (Windows)
└─ README.md               # This documentation
```

*Each `*.c` file is a standalone program with its own `main()` function.* No inter-file dependencies exist, making it trivial to add, remove, or modify examples without affecting others.

## Getting Started

### Prerequisites

| Requirement | Minimum Version | Notes |
|-------------|----------------|-------|
| **Git** | 2.30+ | To clone the repository. |
| **C Compiler** | GCC 9.0+ (MinGW on Windows) or Clang 10+ | Verify with `gcc --version`. |
| **Make (optional)** | GNU Make 4.2+ | For batch compilation (see `Makefile` in future). |
| **VS Code** (optional) | 1.70+ | Uses the `.vscode` configuration. |
| **Windows** (for pre-compiled `.exe`) | — | Linux/macOS users must compile from source. |

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/imaakarsh/C-Lang-Prac.git
cd C-Lang-Prac

# 2. (Optional) Install MinGW on Windows
#    Download from https://www.mingw-w64.org/ and add gcc to PATH.

# 3. Verify compiler availability
gcc --version   # should print version information
```

### Configuration

No additional configuration is required for basic use. If you wish to customize VS Code settings, edit `.vscode/c_cpp_properties.json` to point to your compiler's include directories.

## Usage

### Running a pre-compiled example (Windows)

```powershell
# Example: run the hello world program
.\hello.exe
```

### Compiling and running a source file (cross-platform)

```bash
# Compile `array-pointers.c` to an executable named `array-pointers`
gcc array-pointers.c -o array-pointers

# Run the program
./array-pointers   # on Linux/macOS
array-pointers.exe # on Windows (if you used .exe extension)
```

#### Sample Output (`array-pointers.c`)

```text
ptr = 140735123456784
ptr = 140735123456788
```

*The program prints the address of `age`, then the address after pointer arithmetic (`ptr++`).*

### Quick Reference: Compile All Files (Windows)

```batch
for %%f in (*.c) do gcc "%%f" -o "%%~nf.exe"
```

*(Run from a Command Prompt inside the repository.)*

### Adding a New Example

1. Create `mytopic.c` with a `main()` function.
2. (Optional) Add a corresponding build task in `.vscode/tasks.json`.
3. Commit and push – the repository will automatically include the new source file.

## Development

### Setting up a Development Environment

1. **Clone** the repo (see above).
2. Open the folder in **VS Code** – the workspace will automatically pick up the `.vscode` configuration.
3. Use the built-in **Run > Start Debugging** (F5) to compile and debug a single file.

### Running Tests

There are currently no automated tests. Contributors are encouraged to add a `tests/` directory with unit tests using a framework such as **Unity** or **CMocka**.

### Code Style Guidelines

| Rule | Description |
|------|-------------|
| **Indentation** | 4 spaces, no tabs. |
| **Naming** | `snake_case` for variables and functions. |
| **Braces** | K&R style – opening brace on the same line. |
| **Comments** | Block comment header describing purpose, author, and date. |
| **Safety** | Always check return values of I/O functions (`scanf`, `printf`). |
| **Portability** | Prefer standard C library functions; avoid platform-specific APIs unless wrapped. |

### Debugging Tips

- Use `gcc -g -Wall -Wextra` to enable debugging symbols and warnings.
- Run `gdb ./program` to step through code.
- VS Code's **C/C++ Extension** provides inline debugging when a launch configuration is present.

## Troubleshooting & FAQ

| Problem | Solution |
|---------|----------|
| `gcc: command not found` | Ensure GCC is installed and added to your system `PATH`. |
| Executable crashes with **Access Violation** | Verify you are not dereferencing a `NULL