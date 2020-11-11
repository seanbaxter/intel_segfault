# Segfault in glLinkProgram

```
$ clang++-9 segfault.cxx  -lglfw -lgl3w -o segfault -g
$ ./segfault 
Loading shader _Z9vert_mainv from shadertoy.spv
Loading shader _Z9frag_mainI16menger_journey_tLi0EEvv from shadertoy.spv
Segmentation fault (core dumped)
```

The attached .spv file is a Circle C++ shader for the [Menger Journey](https://github.com/seanbaxter/shaders/blob/master/shadertoy/shadertoy.cxx#L684). I've already applied a work-around for this bug:
https://gitlab.freedesktop.org/mesa/mesa/-/issues/3686

This shader passes validation and but segfaults in `glLinkProgram`. The hypercomplex and sphere tracing examples also segfault in `glLinkProgram`.