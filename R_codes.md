```
#Merge files by column

m <- merge(x=data1, y=data2, by.x='column in data1', by.y='column in data2')
```
```
#View levels and amount in each level of a column 

table(data$column)
```
```
#Create a positive definite matrix 

Posdef <- function (n, ev = runif(n, 0, 10))
{
   Z <- matrix(ncol=n, rnorm(n^2))
   decomp <- qr(Z)
   Q <- qr.Q(decomp)
   R <- qr.R(decomp)
   d <- diag(R)
   ph <- d / abs(d)
   O <- Q %*% diag(ph)
   Z <- t(O) %*% diag(ev) %*% O
   return(Z)
}

pdmat <- Posdef(n=2, ev=1:2)
#eigen(pdmat)$val

pdmat
```