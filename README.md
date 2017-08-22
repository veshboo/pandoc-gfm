Howto **pandoc markdown with latex contents** in github project, especially serving it as README.md

-   Write README.pandoc.md
-   Publish as README.md (github flavored markdown + webtex)
-   Use following command to convert (incorporate to build script or commit hook will be nice)<br/>

    ``` shell
    pandoc -t markdown_github --webtex README.pandoc.md -o README.md
    ```

test document \_\_\_

Machine Learning Lecture by Andrew Ng on Coursera
=================================================

Week 1
------

Introduction

-   What is Machine Learning?
-   Supervised Learning
-   Unsupervised Learning

Linear Regression with One Variable

-   Model (Hypothesis)
-   Cost Function
-   Gradient Descent

Week 2
------

Linear Regression with Multiple Variable

-   Multiple Features
-   Feature Scaling
-   Learning Rate
-   Features and Polymomial Regression
-   Computing Parameters Analytically - Normal Equation

Week 3
------

Logistic Regression

-   Classification
-   Logistic Hypothesis
-   Decision Boundary
-   Cost Function
-   Simplified Cost Function and Gradient Descent
-   Advanced Optimization
-   Multiclass Classification - One-vs-all

Regularization

-   The Problem of Overfitting
-   Cost Function
-   Regularized Linear Regression

Week 4
------

Neural Networks: Representation

