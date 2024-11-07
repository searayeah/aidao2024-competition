# AIDAO 2024

- Consists of online qualifiers and offline main event
- Online qualifiers has two tasks: Tabular data clustering and 3D images classification
- [Main competition website](https://education.yandex.ru/aidao)
- [Qualification contest](https://contest.yandex.com/contest/68727)
- [Data and baselines](https://github.com/atolstikov/aidao24)

> [First place solution from some students](https://github.com/incllude/AIDAO24)

## Some thoughts and links related to qualifiers' tasks

### Task 1

- Task 1 involves clustering fMRI brain data, which includes 320 brain scans from various conditions belonging to 20 individuals.
- Each scan consists of a set of short blood oxygen level time series corresponding to specific brain regions.
- A significant challenge is that the brain regions differ among various scanners (atlases or regions of interest (ROIs)). The data contains two types of brain parcellations, each with varying value ranges and dimensions.
- The Pearson correlation between all pairs of time series for each brain region serves as an effective embedding for each scan. In the literature, this correlation matrix is often referred to as the "human brain fingerprint".
- Utilization of this correlation makes it possible to achieve good metric values on scanner-split datasets.
- However, I am unsure how to unify or convert these correlations into a single embedding dimension that would make sense and enable cross-scanner clustering.
- UMAP is highly effective for reducing the number of dimensions and visualizing data. I used it to ensure that the embedding vectors from different atlases have the same shape.
- As I mentioned, even when the vectors are of the same shape, they do not merge together effectively across different atlases.

#### Some links for Task 1 I found useful

- [Nilearn](https://nilearn.github.io/stable/index.html)
- [GitHub - dadashkarimi/carot: Cross Atlas Remapping via Optimal Transport](https://github.com/dadashkarimi/carot)
- [Functional connectome fingerprinting across the lifespan | Network Neuroscience | MIT Press](https://direct.mit.edu/netn/article/7/3/1206/115891/Functional-connectome-fingerprinting-across-the)
- [Functional connectome fingerprinting: identifying individuals using patterns of brain connectivity - PubMed](https://pubmed.ncbi.nlm.nih.gov/26457551/)
- [Sci-Hub | Functional connectome fingerprinting: identifying individuals using patterns of brain connectivity. Nature Neuroscience, 18(11), 1664–1671 | 10.1038/nn.4135](https://sci-hub.ru/https://doi.org/10.1038/nn.4135)
- [ada_report.pdf](https://yjchoe.github.io/papers/ada_report.pdf)
- [Genetic fingerprinting with heritable phenotypes of the resting-state brain network topology | Communications Biology](https://www.nature.com/articles/s42003-024-06807-0#Abs1)
- [Site Unreachable](https://www.jneurosci.org/content/42/3/377)
- [Functional connectome fingerprinting: Identifying individuals based on patterns of brain connectivity - PMC](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5008686/)
- [Discovering individual fingerprints in resting‐state functional connectivity using deep neural networks - PMC](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10789221/)
- [Functional connectome fingerprinting using shallow feedforward neural networks | PNAS](https://www.pnas.org/doi/10.1073/pnas.2021852118)
