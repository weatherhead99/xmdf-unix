# CMake control file for building the XMDF library
# Copyright (C) 2012 Charlie Sharpsteen
#
# Permission is hereby granted, free of charge, to any person obtaining a copy of
# this software and associated documentation files (the "Software"), to deal in
# the Software without restriction, including without limitation the rights to
# use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
# of the Software, and to permit persons to whom the Software is furnished to do
# so, subject to the following conditions:
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.


# This is a top-level file that sets up dependencies. Building and
# installation of the source code is handled by the CMakeLists.txt file in the
# src subdirectory.

# Will probably work with older versions of CMake, but has not been tested.
# Therefore the minimum version is set to 2.8 but this is a "soft constraint"
# Since this project uses Fortran source code, CMake >= 2.6 is probably a hard
# constraint as that is when Fortran support was finalized in CMake.
CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
PROJECT( XMDF )

# Gather library requirements-- these are a Fortran compiler and a recent
# version of the HDF5 library.
ENABLE_LANGUAGE( Fortran )
#SET( HDF5_USE_STATIC_LIBRARIES TRUE )
FIND_PACKAGE( HDF5 1.8.1 REQUIRED )


# Descend into the src directory to build and install the library.
SUBDIRS( src )