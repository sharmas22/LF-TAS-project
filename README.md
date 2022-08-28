# LF-TAS-project
This repository contains the scripts required to fit the lymphatic filariasis transmission model, EPIFIL, to site-specific conditions as it pertains to the manuscript:

Predicting lymphatic filariasis elimination in data-limited settings: a computational framework for combining data generation and model discovery

Swarnali Sharma*, Morgan E. Smith, Edwin Michael

*swarnali.sharma87@gmail.com

Basic workflow:

Define details of baseline transmission conditions and intervention details to simulate. These details can either be based on observed data or proposed scenarios. Details should be defined in "baseline_data_Dozanso.m", "baseline_data_IND.m", "baseline_data_Missasso.m", "baseline_data_Nigeria.m", "baseline_data_PNG.m"  and "baseline_data_SSA.m". .

First the model must be calibrated to the baseline conditions defined in the previous step. To do this, run the file "Main_ToRunBaselineFitting_Dozanso.m", "Main_ToRunBaselineFitting_IND.m", "Main_ToRunBaselineFitting_Kirare.m", "Main_ToRunBaselineFitting_Missasso.m", "Main_ToRunBaselineFitting_NIG.m" and "Main_ToRunBaselineFitting_PNG.m". This will select a set of best-fitting parameter vectors that reproduce the defined baseline conditions for use in subsequent simulations. The parameter vectors, along with baseline estimates of age-stratified infection prevalence and other key output variables, will be saved in a .mat file (one for each site modeled) called "ParamVectors{SiteName}.mat". These files will be accessed by other functions in Interventions.

To simulate interventions over time using the parameter vectors selected, by the BaselineFitting or Hindcasting procedures above, run the file "Main_ToRunIntv_elim_6to7.m" (for 6 to 7 years old population), "Main_ToRunIntv_elim_40to69.m" (for 40 to 69 years old population), "Main_ToRunIntv_elim_EP_new.m" (for all age group), "Main_ToRunIntv_elim_WHO_6to7.m" (for 6 to 7 years old population who WHO threshold), "Main_ToRunIntv_elim_40to69.m" (for 40 to 69 years old population with WHO threshold). Results of the intervention simulation will be saved in a .mat file one for each site modeled). The outputs stored here can be used in further analyses.
