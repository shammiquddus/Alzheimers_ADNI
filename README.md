# Alzheimers_ADNI
We looked at the contribution of genetic factors in predicting a person's Alzheimer's status at baseline. We worked with two datasets: ADNIMERGE_full, ADNI_Gene_Expression_Profile from University of Southern California Alzheimer's Disease Neuroimaging Initiative (ADNI) database (adni.loni.usc.edu/). 

We expanded the ADNIMERGE dataset and did not take into account the longitudinal aspect of the data. We chose the ADNI2 cohort because gene expression data was collected only for ADNI2 and ADNIGO, thus ADNI1 is a no-go. Since it would be complicated to find variables common to both ADNI2 and ADNIGO, we dropped one or the either without creating any additional bias in the dataset. our final decision is to work on ADNI2 dataset specifically.

### Description of the Datasets
The data encompasses the baseline cognitive statues of a subject and follows his/her progress over a period of mutliple visits. This is the dependent variable 'DX'. The data includes a broad range of predictor categories namely: they are genetic; neuropsychological, everday cognitive and functional tests, MRI to measure changes in brain volume and PET data which looks into brain glucose metabolism. ADNIMERGE_full is the composite data set that pulls on important predictors from all these categories into one snapshot. There are extensive databases of each of these different categories by the different cohorts (ADNI 1, ADNI 2 and ADNIGO) some of which are beyond the compute power our laptops (which was an important cosideration of which dataset we wanted to expand).

### Model Choice
We used regularized logistic CV to build our base model on ADNIMERGE_full and then used PCA and decision tree + Random Forest to improve upon it.
* Baseline model accuracy with the 32 indicators in the original ADNIMERGE_full data: accuracy around 78.6%. Both OVR and MULTINOMIAL gave similar accuracy.
* PCA + Logistic Regression with only gene expression profile: Accuracy of around 65%
* PCA + Logistic Regression with ADNIMERGE + gene expression profile (full data set): Accuracy = 83%
* Random Forest: The best score we got at the depth of 3, is 82.14% 
