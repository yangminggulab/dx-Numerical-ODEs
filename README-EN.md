## Overall Roadmap

Following MIT numerical differential equations and numerical PDE courses, the subject studies both ODE initial-value methods such as Euler, implicit Euler, error, and stability, and finite-difference methods for elliptic, parabolic, and hyperbolic PDEs. This repository follows exactly that line: ODE time stepping plus PDE finite differences.

```text
Numerical Differential Equations = turning continuous equations into computable discrete problems
|
+-- The central problems
|   +-- When analytic solutions are unavailable, how can approximate solutions be computed step by step?
|   |   +-- Use Euler, implicit Euler, predictor-corrector, and related ODE stepping schemes.
|   +-- How can continuous PDEs be placed on finitely many grid points?
|   |   +-- Use grids, difference quotients, and boundary conditions to build algebraic systems.
|   +-- Why should a numerical solution be trusted?
|       +-- Check local truncation error, consistency, stability, and convergence.
|
+-- Tool 1: ODE initial-value problems -> moving forward from slopes
|   +-- Lipschitz condition       lets error recurrence be controlled
|   +-- Explicit Euler            simple current-slope stepping with conditional stability
|   +-- Implicit Euler            heavier computation but stronger stability
|   +-- Predictor-corrector       predict first, then correct with averaged slopes
|   +-- Local/global truncation error distinguish one-step error from accumulated error
|
+-- Tool 2: discretization language -> from continuum to grid
|   +-- Mesh generation           split intervals or regions into finitely many nodes
|   +-- Difference quotients      replace derivatives with discrete values
|   +-- Consistency               check that the difference operator approximates the differential operator
|   +-- Stability and convergence control error amplification
|
+-- Tool 3: elliptic equations -> steady boundary-value problems
|   +-- Five-point difference schemes convert Laplace/Poisson problems to linear systems
|   +-- Triangular-grid differences handle more flexible region partitions
|   +-- Discrete maximum ideas    support uniqueness and stability control
|
+-- Tool 4: parabolic equations -> time evolution of diffusion
|   +-- Explicit schemes          compute the next step directly
|   +-- Implicit schemes          trade linear solves for better stability
|   +-- Stability restrictions    decide how time step and mesh width can fit together
|
+-- Tool 5: hyperbolic equations -> numerical propagation
    +-- Difference schemes        approximate wave propagation
    +-- Initial and boundary data put propagation problems on grids
    +-- Stability analysis        keep wave errors from being amplified
```

# dx's Numerical Differential Equations

## Preface

Numerical methods are fascinating not only because they produce approximate values, but because they force us to understand the original equations again in a different language.

Once we ask what to do when no analytic solution is available, the problem changes. We must ask how derivatives become differences, how boundary conditions constrain unknowns, why an interior point can be determined by surrounding points, and why some schemes remain stable while others amplify error.

## Why This Book Is Written This Way

I did not want this subject to become a list of schemes. Euler methods, finite differences, stability, consistency, and convergence are not templates to memorize. They are translations from continuous problems into discrete, computable, and controllable objects.

Many explanations in the notes keep this translation visible: slopes become directions, step sizes decide how far to move, grid points represent unknown values, and local relations are preserved through difference formulas.

## What This Book Keeps

The first part builds the core ideas for numerical ODEs: Euler methods, local truncation error, stability, convergence, and consistency. The later part develops finite-difference methods for elliptic equations and then moves toward parabolic and hyperbolic problems, dual grids, conservation relations, and different discrete schemes.

The main question throughout is how a continuous problem becomes something a machine can compute without losing mathematical control.

## Intended Readers

This book is for readers who understand differential equations but feel a channel switch when numerical analysis begins. It tries to make the transition from continuous equations to discrete schemes explicit and natural.

## Repository Notes

- The main entry is `main.tex`.
- The chapter files cover ODE time stepping and finite-difference methods for PDEs.
- The notes emphasize finite differences, triangular-grid differences, stability, and discretization for different equation types.
- For local compilation, running `xelatex main.tex` twice is usually enough.
