# May 21, 2018: Synthetic controls


<div align="justify">

### Paper

Abadie A, Diamond A, Hainmueller J. Synthetic Control Methods for Comparative Case Studies: Estimating the Effect of California's Tobacco Control Program. Journal of the American Statistical Association. American Statistical Association; 2010 Jun 1;105(490):493–505. 

### Date

May 21, 2018

### Summary

In their now classic paper, Abadie et al. (2010) describe a method to construct a control population when no such population exists - they call this a "synthetic control". They do so by weighting each potential control by a specific amount, such that all weights add up to one and that the weighted values of covariates and outcome variables are as close to the ones of the intervention group as possible, prior to the intervention. They then take the  post-intervention value of the outcome variable in the synthetic control group and subtract it from the intervention group - this is the causal effect of the intervention on the treated. They test the probability of obtaining such an effect or more extreme under the assumption that no such effect exists using a permutation test, whereby they create synthetic controls and estimate effect sizes for all units involved in creating the initial synthetic control - this they call the placebo trials.

Even though promising, this model does not appear to produce particularly generalizable estimates of effect size because it does not account for intervention group-specific or synthetic control-group specific covariates that may not depend on the intervention but which may modify its effect. Furthermore, it appears to only assume presence of time-invariant covariates with time-varying effects, which is not always a realistic assumption to make. It is also not immediately clear how this method improves on the method of differences-in-differences and what is the impact of error terms on our estimate when (1) the weights do not create a perfect match to the intervention group prior to the intervention and when (2) the amount of time points prior to the intervention is small. Lastly, we wonder to what extent this method is similar to inverse probability of treatment weighting (IPTW).

We could possibly enhance the credibility of this method by using a negative control, such as an outcome that we would not expect to be affected by the intervention, to investigate whether indeed its estimated effect is close to null. We could also use part of the pre-intervention time-points as a validation set to estimate the uncertainty in our predictive ability of the pre-intervention estimate of effect by the synthetic control. Lastly, we could consider using models other than a linear model to estimate the synthetic control, such as those encountered in the machine learning literature, which could create better estimates of the synthetic control.

Synthetic controls can be implemented using the R packages Synth (original package) and gsynth (generalized synthetic controls, where more than one treated units are allowed).

</div>
