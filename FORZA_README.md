# OpenCilk RISC-V Build Instructions

This repository contains scripts to build OpenCilk with RISC-V support. The build process is split into three steps:

1. Fetching the source code (`get` script)
2. Building the native compiler (`build-pt1.sh` script)
3. Building the RISC-V runtime (`build-pt2.sh` script)

## Prerequisites

- CMake (3.13.4 or newer)
- C/C++ compiler (GCC or Clang)
- RISC-V GNU Toolchain (riscv64-unknown-elf-)
- Git
- Standard build tools (make, etc.)

## Step 1: Getting the Source Code

Use the `get` script to clone the necessary repositories:

```bash
./get /path/to/source
```

This will:

- Clone the [forza-opencilk-project](https://github.com/tactcomplabs/forza-opencilk-project) repository (branch: dev/18.x-FORZA)
- Clone the [forza-cheetah](https://github.com/tactcomplabs/forza-cheetah) repository
- Clone the productivity-tools repository

## Step 2: Building the Native Compiler

Use `build-pt1.sh` to build the native & RISC-V OpenCilk compiler:

```bash
./build-pt1.sh /path/to/source /path/to/build [number-of-cores]
```

_Arguments:_

- `source-dir`: Absolute path to the OpenCilk source directory (created by the get script)
- `build-dir`: Absolute path where build outputs will be stored
- `core-count`: (Optional) Number of cores to use for parallel build
