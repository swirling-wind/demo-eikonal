0. Could I record the meeting for study review?

1. 
```py
grad_x_ior, grad_y_ior = compute_gradients(IOR)
nx = grad_x_ior[int(y), int(x)]
ny = grad_y_ior[int(y), int(x)]
```


```py
# 1. Plus gradient
new_vx = vx + delta_t * (nx / n)
new_vy = vy + delta_t * (ny / n)
# In concave len test, the wavefront spread slower in black area (lower IOR), which seems incorrect.
```
![picture 0](images/9e8cd90494bd05176d8ae3c48a401193bb24cdcee41b54ab0b8964585cb452d5.png)  
![picture 1](images/77087a8b19a2d5fde323ef7c7f8f2925d022571d1302a91e8355d22ce5512042.png)  


```py
# 2. Minus gradient
new_vx = vx - delta_t * (nx / n)
new_vy = vy - delta_t * (ny / n)
# In slope test, the incidence angle is smaller than refraction angle, with light moving from a lower IOR to a higher IOR, which seems to violate Snell law.
```
![picture 2](images/1264650dc950c042bf9db862e8533204ca12d517ed442d01c3f2a8865750756e.png)  
![picture 3](images/5f69e053ccd2aec8f8d123419a16ce065f272ae9aa8ee05d82e935f9871c51b6.png)  



Which one is correct?


2. Adaptive wavefront refinement
