# Principal Component Analysis
When the number of features or dimensions in the data increases, it makes the training extremely
slow, the Principal Component Analysis (PCA) technique is used to reduce the dimension of the
data while keeping the information of the original features as close as possible. In a nutshell, this
is what PCA is all about: Finding the directions of maximum variance in high-dimensional data
and project it onto a smaller dimensional subspace while retaining most of the information.
Often, the desired goal is to reduce the dimensions of a 𝑑 -dimensional dataset by projecting it
onto a ( l )-dimensional subspace (where l <𝑑 ) in order to increase the computational efficiency
while retaining most of the information. An important question is "what is the size of l that
represents the data 'well'?"

Later, we will compute eigenvectors (the principal components) of a dataset and collect them in a
matrix. Each of those eigenvectors is associated with an eigenvalue which can be interpreted as
the "length" or "magnitude" of the corresponding eigenvector.
In this assignment, we performed Principal Component Analysis (PCA) on 32D Bag of Visual
Words (BoVW) representation for scene images. In each class we had 50 images for training and
50 images for testing. In assignment 2, we were unable to build GMM for mixtures >= 2, on this
BoVW features due to non-convergence of EM algorithm. This was due to curse of
dimensionality problem.

Here we reduce the dimension of the BoVW features using PCA. The GMM was built on this
reduced dimensional feature. Log Likelihood graphs for l = 1 is shown for all mixture
components. Beyond that, Confusion matrix for different number of principal components and
GMM mixtures are plotted.

Summary of the PCA approach performed in this assignment:
1. Take all the training examples including all classes
2. Compute the Covariance Matrix
3. Perform Eigen analysis to obtain ‘d’ eigenvalues and the corresponding eigenvectors
4. Choose ‘l’ eigenvectors corresponding to ‘l’ leading eigenvalues (significant eigenvalues)
5. Project each of the y n = x n - mu (mean subtracted data for mathematical ease) on to the ‘l’
eigenvalues to get ‘l’ principal components.
6. Perform GMM on the reduced data and compute the Performance matrix.
