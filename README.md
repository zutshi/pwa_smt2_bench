PWA Benchmarks:
===============
The included smt2 files are generated by hand using yice's input file
generated from SAL. Each dir contains several files which were used
to generate the benchmarks. Please ignore all, but the .smt2 files.

Background:
===========
The transition systems were obtained from Piecewise Affine (PWA)
dynamical systems. The coefficients of the PWA system are floating
points but encoded as reals.
All floats have been truncated to only 3 decimals; termed as -
'regular precision'

S3CAMR branch/version: develop/0b3205e9fe5bf5de366b929c62dba7432439fad7
SAL (sal-inf-bmc) version: 3.3
Yices version: 2.4.2


File Description:
=================
- .tst and .py: s3camr benchmarks
- .sal: SAL files
- .yices: Yices2 files
- .smt2: converted Yices2


Benchmark Description:
======================

-bball1:
    Bouncing ball in x-y

    -bench_1 [sat]
        regular precision
        python -O ./scamr.py -f ../examples/bball/bball.tst -cn  --refine model-dft --max-model-error 10 --prop-check --bmc-engine sal --incl-error -pmp --plots x0-x1

-const1:
    constant dynamics

    -bench_1 [sat]
        regular precision
        python -O ./scamr.py -f ../examples/linear/const1/const1.tst -cn  --refine model-dft --max-model-error 10 --prop-check --bmc-engine sal --incl-error --pvt-init-data 1 -p

    -bench_full_prec [sat]
        Full precision: 99 decimals
        python -O ./scamr.py -f ../examples/linear/const1/const1.tst -cn  --refine model-dft --max-model-error 10 --prop-check --bmc-engine sal --incl-error --pvt-init-data 1 -p

-nav30:
    Navigation benchmark (instance #30)

    -bench_1 [missing]
        regular precision
        python -O ./scamr.py -f ../examples/nav/nav30.tst -cn  --refine model-dft --max-model-error 1000 --prop-check --bmc-engine sal --incl-error --pvt-init-data 1 -p
        yices --mode=one-shot "/tmp/sal-zutshi-24978-input.yices" > "/tmp/sal-zutshi-24978-output.yices"
