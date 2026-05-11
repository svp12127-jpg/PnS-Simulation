# Randomness — Probability & Statistics Simulations

A collection of Jupyter notebooks exploring randomness and probability distributions through simulation.

> *"Understanding random variables and probability distributions through simulation. Observe how Bernoulli, Binomial, and Poisson distributions behave."*

---

## Topics Covered

- **Bernoulli Distribution** — Simulating coin tosses; frequentist interpretation of probability; how histogram shape converges to the PMF as the number of experiments grows
- **Binomial Distribution** — Simulating sums of Bernoulli trials; the Galton Board (Quincunx) model; profit/loss gambling analogy; Poisson country population model
- **Poisson Distribution** — Simulating Poisson RVs; varying the rate parameter α; deriving Poisson as the limiting case of a Binomial as n → ∞ with np = α fixed
- **Central Limit Theorem (CLT)** — Observing how the distribution of a sum of iid RVs becomes bell-shaped as the number of terms increases
- **Law of Large Numbers (LLN)** — Observing how the distribution of the sample average concentrates around the true mean as the number of trials grows

---

## Project Structure

```
randomness-main/
│
├── ps_course/
│   ├── 2025630.ipynb              # Homework submission (Simulation HW 1)
│   ├── Questions.ipynb            # Assignment questions (HW 1, Q1–Q3)
│   │
│   └── probability/
│       ├── Bernoulli.ipynb        # Reference: Bernoulli RV simulations
│       ├── Binomial.ipynb         # Reference: Binomial RV simulations + CLT/LLN
│       └── Poisson.ipynb          # Reference: Poisson RV simulations
│
└── README.md
```

---

## Homework Assignment (Simulation HW 1)

The `Questions.ipynb` file contains three questions answered in `2025630.ipynb`:

**Question 1 — Bernoulli Simulations (p = 0.2)**
- (a) Toss a biased coin 20 times; plot outcomes vs. trial number
- (b) Repeat 5 times on the same figure; observe variability across runs
- (c) Repeat 100 times; plot histogram of total heads per sequence — observe the Binomial PMF emerge
- (d) Filter sequences with ≥ 3 heads; re-plot histogram — observe the conditional PMF

**Question 2 — Binomial as an Approximation to Poisson**
- Pick 4 values of α uniformly from (0, 100)
- For each α, find the minimum Binomial(n, p) with np = α that visually approximates Poisson(α)
- Overlay Binomial and Poisson histograms for comparison

**Question 3 — CLT and LLN for Poisson RVs**
- Pick 2 values of α from (1, 20)
- For each α, sum an increasing sequence of iid Poisson(α) RVs (e.g. 5, 10, 100, 1000 terms)
- Observe the histogram converging to a bell curve (CLT) and concentrating around the mean (LLN)

---

## Prerequisites

- Python 3.10+
- Jupyter Notebook or VS Code with the Jupyter extension (recommended)

Install the required libraries:

```bash
pip install numpy scipy matplotlib jupyter
```

---

## How to Run

1. Clone or download the repository
2. Launch Jupyter:

```bash
jupyter notebook
```

3. Open any notebook under `ps_course/` to explore the simulations, or open `2025630.ipynb` for the full homework solution

---

## Key Functions

| Function | Description |
|---|---|
| `aBernoulliExperiment(rng, p, numRepeatsOfExp, numTrialsInAnExp)` | Simulates one or more Bernoulli experiments |
| `np.random.default_rng(seed)` | Seeded random number generator for reproducibility |
| `np.random.poisson(lam, size)` | Generates Poisson(α) samples (lam = α) |
| `matplotlib.pyplot.step()` | Step-function plots used to visualise trial-by-trial outcomes |

---

## Notes

- The Binomial reference notebook includes an analogy to the **Galton Board** (Quincunx machine) to build intuition for the Binomial distribution
- The Poisson notebook formally derives why Binomial(n, p) → Poisson(α) as n → ∞ with np = α fixed
- All simulations use a seeded RNG (`np.random.default_rng`) for reproducibility; change the seed to observe different random outcomes
