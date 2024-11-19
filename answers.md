Q1: What is the URL of the WMS GetCapabilities request?
> https://friendly-sniffle-q7p6xxj9v56vcq77-8080.app.github.dev/geoserver/ows?service=WMS&version=1.3.0&request=GetCapabilities

Q2: What is the URL of the WFS GetCapabilities request?
> https://friendly-sniffle-q7p6xxj9v56vcq77-8080.app.github.dev/geoserver/ows?service=WFS&acceptversions=2.0.0&request=GetCapabilities

Q3: Submit a screenshot of your updated WFS Layer Preview
> Submitted as `q3wfs_preview.png`

Q4: What does drawing order refer to? Which layer goes on top, the first or the last layer in the list?
> Drawing order is the order in which layers are rendered. The layer at the top is the one that goes on top of all the other layers.

Q5: Submit a screenshot of the Layer Preview of the Spearfish Layer Group when sf:sfdem is listed as the 3rd layer.
> Submitted as `q5_preview.png` and `q5_drawing_order.png`

Q6: What is the WMS url for the single-tiled request?
> https://friendly-sniffle-q7p6xxj9v56vcq77-8080.app.github.dev/geoserver/wms?SERVICE=WMS&VERSION=1.1.1&REQUEST=GetMap&FORMAT=image%2Fpng&TRANSPARENT=true&STYLES&LAYERS=spearfish&exceptions=application%2Fvnd.ogc.se_inimage&SRS=EPSG%3A26713&WIDTH=1900&HEIGHT=1000&BBOX=591036.6589767039%2C4911975.798920362%2C609170.1309450499%2C4921519.731535281
> image size is 1900 x 1000 pixels


Q7: What is the WMS url for one of the tiled requests? What is the image size?
> https://friendly-sniffle-q7p6xxj9v56vcq77-8080.app.github.dev/geoserver/wms?SERVICE=WMS&VERSION=1.1.1&REQUEST=GetMap&FORMAT=image%2Fpng&TRANSPARENT=true&tiled=true&STYLES&LAYERS=spearfish&exceptions=application%2Fvnd.ogc.se_inimage&tilesOrigin=589425.9342365642%2C4913959.224611808&WIDTH=256&HEIGHT=256&SRS=EPSG%3A26713&BBOX=603481.9471065588%2C4917034.08320627%2C604703.5704812685%2C4918255.70658098
> image size is 256 x 256 pixels.

Q8: What is the URL of your coarse resolution sample of a WMTS url? What level does this tile refer to? Notice the differences. What are some of the fields that are unique to this url?
> https://friendly-sniffle-q7p6xxj9v56vcq77-8080.app.github.dev/geoserver/gwc/service/wmts?layer=spearfish&style=&tilematrixset=EPSG%3A4326&Service=WMTS&Request=GetTile&Version=1.0.0&Format=image%2Fpng&TileMatrix=EPSG%3A4326%3A13&TileCol=3467&TileRow=2074
> TileMatrix = 13 so it's zoom level 13, if I'm understanding your question right
> WMTS uses TileCol, TileRow and TileMatrix, so those fields are unique to this url. 

Q9: In the zoomed-out URL, what are the TileCol and TileRow?
> TileCol =  1731
> TileRow = 1037

Q10: In the zoomed-in URL, what are the TileCol and TileRow?

> TileCol = 3467
> TileRow = 2075

Q11: Why are they so different for the same location in the map?
> They are different because as the requests are made, the tile matrix changes, so my rows/columns have to change as well. So with a different level of "zoom" my pixels are different.

Q12: Is there a difference in the TileMatrix? %3A is an HTML encoding for a colon, :.What does the number after EPSG:4326 mean?
> Yes.
> The number after EPSG:4326 is how many times the "world" was split up. It's just a way of indexing the world into tiles, so it's a set of tile coordinates.