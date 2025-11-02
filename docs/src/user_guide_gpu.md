### [GPU Acceleration](@id gpu-accelerated-solver)

Clarabel now has a GPU version called `CuClarabel` in Julia, with easy access in Python (via [PythonCall.jl](https://github.com/JuliaPy/PythonCall.jl)) and [CVXPY](https://www.cvxpy.org/).  Since the GPU solver is built on [CUDSS](https://developer.nvidia.com/cudss) sparse linear system solver (accessed via [CUDSS.jl](https://github.com/exanauts/CUDSS.jl)), it is currently supported only on NVIDIA GPUs.

### Use in Julia
You can download the `CuClarabel` branch of `Clarabel.jl` via
```
pkg> add https://github.com/oxfordcontrol/Clarabel.jl/tree/CuClarabel
```
or
```
using Pkg
Pkg.add(url="https://github.com/oxfordcontrol/Clarabel.jl", rev="CuClarabel")
```

Then, you can enable GPU acceleration in Julia by setting the linear subsolver `direct_solve_method` to `:cudss` or `:cudss-mixed`:
| `direct_solve_method` | notes                                                                                                  |
| :---------------------- | :----------------------------------------------------------------------------------------------------- |
| `cudss`                | Enable GPU acceleration of Clarabel (in `Float64`)                                                                                                       |
| `cudss-mixed`             | Enable GPU acceleration of Clarabel with mixed precision  (`Float32` +  `Float64`)                                           |

### Use in Python
Details of how to use in Python can be found [here](https://github.com/oxfordcontrol/Clarabel.jl/tree/CuClarabel). 

