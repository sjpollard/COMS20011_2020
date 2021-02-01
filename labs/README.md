# COMS20011_2020 Labs

The labs are all Jupyter Notebooks.  Please get set up with them as soon as possible: I've left Lab 1 up to allow you to test.

There are two basic options: remotely logging in to a lab machine or locally installing Python (not supported).

## Remote access to MVB machines

* Option 1 - First, follow these instructions to set up the [VPN](https://uob.sharepoint.com/sites/itservices/SitePages/vpn-connect.aspx). Then, follow these guidelines provided by IT Services to set up a [Linux Remote Desktop](https://uob.sharepoint.com/sites/itservices/SitePages/fits-engineering-linux-x2go.aspx)

* Option 2 (advanced) - If you are running an X server already (i.e. because you're running Linux locally), then open a shell on your machine, and type this command: 
```
ssh -X -J youruserid@seis.bris.ac.uk youruserid@rd-mvb-linuxlab.bristol.ac.uk
```
## SSH Port forwarding for Option 2.
This option will remove latency issues from the graphical interface of option 2.

Instead of rendering Jupyter Notebook on the lab machines, you can render it on a browser of your local machine. This will remove most latency issues. To do this you need to forward the port used by Juypter Notebook to a port on your local machine.

Steps below show how to map ports using ssh and to render Juypter Notebook on your local machine:

1. Map a port on your machine to a free port on the lab machines (e.g. 7373)
       ```ssh -L 6006:localhost:7373 -J user@seis.bris.ac.uk user@rd-mvb-linuxlab.bristol.ac.uk```
2. Run jupyter notebook on the specified port 7373
      ```/opt/anaconda3-4.4.0/bin/jupyter notebook --no-browser --port 7373```
3. Open localhost:6006 in a web browser on your local machine and enter the token provided by Jupyter Notebook.

## Locally installing Anaconda

*This is not supported!*

Follow instructions in:
[https://www.anaconda.com/products/individual](https://www.anaconda.com/products/individual)

## Starting a Notebook on the lab machines:
Open a terminal, and enter:
```
/opt/anaconda3-4.4.0/bin/jupyter notebook
```
Jupyter should automatically open a webpage. If not, open your favourite web browser and go to: localhost:8888/notebooks.
