[![Build Status](https://travis-ci.org/Marcello-Sega/pytim.svg?branch=master)](https://travis-ci.org/Marcello-Sega/pytim)
[![GitHub tags](https://img.shields.io/github/tag/Marcello-Sega/pytim.svg)](https://github.com/Marcello-Sega/pytim/)
[![GitHub issues](https://img.shields.io/github/issues/Marcello-Sega/pytim.svg)](https://github.com/Marcello-Sega/pytim/issues)
[![codecov](https://codecov.io/gh/Marcello-Sega/pytim/branch/master/graph/badge.svg)](https://codecov.io/gh/Marcello-Sega/pytim)
[![Code Issues](https://www.quantifiedcode.com/api/v1/project/51f51927f0f3478ba65d5647dc4723a4/badge.svg)](https://www.quantifiedcode.com/app/project/51f51927f0f3478ba65d5647dc4723a4)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/5f3f2e7be75b46c1a6e4a3d44e3bb900)](https://www.codacy.com/app/Marcello-Sega/pytim?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=Marcello-Sega/pytim&amp;utm_campaign=Badge_Grade)
[![Code Climate](https://codeclimate.com/github/Marcello-Sega/pytim/badges/gpa.svg)](https://codeclimate.com/github/Marcello-Sega/pytim)

<sub>**Disclaimer**: Pytim is in **beta-stage** right now and while a systematic testing system has been set up, this has not yet total coverage. The interface has almost converged to its final form, but changes could still be introduced. In the next period we will roll out more examples and, still, some new features. If you try this software out and have some suggestions, remarks, or bugfixes, feel free to comment here on github and/or make a pull request. </sub>

# A Quick Intro

<img src="https://marcello-sega.github.io/pytim/_images/micelle_cut.png" width="380" align="right" style="z-index:999;">

Have a look at some jupyter notebooks:

1. [An introduction to Pytim](https://github.com/Marcello-Sega/pytim/blob/master/notebooks/An%20introduction%20to%20Pytim.ipynb) 
2. [The Willard-Chandler method]( https://github.com/Marcello-Sega/pytim/blob/master/notebooks/Willard-Chandler%20and%20Cube%20format.ipynb)

Browse the examples in the online manual:

3. [Pytim Online Manual](https://marcello-sega.github.io/pytim/quick.html)

# What is Pytim?

[Pytim](https://marcello-sega.github.io/pytim/) is a cross-platform python implementation of several methods for the detection of fluid interfaces in molecular simulations. So far the following methods have been implemented:

* ITIM
* GITIM 
* Willard Chandler
* Chacon Tarazona
* DBSCAN filtering

Pytim relies on the [MDAnalysis](http://www.mdanalysis.org/)
package for reading/writing trajectories, and work therefore seamlessly for a number of popular trajectory formats, including:  
* GROMACS
* CHARMM/NAMD
* LAMMPS
* AMBER
* DL_Poly

as well as common structure file formats such as XYZ or PDB (have a look at the [complete list](https://pythonhosted.org/MDAnalysis/documentation_pages/coordinates/init.html#id1))

# Show me an example usage, now! 

Ok, ok ... have a look below: the pytim part of the notebook is actually all enclosed in cells [1] and [2]. Cells from [3] to [6] are for visualization. This example is about computing molecular layers of a flat interface:

<img src="https://marcello-sega.github.io/pytim/_images/notebook2.png" width="auto" align="center" style="z-index:999;">

# What if the interface is not flat? 

You could use GITIM, or the Willard-Chandler method, look here: 

<img src="https://marcello-sega.github.io/pytim/_images/notebook1.png" width="auto" align="center" style="z-index:999;">


# How to install the package and the documentation? 

## From the PyPI

this will install the latest release present on the Python Package Index:

```
pip install --user --upgrade pytim
```

## From Github
1. Make sure you have an up-to-date version of cython, numpy, scipy and MDAnalysis:

``` 
pip install --user --upgrade cython numpy scipy MDAnalysis
```

2. Download and install pytim

```
git clone https://github.com/Marcello-Sega/pytim.git
cd pytim
python setup.py install --user
```

# Trouble installing ? 

Some of the most common issues are the following:

**Problem**: The system does not let me write (even using `sudo`) some files

**Solution**: You're most likely running under a recent version of OS-X. Always install packages as user (`pip install <package> --user`

**Problem**: cKDTree complains about the `boxsize` parameter

**Solution**: the version of `scipy` must be >= 0.18


**Problem**: Even though I've upgraded `scipy`, I keep getting problems about `boxsize`

**Solution**: You should tell python where to find packages by setting the variable `$PYTHONPATH` 

**Problem**: some error message mentioning `... file was built for x86_64 which is not the architecture being linked (i386)`

**Solution**: use `export ARCHFLAGS='-arch x86_64'` before installing



# OK, but what is ITIM / GITIM more in detail?  
<img src="https://raw.githubusercontent.com/Marcello-Sega/gitim/ITIM/media/soot1small.png" width="180" align="right" style="z-index:999;">

**ITIM** and **GITIM** are two algorithms for the identification
of interfacial molecules or atoms.

ITIM has been designed for planar interfaces while GITIM is free from any geometrical constraints and can
be used to analyze interfacial properties of surfaces with arbitrary
shapes.


---------------------------

# References

We plan to submit soon a manuscript to report on the features/improvements of pytim with respect to the previous available code. In the meanwhile, if you use pytim, please cite this web page, and read and cite the papers corresponding to the method you are using:


[M. Sega, S. S. Kantorovich P. Jedlovszky and M. Jorge, _J. Chem. Phys._ **138**, 044110 (2013)](http://dx.doi.org/10.1063/1.4776196) The generalized identification of truly interfacial molecules (ITIM) algorithm for nonplanar interfaces.

[L. B. Pártay, G. Hantal, P. Jedlovszky, Á. Vincze and G. Horvai, _J. Comp. Chem._ **29**, 945 (2008)](http://dx.doi.org/10.1002/jcc.20852) A new method for determining the interfacial molecules and characterizing the surface roughness in computer simulations. Application to the liquid–vapor interface of water

[E. Chacón, P. Tarazona, Phys. Rev. Lett. **91**, 166103 (2003)](http://dx.doi.org/10.1103/PhysRevLett.91.166103) Intrinsic profiles beyond the capillary wave theory: A Monte Carlo study.

[A. P. Willard, D. Chandler, J. Phys. Chem. B **114**,1954 (2010)](http://dx.doi.org/10.1021/jp909219k) Instantaneous Liquid Interfaces

