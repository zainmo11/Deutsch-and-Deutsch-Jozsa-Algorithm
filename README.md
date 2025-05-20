# Deutsch and Deutsch-Jozsa Quantum Algorithms

This Jupyter notebook demonstrates implementations of the Deutsch and Deutsch-Jozsa algorithms, which are foundational quantum algorithms that showcase quantum computational advantage over classical computation.

## Overview

The notebook covers:
1. **Deutsch's Algorithm** - Determines if a single-bit function is constant or balanced with a single function evaluation
2. **Deutsch-Jozsa Algorithm** - The multi-qubit generalization of Deutsch's algorithm

## Prerequisites

To run this notebook, you'll need:

- Python 3.x
- Qiskit
- Qiskit-Aer (for quantum simulation)
- Matplotlib (for visualization)
- PyLatexEnc (for visualization)

Installation commands are included at the beginning of the notebook:

```bash
pip install qiskit
pip install qiskit-aer
pip install pylatexenc
```

## Deutsch's Algorithm

Deutsch's algorithm solves the following problem:
- Given a black-box function (oracle) f: {0,1} → {0,1}
- Determine if f is constant (f(0) = f(1)) or balanced (f(0) ≠ f(1))
- Do this with only one function evaluation (instead of two classical evaluations)

The notebook implements four different oracle functions:
1. **oracle_constant_0**: f(x) = 0 for all x
2. **oracle_constant_1**: f(x) = 1 for all x
3. **oracle_balanced_identity**: f(x) = x
4. **oracle_balanced_not**: f(x) = NOT(x)

The algorithm works by:
1. Preparing a superposition of all possible inputs
2. Applying the oracle function
3. Using interference to determine the function's property

### Results
- Constant functions produce a measurement of |0⟩ with 100% probability
- Balanced functions produce a measurement of |1⟩ with 100% probability

## Deutsch-Jozsa Algorithm

The Deutsch-Jozsa algorithm extends Deutsch's algorithm to n-bit functions:
- Given a black-box function f: {0,1}ⁿ → {0,1}
- Determine if f is constant or balanced (equal outputs for exactly half of all inputs)
- Do this with only one function evaluation (instead of 2^(n-1)+1 classical evaluations in worst case)

The notebook implements two oracles for n=3:
1. A balanced function (f(x) = 1 if first qubit is 1)
2. A constant function (f(x) = 1 for all x)

### Results
- Constant functions produce all zeros in the measurement (|000⟩) with 100% probability
- Balanced functions produce at least one non-zero measurement with 100% probability

## Key Quantum Concepts Demonstrated

- Quantum parallelism
- Quantum interference
- Phase kickback
- Hadamard transforms
- Quantum oracles
- Entanglement

## Circuit Components

The circuits include:
- Initialization of input and ancilla qubits
- Application of Hadamard gates to create superposition
- Oracle application using controlled operations
- Measurement of the result

## Educational Value

This notebook serves as an excellent introduction to:
- Basic quantum algorithms with provable speedup
- Quantum circuit design principles
- Oracle-based quantum algorithms
- Quantum computational advantage

## References

- [Qiskit Textbook: Deutsch-Jozsa Algorithm](https://qiskit.org/textbook/ch-algorithms/deutsch-jozsa.html)
- Nielsen, M. A., & Chuang, I. L. (2010). Quantum Computation and Quantum Information.
