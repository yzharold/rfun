rfun
----------------------

This utility will not be updated, and is superseded by the [funr](https://github.com/sahilseth/funr) R package. 
You may use: `install.packages("funr");library(funr);setup()` to get started and visit [funr's github page ](https://github.com/sahilseth/funr) for more details.


> r-fun(ction): 
> attempt to make a **fun** cli for R



A small utility which wraps Rscript and provides access to **all** R functions from CLI.


## install:

Download and place in `~/bin`

```
chmod u+x ~/bin/rfun
export PATH=${PATH}:~/bin ## add to .bashrc
```

### install method 2
```
## automatically placed in your bin, and updated when packages gets updated
install.packages('devtools')
devtools::install_github("sahilseth/flowr")
```


## Using a base package

```
## ------- load help for rnorm
rfun rnorm
## ------- sample from rnorm
rfun rnorm n=100
```



## Using a non-base package
### Loading a package automatically by `::`
```
## load help file for knitr
rfun knitr::knit
## OR use
rfun knitr::knit -h
```

### Lets process a Rmd file
```
## get path to an example Rmd file. Assuming we have knitr installed.
## ------- save the filename in a BASH variable rmd
rmd=$(rfun system.file package=knitr ...=examples/knitr-minimal.Rmd)
echo $rmd
## knit this awesome example !
rfun knitr::knit input=$rmd
```
### Features:
- load help file to fetch arguments
- Automatically load package before running using `::`
- Fetch all named parameters of the function and supply shell arguments after converting to the correct type



#### Note:
This was originally built for `flowr` and is a derivative of this file:
[https://github.com/sahilseth/flowr/blob/master/inst/scripts/flowr](https://github.com/sahilseth/flowr/blob/master/inst/scripts/flowr)

I plan to keep these two in sync in case we find any bugs. In fact they are just alias on my systems.

