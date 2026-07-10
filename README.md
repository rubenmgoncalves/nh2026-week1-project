# NeuroHackademy 2026 Week-1 Projects

This repository is a template for the NeuroHackademy 2026 week-1
projects. The goal of the project is to examine data from the
[Reproducible Brain Charts (RBC)](https://reprobrainchart.github.io/) database
and to use any of its data to predict the `p_factor` of a set of participants.
Project details can be found below.


## How to use this repository

This repository is a template for your own analysis of the RBC dataset. Please
[fork this repository](
https://github.com/NeuroHackademy2026/nh2026-week1-project/fork) then clone
your forked copy locally into your JupyterHub environment:

```bash
git clone git@github.com:USERNAME/nh2026-week1-project
```

We encourage all group members to fork the repository (but only one group
member should upload the predicted data and make a pull request at the end;
these steps are documented in the analysis notebook).

Once you have cloned your fork of the repository locally on the JupyterHub you
can open the `analysis.ipynb` notebook in the repository root. This file
contains an example workflow that loads in the surface area of Brodmann Area 1
for each subject, trains a linear regression model to predict the `p_factor`
based on that surface area in the set of training participants, then uses the
trained model to predict the `p_factor` in for the test participants based on
their BA1 surface areas. Feel free to make your own notebook or to modify this
analysis notebook for your project.


## The RBC Database

The RBC database contains many independent datasets; in this project, we will
focus on just one of these datasets, the
[Philadelphia Neurodevelopmental Cohort (PNC)](
https://www.med.upenn.edu/bbl/philadelphianeurodevelopmentalcohort.html).
The data from this dataset have been collected into three GitHub repositories:
* [`ReproBrainChart/PNC_BIDS`](https://github.com/ReproBrainChart/PNC_BIDS)
* [`ReproBrainChart/PNC_FreeSurfer`](
  https://github.com/ReproBrainChart/PNC_FreeSurfer)
* [`ReproBrainChart/PNC_CPAC`](https://github.com/ReproBrainChart/PNC_CPAC)

Although you are welcome to use any data from the dataset to model and predict
the `p_factor`, we encourage you to focus on the data available in the
`PNC_FreeSurfer` repository, as it does not require sophisticated preprocessing
and is fairly easy to model in a short amount of time.

### What is `p_factor`?

The `p_factor` that you are tasked with modeling and predicting is a general
psychopathology factor that has been calculated for each subject. The details
of this calculation are not critical for this project, but more information can
be found in [this RBC publication](https://doi.org/10.1101/2025.02.24.639850).

### Can't we just get the `p_factor` from the dataset?

We have provided two TSV files on the NeuroHackademy JupyterHub:
* `/home/jovyan/shared/data/RBC/train_participants.tsv`
* `/home/jovyan/shared/data/RBC/test_participants.tsv`

The first of these files, `train_participants.tsv` contains a subset of the PNC
participants and various meta-data (including the `p_factor`) for each. The
`test_participants.tsv` file contains the left-out test subjects, and all of
the `p_factor` cells in this data table have been set to `NaN`. Although it is
possible to find and extract the true `p_factor` values for these test
subjects, we encourage you not to do so, or at least not to do so until after
you have generated predictions. (We will provide the `p_factor` data to you
when the projects are completed).
