# TensorRT3-errors-2

ERROR: resources.cpp (199) - Cuda Error in gieCudaMalloc: 2

[TensorRT] ERROR: resources.cpp (199) - Cuda Error in gieCudaMalloc: 2

[TensorRT] ERROR: resources.cpp (199) - Cuda Error in gieCudaMalloc: 2

[TensorRT] ERROR: Failed to create engine

raise AssertionError('UFF parsing failed on line {} in statement {}'.format(line, text))
AssertionError: UFF parsing failed on line 214 in statement assert(engine)

I have resolved this amzing problem.
I run this code in anaconda3/lib/python3.6/site-packages/tensorrt/examples/tf_to_trt/tf_to_trt.py

Maybe you should download mnist datasets from: http://yann.lecun.com/exdb/mnist/ 

And put this tars into the new path:/tmp/tensorflow/mnist/input_data/

My GPU is 1060 3G, so to run this code sucessfully,
you must change tf_to_trt.py on line 91 from 
    MAX_WORKSPACE = 1 << 30 to MAX_WORKSPACE = 1 << 10

And it would run sucessfully.
Maybe it would help you.

![image](https://github.com/zhucheng725/TensorRT3-errors-2/blob/master/result.png)
