# Findings: Price Drivers in Vehicles Dataset

**Best model:** ElasticNet

**Cross-validated performance** (RMSE lower is better):
- Ridge best RMSE = 5723.56
- Lasso best RMSE = 5775.41
- ElasticNet best RMSE = 5722.86

**Hold-out performance:**
- Test R² = 0.738
- Test RMSE = 6297.24

**Key drivers that INCREASE price (top 12 coefficients):**

                          feature         coef
           model_Sterling Acterra 19744.123442
                      model_sport 14636.199658
                model_sierra 3500 14588.988314
                   model_Hino 268 13863.413081
                     model_cc4500  9732.327305
                         model_gx  9388.174512
model_f-250 super duty lariat cre  9285.340442
           model_Maserati Levante  9065.478456
                 model_fuso fh211  8912.625441
               model_4500 lcf gas  8663.227632
       model_sierra 2500hd denali  7869.275005
                         model_x6  7863.802616

**Key drivers that DECREASE price (bottom 12 coefficients):**

                           feature          coef
              model_crown victoria  -7234.878489
           manufacturer_volkswagen  -7327.405769
           model_outlander phev gt  -7380.570303
                         model_hhr  -7382.751128
                    model_e320 cdi  -7390.383336
                          fuel_gas  -7689.224280
                       fuel_hybrid  -8340.609655
                        model_trax  -8540.581817
                   cylinders_other  -9816.714669
model_SPECIAL FINANCE PROGRAM 2020  -9816.718472
       model_2002 limited 4 runner  -9862.976177
       model_renegade sport suv 4d -10355.300901

**Interpretation:**
- Mileage (odometer) and vehicle age typically **decrease** price.
- Premium manufacturers, specific models/trims, and certain transmission/fuel types may **increase** price.

**Recommendations:**
- Use model outputs to set pricing bands by age/mileage and adjust for manufacturer/model premiums.
- Review listings with unusually low/high predictions for potential data quality issues or outliers.

**Next steps:**
- Add features: trim level, engine size, options, accident history, and geographic demand.
- Try tree-based models (RandomForest, XGBoost) and SHAP for non-linear effects.
