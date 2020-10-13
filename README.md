# lodToolkit
- level-of-details toolkit(LTK)

## App
### pointcloudToLod
- Convert point cloud in *ply/las/laz/xyz* format to *osgb/[3mx](https://docs.bentley.com/LiveContent/web/ContextCapture%20Help-v9/en/GUID-CED0ABE6-2EE3-458D-9810-D87EC3C521BD.html)* lod tree, so that the point cloud could be loaded instantly.
> This program could handle extremely large point cloud as *ply/las/laz/xyz* file is streaming to the convertor.

### meshToLod
- Convert mesh in *obj* format to *osgb/[3mx](https://docs.bentley.com/LiveContent/web/ContextCapture%20Help-v9/en/GUID-CED0ABE6-2EE3-458D-9810-D87EC3C521BD.html)* lod tree, so that the mesh could be loaded instantly.
> This program only support *obj* format mesh with group info, each group will be a tile in the lod tree.

### osgbTo3mx
- Convert *osgb* lod tree to Bentley ContextCapture *[3mx](https://docs.bentley.com/LiveContent/web/ContextCapture%20Help-v9/en/GUID-CED0ABE6-2EE3-458D-9810-D87EC3C521BD.html)* tree.

#### How to use
```
osgbTo3mx.exe --input <DIR> --output <DIR>
	-i, --input <DIR> 
	-o, --output <DIR> 
```

#### Example
```
osgbTo3mx.exe -i E:\Data\Test -o E:\Data\Test_3mx
```

#### The input dir should look like this
```
--metadata.xml

--Data\Tile_000_000\Tile_000_000.osgb

```

## Thirdparty (source codes included for convenience):
- [LASzip](https://github.com/LASzip/LASzip)
- [openCTM-1.0.3](http://openctm.sourceforge.net/)
- [cJsonObject-1.2](https://github.com/Bwar/CJsonObject)
- PlyIO

> Recommend to use OpenSceneGraph 3.4.X, because the *osgb* file generated by 3.6.X may NOT be correctly parsed by lower version of OpenSceneGraph
