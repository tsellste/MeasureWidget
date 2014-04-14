MeasureWidget
=============

Measure Widget for use with the ArcGIS Viewer for Flex

04/14/2014 - Compiled for FlexViewer 3.6

08/28/2013 - Fixed problem for calculating area in State Plane feet found by Josh White.  The problem occured when the polygon was passed to the geometry service and the service was returning values in meters.  Changes were made to the widget to be more explicit about the values returned.

08/16/2013 - Compiled for FlexViewer 3.4

05/24/2013 - Compiled for FlexViewer 3.3

01/07/2013 - Updated the download to include updates for the 3.0 version. Updated interface to display the measure form properly. Removed the cumulative total when drawing polyline is complete.

01/04/2013 - Compiled for FlexViewer 3.1.  Fixed area calculation for spatial references other than WGS1984 and Web Mercator. Added functionality to allow for control of measurement text font, color and size. 

11/05/2012 - added cumulative total to display at the end of a polyline being
drawn as suggested by Andrew Edmonds. Also fixed code to properly round segment
measurement lengths. The segment length measurements were previously truncated
instead of being properly rounded.

9/10/2012 - added decimal places to the XML configuration to define how many 
decimal places are displayed on the measurement labels for each different unit 
of measure.  Also added logic to only display a total measurement length when
there is more than one segment in a polyline.


8/7/2012 - Added functionality to calculate measurements when basemap is using
a spatial reference other than web mercator aux sphere. I have tested it with 
our state plane feet projection.

This widget is a modification of the FlexViewer Draw tool.  Our planning
staff at the City of Yakima wanted to have more interactive measurements
than the draw tool provides.  With the draw tool you have to complete the
drawing of a line or polygon and a result will be returned from a geometry
service.  They needed to know the length of the vertex as they were drawing
the line or polygon.

Requirements:
- The ArcGIS Flex API 3.x or greater swc. Download it here:  http://resources.arcgis.com/content/login?destination=content/arcgis-flex-api-download
- Internet access to the ArcGIS Online servers
- Web Server to deploy the application
- Flash Player 11 

To install using the compiled version just copy the folder called Measure
under the Widgets folder, and add this line to your config.xml

if your map units are in meters:
<widget label="Measure" left="60" top="400"
                icon="widgets/Measure/assets/images/i_measure2.png"
                config="widgets/Measure/MeasureWidget.xml"
                url="widgets/Measure/MeasureWidget.swf"/>

if your map units are in feet:
<widget label="Measure" left="60" top="400"
                icon="widgets/Measure/assets/images/i_measure2.png"
                config="widgets/Measure/MeasureWidget_ft.xml"
                url="widgets/Measure/MeasureWidget.swf"/>

For the Source you need to copy the Measure folder to src/widgets

Finalize the install for Uncompiled version:
 - In Flex Builder on the left of the screen is the FlexNavigator tree, right click you Flex Sample Viewer project
   and go to properties
 - In the Properties dialog choose Flex Compiler in the left window.
 - Ensure your Flex SDK Version is 4.6
 - Check Require Flash Player Version under HTML Wrapper and enter 11.0
 - Now Flex Modules in the left window.
 - On the right hand side of the dialog will be an add buton click it
 - browse to src\widgets\Measure and add the MeasureWidget.mxml
 - click ok all the way out.
 - Change the MeasureWidget.xml the top item in the distanceunits tag is the default, which is feet. The default areaunits is square miles.  Change the order to best suit your needs.

