# QGIS Project Management

*@this repository: defines the basic rules of the data organization of a large QGIS project*
- Content:
    - Base Rules
    - Data Management Plan
<hr />


## **Base rules:**
*@these are some standard rules we have to follow and respect to make a reproducable and professional project*
#### **1. Naming/Labeling:**
- contain the map scale
- unique id
- alpha code for map sheed id if exists
- file type
- complete map with legend
- publisher
   - Example below:
            ![Naming Convention](img/naming_conv.png)
            
#### 2. **Storage of the Data:**
- Have always a master and a working folder and keep separate the functional part (scripts)
    - RawData
    - Processed Data
    - Scripts and data
- If possible, use scripts to programatically manage this data

   - Example Directory Tree 

                .Root
                ├── rawData
                |       ├─Culture_data
                |           ├─Block      
                |           ├─Environmental      
                |           ├─Facility      
                |           ├─Field      
                |           ├─Hydrography      
                |           ├─Ortho      
                |           ├─Pipeline      
                |           ├─Topo_Bathymetry      
                |           ├─Topo_BathymetryTransport      
                |       ├─Well_data
                |           ├─dataset1
                |           ├─dataset2
                |       ├─Geo_data
                |       ├─Raster_data
                |       ├─Map_data
                |                   ...
                |                   ..
                |                   .
                |
                ├── processedData
                |       ├─Project1/
                |           ├─Project1.qgz
                |       ├─Project1_db
                |           ├─proc_Culture
                |           ├─proc_Well_data
                |           ├─proc_Geo_data
                |                   ...
                |                   ..
                |                   .
                |
                ├── templates_n_scripts
                |           ├─Queries
                |               ├─Well subsets
                |               ├─Surevey Subsets
                |           ├─Filters
                |           ├─Server_fetch
                |               ├─map_tiles
                |               ├─shape_files
                |           ├─Templates
                |               ├─Symbols
                |               ├─Colorbars
                |               ├─Layouts
                |           ├─Backup
                |               ├─Git Commands
                
                


#### 3. **Versioning**
- Use a version management system, like GitHub or BitBucket
- Find / create a server to store the Raw data geographically separately
- Find / create a server to store your Processed Data

#### 4. **Workflow**
- How to:
    - at every work session fetch/copy data to the rawData folder
    - build in the Project.\
     If:
        - the data is displayed -> fetch every time from rawData
        - the data is modified -> make a copy in Project1_db/subfolder/
        - the process is replicable, write a script
    - automatic backups and local copies by every nth time period
    - commit the changes, and backup the **processedData** to the cloud
- Python:
    - automatic versioning
    - automatic backups and local copies at every couple of day **including the rawData**


#### 5. **Sharing**
- Key helpers to include
    - Metadata
    - Readme files
    - Project specific explanations 
- Share diversification
    - different formats (.shp, .geojson, .csv)
    - to make it able for different applications to use the data

## **Data Management Plan:**
*@if we take forward this planning,depending on the client we can come up with a data protection and security plan*

1. What data will be produced
2. What standards will be used to document the data?
3. How will the data be protected especially restricted data?
4. How will the data be archived and preserved?
5. How will reuse of the data and access to the data be facilitated?
