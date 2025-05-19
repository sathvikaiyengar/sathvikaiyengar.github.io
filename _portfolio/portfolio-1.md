---
title: "Determining Importance of Features Related to Star Formation in Central and Satellite Galaxies Using Machine Learning"
excerpt: "<div style='display: flex; align-items: center; gap: 20px;'><span>My latest research involves exploring how to best utilize supervised ML models to classify spatially resolved pixels and predict their star formation rate. </span><img src='/images/nasa-galaxy.jpg' width='500' style='margin:0;'/></div>"
collection: portfolio
---

## Key Definitions
<ins>Galaxy quenching:</ins> process in which star formation shuts down in a galaxy <br/>
<ins>Central galaxies:</ins>  largest galaxy in center of halo<br/>
<ins>Satellites galaxies: </ins> smaller galaxies revolving around central galaxies<br/>
<ins>Spaxels:</ins>  spatially resolved pixel containing vast information on a tiny area of the sky<br/>


## Motivations
- Determine the most important parameter for predicting the quenching of galaxies on spatially resolved scales using ML algorithms
- Apply for subsets of the TNG100 galaxy sample including: high- and low- mass centrals, high- and low- mass satellites
- Compare results from TNG100 simulation data to observations from similar papers (see Bluck)

## Data Preprocessing: 
### Annular Binning

## Methods

**Global parameters (galaxy specific):** \
<ins>s_mass:</ins> stellar mass; the total mass of all stellar particles bound to a galaxy; in units of 10^10 M_sun/h<br/>
<ins>BHMass:</ins> mass of the supermassive black hole at the center of a galaxy; in units of 10^10 M_sun/h <br/>
<ins>BH_AGN:</ins> total black hold energy imparted in both quasar (BH_cumQM) and radio mode (BH_cumRM)<br/>
<ins>Mhalo:</ins> total mass of all particles in the FoF halo that the galaxy belongs to; units are 10^10 M_sun/h<br/>
<ins>overdens:</ins>  local galaxy overdensity evaluated at the 5th nearest neighbor<br/>
<ins>bulge:</ins> the F(G, M20) 'bulge statistic' which is a morphology measurement<br/>

**Local parameters (spaxel specific):** \
<ins>avg_gas_mass:</ins> base-10 log of gas mass surface density of the bin <br/>
<ins>avg_s_mass:</ins> base-10 log of the stellar mass surface density of the bin<br/>

**Methodology:**
- Conducting 10 independent runs, utilizing cross validation resulting in 500 model runs
- Separation of training/testing on the galaxy-level to prevent data leakage
- Randomized Search CV utilized for hyperparameter tuning 
    For Random Forest: n_estimators, max_depth, min_samples_split, min_samples_leaf, max_features, bootstrap
    For XGBoost: n_estimators, max_depth, learning_rate, alpha, reg_lambda, scale_pos_weight, min_child_weight
- Utilized ROC curves, AUC/F1 scores to determine model accuracy 


***For Classification, our target variable was whether the spaxel quenched (0) or star-forming (1).***
***For Regression, our target variable was the star-formation rate of the spaxel.***


## Results 
### RF Classification

<!-- <div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: center;">
    <img src="/images/classification-1.png" alt="Classification Result 1" width="45%" style="margin-bottom: 20px;"/>
    <img src="/images/classification-2.png" alt="Classification Result 2" width="45%" style="margin-bottom: 20px;"/>
    <img src="/images/classification-3.png" alt="Classification Result 3" width="45%"/>
    <img src="/images/classification-4.png" alt="Classification Result 4" width="45%"/>
</div> -->


### RF Regression

<!-- <div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: center;">
    <img src="/images/classification-1.png" alt="Classification Result 1" width="45%" style="margin-bottom: 20px;"/>
    <img src="/images/classification-2.png" alt="Classification Result 2" width="45%" style="margin-bottom: 20px;"/>
    <img src="/images/classification-3.png" alt="Classification Result 3" width="45%"/>
    <img src="/images/classification-4.png" alt="Classification Result 4" width="45%"/>
</div> -->

### NN Classification

<!-- <div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: center;">
    <img src="/images/classification-1.png" alt="Classification Result 1" width="45%" style="margin-bottom: 20px;"/>
    <img src="/images/classification-2.png" alt="Classification Result 2" width="45%" style="margin-bottom: 20px;"/>
    <img src="/images/classification-3.png" alt="Classification Result 3" width="45%"/>
    <img src="/images/classification-4.png" alt="Classification Result 4" width="45%"/>
</div> -->


### NN Regression

<!-- <div style="display: flex; flex-wrap: wrap; gap: 20px; justify-content: center;">
    <img src="/images/classification-1.png" alt="Classification Result 1" width="45%" style="margin-bottom: 20px;"/>
    <img src="/images/classification-2.png" alt="Classification Result 2" width="45%" style="margin-bottom: 20px;"/>
    <img src="/images/classification-3.png" alt="Classification Result 3" width="45%"/>
    <img src="/images/classification-4.png" alt="Classification Result 4" width="45%"/>
</div> -->