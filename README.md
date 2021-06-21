# NALCN
Files related to statistical clustering of mutations in NALCN reported in Rahrmann et al.

## Requirements
This code runs in python3, using the sklearn, scipy, numpy, and pandas modules, and will run on any operating system supporting python3. The code has been tested on:
- Windows 10
- macOS: Big Sur (11.4)

## Installation
Python dependencies are available via pip, installation taking approximately 5 mins:
```
pip install numpy
pip install scipy
pip install sklearn
pip install pandas
```

## Method
This method uses sampling to calculate an expected distribution for a given cluster distribution in a structure. For example, if there are 50 mutations in a structure, we randomly sample the structure 100,000 times, each time taking a random 50 residue mutations to calculate an expected distribution. We then compare our observed mutational clusters to the expected. Eg. if we find one cluster of 10 and one cluster of 20 mutations (defined as mutations with a distance lower than a certain value from each other - we use the same distance for the observed and expected). If we find that less than 5% of the expected random samples contain similar clusters (in the example case one cluster of >=10 and one of >=20), then the observation is statistically significant.

Depending on the expected distribution size (number of mutations), calculation can take some time (up to an hour on a 4 CPU laptop).

## Reproducible example
See NALCN_mutationalclustering_3D.ipynb for a reproducible example of clustering observed mutations in the cryo structure of NALCN, including structure file and list of real observed mutations.

## License
This project is covered under the MIT license.
