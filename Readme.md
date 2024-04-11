nbody-starter
=============

*nbody-starter* is the starter code for a naive N-body simulator intended for parallelization. The C serial program generates a test dataset of planetary bodies, computes the forward N-body simulation, and writes the result to standard output. The resulting data can be replayed using the accompanying Unity [project](https://github.com/toksaitov/nbody-project).

The starter code in `nbody.c` is designed for you to create a parallelized version in the `nbody-mpi.c` file.

## Prerequisites

* *Open MPI* `>=4.1.2`

## Usage

Ensure that Open MPI is installed and your parallelized solution is prepared. Then, compile the programs:

```bash
make
```

Next, execute the parallelized program. Remember to specify all required command-line arguments:

```
time mpirun -np <number of processes>             \
    ./nbody-mpi <time period (~10-100)>           \
                <delta time (~0.01-0.1)>          \
                <body count (~100-1000)>          \
                <initial body mass (~10000)>      \
                <softening length (~100)>         \
                [debug acceleration scale (~100)] > <file to write the output>
```

You can run the serial program as follows:

```
time ./nbody <time period (~10-100)>           \
             <delta time (~0.01-0.1)>          \
             <body count (~100-1000)>          \
             <initial body mass (~10000)>      \
             <softening length (~100)>         \
             [debug acceleration scale (~100)] > <file to write the output>
```

## Licensing

*nbody-starter* is licensed under the MIT license. See LICENSE for the full license text.

## Credits

*nbody-starter* was created by [Dmitrii Toksaitov](https://github.com/toksaitov).
