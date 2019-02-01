# Control of Digitimer DS8R using Python

The files provided here enable control of [Digitimer DS8R][ds8r] current stimulator using Python.
This repo is a Python porting of the [cocoanlab/DS8R_matlab][ds8r-matlab].

[ds8r]: https://digitimer.com/products/human-neurophysiology/peripheral-stimulators-2/ds8/
[ds8r-matlab]: https://github.com/cocoanlab/DS8R_matlab

Files provided here include:

* `D128RProxy.dll`: a 64-bit Windows DLL file provided by Digitimer.
* `DS8R_API.exe`: compiled C++ code to use the DLL file, provided by [cocoanlab/DS8R_matlab][ds8r-matlab].
* `DS8R.py`: `DS8R` class (a controller for DS8R device) is defined.
* `example.py`: (optional) example codes for `DS8R`.

**Important:** Before use, make sure you have installed the original DS8R software, and saved all the files in one folder.

The code for the DS8R control using Python should be implemented using two basic parts as follows (refer to `example.py` for an example use):  

```python
# create an object of the DS8R class and set parameter values.
level1 = DS8R(demand=20,
              pulse_width=1000,
              enabled=1,
              dwell=10,
              mode=1,
              polarity=1,
              source=1,
              recovery=20)

# apply parameters and trigger
level1.run()
```

If you have any questions or comments, please contact Hoyoung Doh: comicroad11@gmail.com
