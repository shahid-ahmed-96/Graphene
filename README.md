# Graphene

## Getting started
The pdf version of the class presentation provides context for the workflow of the project.
Kindly go through it.<br>

## Structure Generation
The file "structure_mono_gra.ipynb" is a set of python commands using ASE that helps to create orthogonal structure for LAMMPS. <br>
These structures, i.e. atomic positions are written to LAMMPS readable files, ".lammps-data".<br>
Refer to how these files look in helpfiles directory provided in Bilayer-Graphene repository.<br>

## Running the script
Ensure availability of the Tersoff file and the structure files at the same location as input script.<br>
The script "in.graph_xg.lmp" is the list of commands that is executed on our system.<br> It first reads the  Tersoff potential and atomic positions data file and then executes the required commands on this system as specified. <br>
For relaxation we use isobaric-isothermal (NPT) ensemble to let the atomic positions relax.  <br>
Next, we switch on the thermostats and allow the system to equilibrate.<br>
Finally in the production run we keep a note of the heat values for the time duration and subsequently apply Fourier's law for obtaining the thermal conductivity. This method is the Non-Equilibrium Molecular Dynamics (NEMD).<br>
We output all the required parameters for calculations.

## Post Processing
The file "Post_processing.ipynb" reads the temperature profile and required parameters. It then calculates the thermal conductivity.<br>
**Important** : In structure creation we use interplane separation of 10A (To ensure no interations between differentlayers as we are concerned only with Basal plane conductivity). However here we are specifying to be 3.35A (interplanar distance as observed experimentally in graphite). 


We should do convergence studies for each parameter. However, it is observed Graphene has a length dependence to upto about 16 $\mu$ m. Due to computational limitations we could go upto only about 1 $\mu$ m. Comparisions with literature shows similar trends. Possible deviations have been mentioned in the pdf file. <br>
