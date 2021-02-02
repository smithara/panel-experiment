# panel-experiment

The `Dockerfile` specifies the environment based on [`pangeo/pangeo-notebook`](https://github.com/pangeo-data/pangeo-docker-images) (see the [package list](https://github.com/pangeo-data/pangeo-docker-images/blob/master/pangeo-notebook/packages.txt) for what it contains). To build the image, run:
```
docker build -t panel-experiment .
```

Then launch a JupyterLab with:
```
docker run -it --rm -p 8888:8888 -v "$(pwd)":/home/jovyan panel-experiment jupyter lab --ip 0.0.0.0

```

Or serve a notebook containing Panel code directly:
```
docker run -it --rm -p 5006:5006 -v "$(pwd)":/home/jovyan panel-experiment panel serve demo.ipynb --allow-websocket-origin=localhost:5006
```