<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Random Name Selector</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <img src="logo-yellow.svg" alt="logo" id="logo" />
    <h1 id="head">Concept Factory Friday Virtual Hangout</h1>
    <h2 id="text">Random Name Selector</h2>
    <textarea
      name="listofnames"
      id="listofnames"
      cols="50"
      rows="5"
      placeholder="Enter the list of names seperately on each line"
    ></textarea>
    <iframe
      id="frame"
      sandbox="allow-scripts allow-same-origin allow-presentation allow-popups"
      title="Questions"
      src="https://docs.google.com/presentation/d/e/2PACX-1vT0AS-7jkBtuvoNMWDmxMkip-8VvenjX81pvdotGIrk7y8OP8GgeYwgSvrBDiyLinlOUmFPe2tBhWwR/embed?start=false&loop=false&delayms=60000"
      frameborder="0"
      allowfullscreen="true"
      mozallowfullscreen="true"
      webkitallowfullscreen="true"
    >
      <base target="_parent" />
    </iframe>
    <br />
    <button id="but" onclick="textDataToArray()">Pick a Random Name</button>
    <div id="winner"><strong id="book"></strong></div>
    <script>
      function textDataToArray() {
        var textdata = document.getElementById("listofnames").value;
        var myArray = textdata.split("\n");
        var listarr = [];
        for (i = 0; i < myArray.length; i++) {
          listarr.push(myArray[i]);
        }
        // document.getElementById("list").innerHTML = listarr.toString();
        const randomName = listarr[Math.floor(Math.random() * listarr.length)];
        document.getElementById("book").innerHTML = randomName;

        var index = listarr.indexOf(randomName);
        if (index !== -1) {
          listarr.splice(index, 1);
          document.getElementById("listofnames").value = listarr.join("\n");
        }
      }
    </script>
  </body>
</html>
