# anystep-gradient-descent
A repository to catalogue studying and experimentation on large-step Gradient Descent.

Based on *Any-stepsize Gradient Descent for Separable Data under Fenchel-Young Losses* by Bao et al. (https://arxiv.org/abs/2502.04889), and *Large Stepsize Gradient Descent for Logistic Loss: Non-Monotonicity of the Loss Improves Optimization Efficiency* by Wu et al. (https://arxiv.org/abs/2402.15926).

## Introduction

We're studying the behavior of large step-sizes on Gradient Descent (GD).

GD is one of the most common optimizers in Machine Learning. 

Wu et al. shows that under logistic regression with linearly separable data, GD with large step sizes still converges. Bao et al. extends this finding further. We will start by analyzing the simpler case in Wu et al.'s study.


## Context

Wu et al. considers large GD step-sizes for binary classification with a linear model trained with Logistic Loss.

First, we need to understand what the classic theory says about how GD behaves.

<img src="https://github.com/slamgLuke/anystep-gradient-descent/raw/main/boards/board1.jpg" width="500">

For a $\beta$-smooth function, the descent lemma guarantees convergence if $0 < \eta < \cfrac{2}{\beta}$, where $\eta$ is the GD step-size.

We will study the behavior of large GD step-sizes with the same conditions of Wu et al., which defines the following:
- All data points $x_i$ have a magnitude of at most 1.
- The two classes are linearly separable.
- Labels are defined as $y_i \in \{-1, +1\}$
- There is a unit vector $w^{*}$ and a $\gamma > 0$ such that $\langle y_i x_i, w^{*}\rangle \geq \gamma$ for all $i$

This last point is used to refer to the fact that under an optimal vector $w^{*}$ which separates the data, the closest point to the decision boundary is at distance $\gamma > 0$.
This means that the vector $\frac{w^{*}}{\gamma}$ produces a score $z_i = y_i \langle x_i, \frac{w^{*}}{\gamma}\rangle \geq 1$.


## Loss Landscape

<img src="https://github.com/slamgLuke/anystep-gradient-descent/raw/main/boards/board2.jpg" width="500">

<img src="https://github.com/slamgLuke/anystep-gradient-descent/raw/main/boards/board3.jpg" width="500">

<img src="https://github.com/slamgLuke/anystep-gradient-descent/raw/main/boards/board4.jpg" width="500">

<img src="https://github.com/slamgLuke/anystep-gradient-descent/raw/main/boards/board5.jpg" width="500">
