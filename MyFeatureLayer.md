
<html>
    
    <head>
      <meta charset="utf-8">
      <meta name="viewport" content="initial-scale=1, maximum-scale=1, user-scalable=no">
      <title>My feature layer</title>
      <style>
        html, body, #viewDiv {
          padding: 0;
          margin: 0;
          height: 100%;
          width: 100%;
        }

        /*  styling the website */
        #MainHeading{ 
          text-align: center;
          background-color: lightblue;
          color: black;
          padding: 40px;
        }
        /* styling the id element */
        #header {
        background-color: lightblue;
        color: black;
        padding: 40px;
        text-align: center;
        }
        /* designing the class elements */
        .beaches {
        background-color: grey;
        color: white;
        border: 2px solid dark grey;
        margin: 20px;
        padding: 20px; 
        }
      </style>


      <link rel="stylesheet" href="https://js.arcgis.com/4.25/esri/themes/light/main.css">
      <script src="https://js.arcgis.com/4.25/"></script>
    
      <script>
      require([
        "esri/config",
        "esri/Map",
        "esri/views/MapView",
    
        "esri/layers/FeatureLayer"
    
      ], function(esriConfig,Map, MapView, FeatureLayer) {
    
      esriConfig.apiKey = "AAPKb2b10b8dac4347c09fd553839bb136d0lfvuRJAqtn2a_PkpZd8VSbySmTvPgQ2DwYkxUE5EvLGIYDswfW5YvaIDgQSFMIH2";
    
      const map = new Map({
        basemap: "arcgis-imagery"
      });
    
      const view = new MapView({
        container: "viewDiv",
        map: map,
        center: [151.23802082337784,-33.8222807184553],
        zoom: 11
      });
    
    //Sydney Beaches feature layer (points)
      const sydneybeachLayer = new FeatureLayer({
        url: "https://services1.arcgis.com/pMeXRvgWClLJZr3s/arcgis/rest/services/my_points/FeatureServer/0"
      });
    
      map.add(sydneybeachLayer,0)
    
      });
    </script>
    </head>




    <body>
          <!-- laying the structure for the website -->
      <h1 id = "MainHeading">BEAUTIFUL SYDNEY BEACHES</h1>

      <!-- defining the class -->
      <div class="beaches">
        <h2> BONDI BEACH</h2>
       
      </div> 
      
      <div class="beaches">
        <h2>MANLY BEACH</h2>
       
      </div>
      
      <div class="beaches">
        <h2>SHELLY BEACH</h2>
     
      </div>

      <div class="beaches">
        <h2>BALMORAL BEACH</h2>
      
      </div>
      <div id="viewDiv"></div>
    </body>
    </html>
