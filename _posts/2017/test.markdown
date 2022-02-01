---
layout: post
title: 'Numba series part 2: Custom data types and parallelization'
date: '2017-09-26 15:04'
excerpt: >-
  Here we will focus on how we can use custom data types inside of Numba
  optimized functions as well as parallelization.
comments: true
---

This is the second part of my little series about the Numba library. This time we will take a look on how we can use custom data types inside of functions we like to get optimized by Numba. Out-of-the-box Numba can handle scalars and n-dimensional Numpy arrays as input. Tuples and lists are also supported but lists for example have to be strictly homogeneous (even integers and floats in one list are not supported). As we have seen in the [last part](https://kratzert.github.io/2017/09/21/numba-series-part-1-the-jit-decorator-and-some-more-numba-basics.html) Pythons dictionaries are not supported. I personally like dictonaries and their key-indexing and find them really useful in many occasions. Luckily there is a way, how we can use something similar inside a Numba optimized function: `numpy.dtype()`
