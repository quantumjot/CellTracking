# CellTracking

*Please note, this is just a landing page for our cell tracking software projects*

The cell tracking pipeline consists of several libraries:
+ BayesianTracker
+ Sequitr
+ Sequitr server
+ Neighbourhood analysis and Chessplots (https://github.com/DGradeci/Chessplots)

[![conv-net-output](http://lowe.cs.ucl.ac.uk/images/segmentation.png)]()  
*Example of segmenting and localizing cells in low contrast microscopy images*

For more information see: http://lowe.cs.ucl.ac.uk/

---

### Launching the server

We are currently using TensorFlow v1.8.

On the first run, you can either manually create a 'server.config' file or run:

```bash
$ python server.py --setup
```

This will execute the auto configuration of the server, creating a list of TF compatible GPU and CPU compute devices.  The server can then be started using the following command:

```bash
$ python server.py
```

The following (optional) flags can be used to specify how the server instance is configured.

```
usage: server.py [-h] [--jobdir JOBDIR] [--logdir LOGDIR]
                 [--gpus [{0,1,2,3} [{0,1,2,3} ...]]] [--local] [--setup]

Sequitr server process

optional arguments:
  -h, --help            show this help message and exit
  --jobdir JOBDIR       Path to job directory
  --logdir LOGDIR       Path to log directory
  --gpus [{0,1,2,3} [{0,1,2,3} ...]]
                        Specify the gpus which can be used for processing
  --local               Running a local server only. Prevents server pinging.
  --setup               Runs the setup configuration to determine hardware
                        specs, and generate the config file. On server
                        restart, the config will persist.
```
