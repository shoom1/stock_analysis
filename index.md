---
title       : Stocks Analysis
subtitle    : Simple Shiny App
author      : 
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Simple Stock Analysis App

1. Loads historical prices for a given stock symbol
2. Calculates daily relative returns of stock prices
3. Can show time series of daily returns and histogram of returns distribution
4. Calculates autocorrelations of daily returns

--- .class #id 

## Loading Time Series

Load timeseries of specified stock symbols from yahoo finance using `quantmod` R package. The example below loads time series of Apple Inc. stock history starting 2010-01-01 and ending 2014-10-26. The corresponding plot is shown below.


```r
aapl <- getSymbols("AAPL", auto.assign=FALSE, from='2010-01-01', to='2014-10-26')
```
<img src="assets/fig/unnamed-chunk-3.png" title="plot of chunk unnamed-chunk-3" alt="plot of chunk unnamed-chunk-3" style="display: block; margin: auto;" />

---
## Relative Returns
Relative returns of stock prices time series $\{S_k\}$ are defined as: 
$$r_k = (S_k-S_{k-1})/S_{k-1}$$
The time series and distribution of daily relative returns of Apple Inc. are shown below:

<img src="assets/fig/unnamed-chunk-5.png" title="plot of chunk unnamed-chunk-5" alt="plot of chunk unnamed-chunk-5" style="display: block; margin: auto;" />


---
## Autocorrelations

In order to test whether daily returns are indepentent we can calculate autocorrelation using `acf()` R function.

<img src="assets/fig/unnamed-chunk-6.png" title="plot of chunk unnamed-chunk-6" alt="plot of chunk unnamed-chunk-6" style="display: block; margin: auto;" />

