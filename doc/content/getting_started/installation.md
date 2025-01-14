# Installation

## Step One: Install Conda MOOSE Environment

!style halign=left
In order to install TMAP8, the MOOSE developer environment must be installed. The
installation procedure depends on your operating system, so click on the MOOSE
website link below that corresponds to your operation system/platform and follow
the instructions to the conda installation step named "Cloning MOOSE". Then,
return to this page and continue with Step Two.

- [Linux and MacOS](https://mooseframework.inl.gov/getting_started/installation/conda.html)
- [Windows 10 (experimental)](https://mooseframework.inl.gov/getting_started/installation/windows10.html)

Advanced manual installation instructions for this environment are available
[via the MOOSE website](https://mooseframework.inl.gov/getting_started/installation/index.html).

If an error or other issue is experienced while using the conda environment,
please see [the MOOSE troubleshooting guide for Conda](https://mooseframework.inl.gov/help/troubleshooting.html#condaissues)

## Step Two: Clone TMAP8

!style halign=left
TMAP8 is hosted on [GitHub](https://github.com/idaholab/TMAP8), and should be
cloned directly from there using [git](https://git-scm.com/). As in the MOOSE
directions, it is recommended that users create a directory named "projects" to
put all of your MOOSE-related work.

To clone TMAP8, run the following commands in Terminal:

```bash
mkdir ~/projects
cd ~/projects
git clone https://github.com/idaholab/TMAP8.git
cd TMAP8
git checkout main
```

!alert! note title=TMAP8 branches
This sequence of commands downloads TMAP8 from the GitHub server and checks
out the "main" code branch. There are two code branches available:

- "main", which is the current most-tested version of TMAP8 for general usage, and
- "devel", which is intended for code development (and may be more regularly broken
  as changes occur in TMAP8 and MOOSE).

Developers wishing to add new features should create a new branch for submission
off of the current "devel" branch.
!alert-end!

## Step Three: Build and Test TMAP8

!style halign=left
To compile TMAP8, first make sure that the conda MOOSE environment is activated
(*and be sure to do this any time that a new Terminal window is opened*):

```bash
mamba activate moose
```

Then navigate to the TMAP8 clone directory and download the MOOSE submodule:

```bash
cd ~/projects/TMAP8
git submodule update --init moose
```

!alert note
The copy of MOOSE provided with TMAP8 has been fully tested against the current
TMAP8 version, and is guaranteed to work with all current TMAP8 tests.

Once all dependencies have been downloaded, TMAP8 can be compiled and tested:

```bash
make -j8
./run_tests -j8
```

!alert! note
The `-j8` flag in the above commands signifies the number of processor cores used to
build the code and run the tests. The number in that flag can be changed to the
number of physical and virtual cores on the workstation being used to build TMAP8.
!alert-end!

If TMAP8 is working correctly, all active tests will pass. This indicates that
TMAP8 is ready to be used and further developed.

## Troubleshooting

!style halign=left
If issues are experienced in installation and testing, several resources
are available:

- [TMAP8 Issues Page](https://github.com/idaholab/TMAP8/issues) for TMAP8 bugs or feature requests.
- [TMAP8 Discussion Forum](https://github.com/idaholab/TMAP8/discussions) for TMAP8 issues and questions.
- [MOOSE FAQ page](https://mooseframework.inl.gov/help/faq/index.html) for common MOOSE issues.
- [MOOSE Discussion Forum](https://github.com/idaholab/moose/discussions) for non-TMAP8 issues and questions.

## What next?

!style halign=left
With installation and testing complete, proceed to [using_tmap8.md].
