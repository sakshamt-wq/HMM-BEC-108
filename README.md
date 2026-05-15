# HMM Splice Site Predictor
A Python-based implementation of a Hidden Markov Model (HMM) designed to identify splice sites in DNA sequences by modeling the transitions between exons and introns.

# Features
State Modeling: Defines states for Exons, Introns, and Splice Sites.

Probabilistic Inference: Computes log-probabilities to determine the most likely structure of a given DNA sequence.

Numerical Stability: Performs calculations in log-space to prevent underflow issues common with small probabilities.

# Prerequisites
Python 3.x

NumPy

# Installation
Ensure you have the required dependency installed:

Bash
pip install numpy
Usage
Clone this repository to your local machine.

Ensure your input DNA sequence is defined in the script.

Run the model:

Bash
python hmm.py
Project Structure
hmm.py: The core script containing the HMM logic, transition/emission matrices, and probability calculations.

README.md: Project documentation.

# Troubleshooting
If you encounter errors related to path iteration, ensure your main execution loop is structured as follows:

Python
for p in LENGTHS:
    prob = get_log_prob_for_state_path(p, query_sequence) + math.log(0.1)
    results.append((p, prob))
    print(p, ":", prob)
