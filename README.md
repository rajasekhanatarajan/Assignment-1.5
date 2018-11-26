# Assignment-1.5

Create an m x n matrix with replicate(m, rnorm(n)) with m=10 column vectors of n=10 elements each,

constructed with rnorm(n), which creates random normal numbers.

Then we transform it into a dataframe (thus 10 observations of 10 variables) and perform an algebraic

operation on each element using a nested for loop: at each iteration, every element referred by the two

indexes is incremented by a sinusoidal function, compare the vectorized and non-vectorized form of creating

the solution and report the system time differences.

ans:

Create a m x n matrix (of m rows and n columns)
mymat <- matrix(nrow=30, ncol=30)

For each row and for each column, assign values based on position: product of two indexes
for(i in 1:dim(mymat)[1]) { for(j in 1:dim(mymat)[2]) { mymat[i,j] = i*j } }

Just show the upper left 10x10 chunk
mymat[1:10, 1:10]

set.seed(42)

m=10

n=10

mymat <- replicate(m, rnorm(n))

mydframe <- data.frame(mymat)

for (i in 1:m) {

for (j in 1:n) {

 mydframe[i,j]<-mydframe[i,j] + 10*sin(0.75*pi)

 print(mydframe)
}

}