-   Non-linear Hypothesis
-   Neurons and the Brain
-   **Model Representation** <br/> ![x = a^{(1)} \\to  g(a^{(1)} \* \\Theta^{(1)}) = a^{(2)} \\to  g(a^{(2)} \* \\Theta^{(2)}) = a^{(3)} \\to  ... \\to  g(a^{(l-1)} \* \\Theta^{(l-1)}) = a^{(l)} = h\_\\Theta(x)](https://latex.codecogs.com/png.latex?x%20%3D%20a%5E%7B%281%29%7D%20%5Cto%20%20g%28a%5E%7B%281%29%7D%20%2A%20%5CTheta%5E%7B%281%29%7D%29%20%3D%20a%5E%7B%282%29%7D%20%5Cto%20%20g%28a%5E%7B%282%29%7D%20%2A%20%5CTheta%5E%7B%282%29%7D%29%20%3D%20a%5E%7B%283%29%7D%20%5Cto%20%20...%20%5Cto%20%20g%28a%5E%7B%28l-1%29%7D%20%2A%20%5CTheta%5E%7B%28l-1%29%7D%29%20%3D%20a%5E%7B%28l%29%7D%20%3D%20h_%5CTheta%28x%29 "x = a^{(1)} \to  g(a^{(1)} * \Theta^{(1)}) = a^{(2)} \to  g(a^{(2)} * \Theta^{(2)}) = a^{(3)} \to  ... \to  g(a^{(l-1)} * \Theta^{(l-1)}) = a^{(l)} = h_\Theta(x)")
-   Example - AND, ! AND !, OR -&gt; XOR
-   Example - Multclass Classification

Week 5
------

Neural Networks: Learning

-   Cost Function - NN multiclass classification
-   Backpropagation

Backpropagation in Practice

-   Unrolling Parameters
-   Gradient Checking
-   Random Initialization
-   Putting It Together

Week 6
------

Advice for Applying Machine Learning

-   ***Not-satisfiying result! -&gt; What to Try Next?***
    -   More training examples
    -   Trying smaller sets of features
    -   Trying additional sets of features
    -   Trying polynomial features
    -   Increasing or decreasing ![\\lambda](https://latex.codecogs.com/png.latex?%5Clambda "\lambda")

Training set / Cross Validation set / Test set

-   Evaluating a hypothesis with a separate test set
    -   Check overfit, generalization
    -   train:test = 70%:30%
-   Model selection with another separate cross validation set
    -   Compare different models (\# of features, degree of polynomial, and ![\\lambda](https://latex.codecogs.com/png.latex?%5Clambda "\lambda"))
    -   train:cv:test = 60%:20%:20%

Model selection details: ![J(\\Theta;\\lambda)](https://latex.codecogs.com/png.latex?J%28%5CTheta%3B%5Clambda%29 "J(\Theta;\lambda)")

-   Number of parameters(![|\\Theta|](https://latex.codecogs.com/png.latex?%7C%5CTheta%7C "|\Theta|")) and Bias/Variance
    -   bias(underfit): ![J\_{CV}(\\theta) \\approx J\_{train}(\\theta) \\gg 0](https://latex.codecogs.com/png.latex?J_%7BCV%7D%28%5Ctheta%29%20%5Capprox%20J_%7Btrain%7D%28%5Ctheta%29%20%5Cgg%200 "J_{CV}(\theta) \approx J_{train}(\theta) \gg 0"), not enough parameters for task
    -   variance(overfit): ![J\_{CV}(\\theta) \\gg J\_{train}(\\theta)](https://latex.codecogs.com/png.latex?J_%7BCV%7D%28%5Ctheta%29%20%5Cgg%20J_%7Btrain%7D%28%5Ctheta%29 "J_{CV}(\theta) \gg J_{train}(\theta)"), too many parameters for task
-   Regualization and Bias/Variance
    -   Remind contribution of ![\\lambda](https://latex.codecogs.com/png.latex?%5Clambda "\lambda") to ![J](https://latex.codecogs.com/png.latex?J "J"), ![J(\\theta) = \\frac{1}{2m} \\sum\_{i=1}^{m} (h\_\\theta (x^{(i)}) - y^{(i)})^2 + \\frac{\\lambda}{2m} \\sum\_{j=1}^{m} \\theta\_j^2](https://latex.codecogs.com/png.latex?J%28%5Ctheta%29%20%3D%20%5Cfrac%7B1%7D%7B2m%7D%20%5Csum_%7Bi%3D1%7D%5E%7Bm%7D%20%28h_%5Ctheta%20%28x%5E%7B%28i%29%7D%29%20-%20y%5E%7B%28i%29%7D%29%5E2%20%2B%20%5Cfrac%7B%5Clambda%7D%7B2m%7D%20%5Csum_%7Bj%3D1%7D%5E%7Bm%7D%20%5Ctheta_j%5E2 "J(\theta) = \frac{1}{2m} \sum_{i=1}^{m} (h_\theta (x^{(i)}) - y^{(i)})^2 + \frac{\lambda}{2m} \sum_{j=1}^{m} \theta_j^2")
    -   ![\\lambda \\approx 0 \\implies \\verb!maybe overfit!](https://latex.codecogs.com/png.latex?%5Clambda%20%5Capprox%200%20%5Cimplies%20%5Cverb%21maybe%20overfit%21 "\lambda \approx 0 \implies \verb!maybe overfit!")
    -   ![\\lambda \\gg 0 \\implies \\verb!maybe less overfit!](https://latex.codecogs.com/png.latex?%5Clambda%20%5Cgg%200%20%5Cimplies%20%5Cverb%21maybe%20less%20overfit%21 "\lambda \gg 0 \implies \verb!maybe less overfit!")
-   Learning Curves, Error x ***training set size***
    -   High bias, low training size: ![J\_{train}(\\Theta)](https://latex.codecogs.com/png.latex?J_%7Btrain%7D%28%5CTheta%29 "J_{train}(\Theta)") low and ![J\_{CV}(\\Theta)](https://latex.codecogs.com/png.latex?J_%7BCV%7D%28%5CTheta%29 "J_{CV}(\Theta)") high
    -   High bias, large training size: both ![J\_{train}(\\Theta)](https://latex.codecogs.com/png.latex?J_%7Btrain%7D%28%5CTheta%29 "J_{train}(\Theta)") and ![J\_{CV}(\\Theta)](https://latex.codecogs.com/png.latex?J_%7BCV%7D%28%5CTheta%29 "J_{CV}(\Theta)") high
    -   High variance, low training size: ![J\_{train}(\\Theta)](https://latex.codecogs.com/png.latex?J_%7Btrain%7D%28%5CTheta%29 "J_{train}(\Theta)") low and ![J\_{CV}(\\Theta)](https://latex.codecogs.com/png.latex?J_%7BCV%7D%28%5CTheta%29 "J_{CV}(\Theta)") high
    -   High variance, large training size: ![J\_{train}(\\Theta)](https://latex.codecogs.com/png.latex?J_%7Btrain%7D%28%5CTheta%29 "J_{train}(\Theta)") OK and ![J\_{CV}(\\Theta)](https://latex.codecogs.com/png.latex?J_%7BCV%7D%28%5CTheta%29 "J_{CV}(\Theta)") **keep decreasing**
-   Summary
    -   Select best combo ![\\Theta](https://latex.codecogs.com/png.latex?%5CTheta "\Theta"), ![\\lambda](https://latex.codecogs.com/png.latex?%5Clambda "\lambda"), and right amount of data by checking ![J\_{CV}](https://latex.codecogs.com/png.latex?J_%7BCV%7D "J_{CV}")
    -   And also check ![J\_{test}](https://latex.codecogs.com/png.latex?J_%7Btest%7D "J_{test}") for good generalization

Machine Learning System Design (with Spam classifier)

-   Prioritizing What to Work On
-   Error Analysis
-   Error Metrics Skewed Classes
-   Precision and Recall trade off

Week 7
------

-   Support Vector Machine

Week 8
------

Unsupervised Learning

-   Clustering
-   K-Means Algorithm
-   Optimization Objective
-   Random Initialization
-   Choosing the Number of Clusters

Dimensionality Reduction

-   Motivation
-   Motivation I: Data Compression
-   Motivation II: Visualization

-   Principal Component Analysis
-   Principal Component Analysis Problem Formulation
-   Principal Component Analysis Problem Algorithm

-   Applying PCA
-   Reconstructin from Compressed Representation
-   Choosing the Number of Principal Components
-   Advice for Applying PCA

Week 9
------

Anomaly Detection

Recommender Systems

Week 10
-------

Large Scale Machine Learning

-   Gradient Descent with Large Datasets
-   Learning with Large Datasets
-   Stochastic Gradient Descent
-   Mini-Batch Gradient Descent
-   Stochastic Gradient Descent Convergence

-   Advanced Topics
-   Online Learning
-   Map Reduce and Data Parallelism

Week 11
-------

Application Example: Photo OCR

-   Photo OCR
-   Problem Description and Pipeline
-   Sliding Windows
-   Getting Lots of Data and Artificial Data
-   Ceiling Analysis: What Part of the Pipeline to Work on Next

Conclusion

-   Summary and Thank You

