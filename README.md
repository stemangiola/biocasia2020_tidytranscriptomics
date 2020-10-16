<!-- badges: start -->
[![.github/workflows/basic_checks.yaml](https://github.com/stemangiola/biocasia2020_tidytranscriptomics/workflows/.github/workflows/basic_checks.yaml/badge.svg)](https://github.com/stemangiola/biocasia2020_tidytranscriptomics/actions) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.4087926.svg)](https://doi.org/10.5281/zenodo.4087926) [![Docker](https://github.com/Bioconductor/BioC2020/raw/master/docs/images/docker_icon.png)](https://hub.docker.com/repository/docker/stemangiola/biocasia2020_tidytranscriptomics) 	
<!-- badges: end -->

# Introduction to Tidy Transcriptomics
<p float="left">
<img height="100" alt="biocasia2020" src="man/figures/biocasia_logo.png"/> 
<img height="100" alt="tidybulk" src="https://github.com/Bioconductor/BiocStickers/blob/master/tidybulk/tidybulk.png?raw=true"/>
</p>

## Instructor names and contact information

* Maria Doyle <Maria.Doyle at petermac.org>  
* Stefano Mangiola <mangiola.s at wehi.edu.au>

## Syllabus

Material [web page](https://stemangiola.github.io/biocasia2020_tidytranscriptomics/articles/tidytranscriptomics.html).

This material was created for the [BioC Asia 2020 conference](https://biocasia2020.bioconductor.org/) workshop but it can also be used for self-learning.

More details on the workshop are below.

## Workshop package installation 

This is necessary in order to reproduce the code shown in the workshop. The workshop is designed for R `4.0` and can be installed using one of the two ways below.

### Via Docker image

If you're familiar with [Docker](https://docs.docker.com/get-docker/) you could use the Docker image which has all the software pre-configured to the correct versions.

```
docker run -e PASSWORD=abc -p 8787:8787 stemangiola/biocasia2020_tidytranscriptomics:biocasia2020
```

Once running, navigate to <http://localhost:8787/> and then login with
`Username:rstudio` and `Password:abc`.

You should see the Rmarkdown file with all the workshop code which you can run.

### Via GitHub

Alternatively, you could install the workshop using the commands below in R `4.0`.

```
# Install same versions used in the workshop
#install.packages('remotes')
remotes::install_github(c("stemangiola/tidybulk@v1.1.8", "stemangiola/tidySCE@v0.99.2", "stemangiola/tidyHeatmap@v1.1.5"))

# Install workshop package
remotes::install_github("stemangiola/biocasia2020_tidytranscriptomics", build_vignettes = TRUE)

# To view vignettes
library(biocasia2020tidytranscriptomics)
browseVignettes("biocasia2020tidytranscriptomics")
```

To run the code, you could then copy and paste the code from the workshop vignette or [R markdown file](https://raw.githubusercontent.com/stemangiola/biocasia2020_tidytranscriptomics/master/vignettes/tidytranscriptomics.Rmd) into a new R Markdown file on your computer.

## Workshop Description

This workshop will present how to perform analysis of RNA sequencing data following the tidy data paradigm. The tidy data paradigm provides a standard way to organise data values within a dataset, where each variable is a column, each observation is a row, and data is manipulated using an easy-to-understand vocabulary. Most importantly, the data structure remains consistent across manipulation and analysis functions.

This can be achieved for RNA sequencing data with the [tidybulk](https://stemangiola.github.io/tidybulk/), [tidySCE](https://stemangiola.github.io/tidySCE/),  [tidyHeatmap](https://stemangiola.github.io/tidyHeatmap/) and [tidyverse](https://www.tidyverse.org/) packages. The tidybulk package provides a tidy data structure and a modular framework for bulk transcriptional analyses, the tidySCE package provides similar for single-cell transcriptional analyses, and tidyHeatmap provides a tidy implementation of ComplexHeatmap. These packages are part of the tidytranscriptomics suite that introduces a tidy approach to RNA sequencing data.

### Pre-requisites

* Basic knowledge of RStudio
* Familiarity with tidyverse syntax

Recommended Background Reading
[Introduction to R for Biologists](https://melbournebioinformatics.github.io/r-intro-biologists/intro_r_biologists.html)

### Workshop Participation

The workshop format is a 55 min session consisting of hands-on demos with Q&A.

### _R_ / _Bioconductor_ packages used

* tidyverse
* tidybulk
* tidySCE
* tidyHeatmap
* limma
* edgeR
* DESeq2
* SummarizedExperiment
* SingleCellExperiment
* scater
* scran
* SingleR
* igraph
* airway
* org.Hs.eg.db
* dittoSeq
* ggrepel
* GGally
* plotly


### Time outline

Rough guide

| Activity                                              | Time |
|-------------------------------------------------------|------|
| Part 1 Bulk RNA-seq with tidybulk                     | 25m  |
| Part 2 Single-cell RNA-seq with tidySCE               | 30m  |
| Total                                                 | 55m  |

### Workshop goals and objectives

In exploring and analysing RNA sequencing data, there are a number of key concepts, such as filtering, scaling, dimensionality reduction, hypothesis testing, clustering and visualisation, that need to be understood. These concepts can be intuitively explained to new users, however, (i) the use of a heterogeneous vocabulary and jargon by methodologies/algorithms/packages, (ii) the complexity of data wrangling, and (iii) the coding burden, impede effective learning of the statistics and biology underlying an informed RNA sequencing analysis.

The tidytranscriptomics approach to RNA sequencing data analysis abstracts out the coding-related complexity and provides tools that use an intuitive and jargon-free vocabulary, enabling focus on the statistical and biological challenges.

#### Learning goals

* To understand the key concepts and steps of RNA sequencing data analysis
* To approach data representation and analysis though a tidy data paradigm, integrating tidyverse with tidybulk, tidySCE and tidyHeatmap.

#### Learning objectives

* Recall the key concepts of RNA sequencing data analysis
* Apply the concepts to publicly available data
* Create plots that summarise the information content of the data and analysis results
