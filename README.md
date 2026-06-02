This repo has submodules

* [poncatime.interface](https://github.com/tdhock/poncatime.interface)
* [ponca](https://github.com/poncateam/ponca) -- needs to be at root, not inside `poncatime.interface`

Compile with `R CMD INSTALL poncatime.interface` gives

```
g++ -std=gnu++20  -I"C:/PROGRA~1/R/R-46~1.0/include" -DNDEBUG -I../../ponca/ -I../../ponca/external/eigen/ -I'C:/Users/hoct2726/AppData/Local/R/win-library/4.6/Rcpp/include' -I'C:/Users/hoct2726/AppData/Local/R/win-library/4.6/RcppEigen/include'   -I"C:/rtools45/x86_64-w64-mingw32.static.posix/include"      -O2 -Wall  -mfpmath=sse -msse2 -mstackrealign    -c curvatureEstimation.cpp -o curvatureEstimation.o
curvatureEstimation.cpp:174:19: error: 'DistWeightFunc' does not name a type
```

Whereas I do not get this error when I run R CMD INSTALL on [poncatime](github.com/poncateam/poncatime), why?

```
g++ -std=gnu++20  -I"C:/PROGRA~1/R/R-46~1.0/include" -DNDEBUG -Iexternal/ponca/ -Iexternal/ponca/external/eigen/ -I'C:/Users/hoct2726/AppData/Local/R/win-library/4.6/Rcpp/include' -I'C:/Users/hoct2726/AppData/Local/R/win-library/4.6/RcppEigen/include'   -I"C:/rtools45/x86_64-w64-mingw32.static.posix/include"      -O2 -Wall  -mfpmath=sse -msse2 -mstackrealign    -c curvatureEstimation.cpp -o curvatureEstimation.o
```
