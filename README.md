# GEM-ComsolVersion
Interface garfield++ with Comsol Multiphysics

To import the fieldmap from Comsol multiphysics, here is what you should do below:
1. Export "mesh.mphtxt" :
    (1) Open Comsol Multiphysics and navigate to the tab "Model Builder"
    (2) Navigate to Results-Export
    (3) Right Click on Export-Mesh
    (4) Change the "File type" to "*.mphtxt"
    (4) Change the filename to: "mesh.mphtxt"
    (5) Click the button on the upleft corner "Export"
    
2. Export "field.txt":
    (1) Open Comsol Multiphysics and navigate to the tab "Model Builder"
    (2) Navigate to Results-Export
    (3) Right Click on Export-Data
    (4) In the "Expressions" section, click the "+" sign, find: "V-Electrical potential", click on that
    (5) In the "Advanced" section, change the "Resolution" to "Custom" and set the "Lagrange-element node-point order" to 2
    (6) Change the "Filename" to "field.txt" and click on "Export" button
    
3. Write "dielectrics.dat" manually
    Comsol multiphysics seems don't provide us an easy way to export the file format which meet the requirement of garfield++.     So wen have to write it manually.
    The steps are below:
    (1) Create a file named "dielectrics.dat"
    (2) Input the information in this format:
        >> The number of materials. (for example: n)
        >> The relative permittivity of material 0
        >> The relative permittivity of material 1
        >> The relative permittivity of material 2
        ...
        >> The relative permittivity of material n-1
        >> The number of domains in the geometry (for example: m)
        >> 0
        >> The material index of domain 0
        >> 1
        >> The material index of domain 1
        >> 2
        >> The material index of domain 2
        ...
        >> m
        >> The material index of domain m-1
    (3) Save the file.
