# Activation Functions

## Overview
Activation functions determine the output of a neuron based on its inputs. They are essential for introducing non-linearity into neural networks, enabling them to learn complex patterns.

## Types of Activation Functions

### Linear Activation Function
- Simply outputs whatever it receives as input (y = x)
- **Limitations**:
  - Cannot perform complex learning
  - Makes multiple layers redundant
  - Not useful for backpropagation
  - Rarely used in practice

### Binary Step Function
- Outputs 0 for negative inputs, 1 for positive inputs
- **Limitations**:
  - Cannot handle multiple classification (binary only)
  - Vertical slopes cause problems with derivatives
  - Not commonly used in modern networks

### Non-Linear Activation Functions
These enable complex mappings and effective learning:

#### Sigmoid/Logistic Function
- Outputs between 0 and 1
- Smooth with well-behaved derivatives
- **Best for**: Problems requiring multiple labels per input
- **Limitations**: Suffers from vanishing gradient problem

#### Hyperbolic Tangent (TanH)
- Outputs between -1 and 1
- Mean centered around zero (preferred over sigmoid)
- **Best for**: Recurrent neural networks
- **Limitations**: Computationally expensive, vanishing gradient issues

#### Rectified Linear Unit (ReLU)
- f(x) = max(0, x)
- **Advantages**:
  - Fast computation
  - Efficient convergence
  - No vertical lines causing calculus problems
- **Limitations**: "Dying ReLU problem" with negative inputs

#### Leaky ReLU
- Adds small negative slope for x < 0
- Solves the dying ReLU problem
- Slope is manually configured

#### Parametric ReLU (PReLU)
- Like Leaky ReLU but negative slope is learned through backpropagation
- More computationally intensive

#### Exponential Linear Unit (ELU)
- Uses exponential function for negative inputs
- Smoother curves preferred by calculus

#### Swish
- Developed by Google
- Benefits very deep networks (40+ layers)

#### Maxout
- Outputs maximum of all inputs
- ReLU is a special case
- Doubles parameters to train, making it expensive

#### Softmax
- Used in output layer for classification problems
- Converts outputs to probabilities for each class
- **Best for**: Single-label classification

## Choosing the Right Activation Function

1. For output layer in classification: Softmax
2. For recurrent neural networks: TanH
3. For most other cases: Start with ReLU
4. If ReLU underperforms: Try Leaky ReLU → PReLU → Maxout
5. For very deep networks (40+ layers): Consider Swish
6. For multi-label classification: Sigmoid​​​​​​​​​​​​​​​​
