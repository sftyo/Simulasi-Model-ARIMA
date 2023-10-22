# ARIMA Model Simulation

## Introduction 

ARIMA Model Simulation was done to understand the error difference between the parameter estimation and the real parameter. On this project, we are going to simulate ARIMA(9,0,5) that were define as:
$$Y_t = \phi_1 Y_{t-1} + \phi_2 Y_{t-2} + \cdots + \phi_9 Y_{t-9} - \theta_1 e_{t-1} - \cdots - \theta_5 e_{t-5} + e_t$$
where $e_i$ have  $N(0,\sigma_{\epsilon}^2)$ distribution.

## Stationarity
Notice the AR equation on the equation above. We define the characteristic equation as:
$$\Phi(x) = 1 - \phi_1x - \phi_2 x^2 - \cdots - \phi_9 x^9$$

The model will achieve stationarity if the roots of the characteristic equation has an absolute value of less than 1. So for this project we define the value of parameter to be:
$$\mathbf{q} = (0.01, 0.02, 0.03, 0.04, 0.05, 0.06, 0.07, 0.08, 0.09,0.65, -0.15, 0.25,0.35, 0.33)$$

## Error
In this simulation, we hope that the more historical data ($T$) we have, the closer will be the estimate parameter to the actual parameter. To calculate the error, will use MSE as our metrics:
$$\text{MSE} = \dfrac{1}{T} \sum_{i = 1}^T|| \mathbf{\hat{q}}_T - \mathbf{q}||^2$$

where for $T \rightarrow \infty$, we hope that the value of MSE will be smaller.

## Conclusion
Based on the plot on the R Markdown files. We see that, in general the more historical data $T$ we have, the smaller the error will be. Althought for some $T$, there are some spikes. 

So we conclude that, the more historical data ($T$) we have, the estimate parameter will be close to the actual parameter (or the error will be smaller)
