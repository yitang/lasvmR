# lasvmR

lasvmR is a simple wrapper for the LASVM Solver (see http://leon.bottou.org/projects/lasvm). LASVM is basically an online variant of the SMO solver, but citing the original webpage is better:

> LASVM is an approximate SVM solver that uses online approximation. It reaches accuracies similar to that of a real SVM after performing a single sequential pass through the training examples. Further benefits can be achieved using selective sampling techniques to choose which example should be considered next.


# Note

- Though LASVM works internally with sparse data, the interface to R works with dense matrices and vectors. Therefore data has to be copied over. If this bugs you too much, you are free to open an issue and/or propose a solution.

- LASVM is a binary classificator. It does not work with multiclasses and only accepts labels -1, 1.

- Large degree polynomial kernel will kill the computation of the gradient, so LASVM will have floating point issues and crash. Be aware that this might not be the only problem. To see this for yourself, call extra/crash.R or use LASVM directly via 'la_svm -t 1 -s 1 -c 30000 -d 60 crash.data ./crash.model' with crash.R and crash.data from the github repository.



# Changelist

- v0.1.1: Remove memory bug and compile warnings.
- v0.1.0: Initial release.
