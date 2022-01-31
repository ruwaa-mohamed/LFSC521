Module I
================

### Downloading Sample Data

For the purpose of only trying the `tidyverse` R package, sample data of
**PheWAS of GWAS Catalog of SNPs** was downloaded from **eMERGE**
databases. The downloaded data can be found here:

<https://phewascatalog.org/files/phewas-catalog.csv.zip>.

The downloaded file was unzipped to get the CSV file.

### Importing the `tidyverse` Library

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.1 ──

    ## ✓ ggplot2 3.3.5     ✓ purrr   0.3.4
    ## ✓ tibble  3.1.6     ✓ dplyr   1.0.7
    ## ✓ tidyr   1.1.4     ✓ stringr 1.4.0
    ## ✓ readr   2.1.1     ✓ forcats 0.5.1

    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

### Load the Data

``` r
df <- read.csv("phewas-catalog.csv")
View(head(df))
```

``` r
colnames(df)
```

    ## [1] "chromosome"        "snp"               "phewas.phenotype" 
    ## [4] "cases"             "p.value"           "odds.ratio"       
    ## [7] "gene_name"         "phewas.code"       "gwas.associations"

### Data Analysis

(involve split-apply-combine approach)

``` r
str(df)
```

    ## 'data.frame':    215107 obs. of  9 variables:
    ##  $ chromosome       : Factor w/ 2185 levels "1","1 100049785",..: 954 954 1809 1732 954 86 1809 1729 1809 1088 ...
    ##  $ snp              : Factor w/ 3144 levels "rs1000579","rs1000778",..: 1182 1182 507 1039 1182 691 507 982 507 2393 ...
    ##  $ phewas.phenotype : Factor w/ 1354 levels "Abdominal aortic aneurysm",..: 99 386 49 711 383 83 840 711 1201 630 ...
    ##  $ cases            : int  737 1170 2505 40 1566 749 1931 40 2161 46 ...
    ##  $ p.value          : num  5.24e-28 2.41e-26 4.14e-26 3.41e-25 8.03e-24 ...
    ##  $ odds.ratio       : num  2.41 2.11 1.69 12.27 1.84 ...
    ##  $ gene_name        : Factor w/ 1776 levels "AAK1","ABCA1",..: 1624 1624 787 685 1624 320 787 1437 787 1674 ...
    ##  $ phewas.code      : num  290 290 702 275 290 ...
    ##  $ gwas.associations: Factor w/ 754 levels "3-(4-hydroxyphenyl)lactate / Isovalerylcarnitine",..: 40 40 257 425 40 13 257 424 257 599 ...

### Including Some Plots

(include a plot or two made with ggplot2)
