# js-hw-11-charles-tip-calci

## hosted link :- https://rohitdhawale07.github.io/js-hw-11-charles-tip-calci/

This is the simple project of creating a calculator which will calculate tip for perticular bill.
While creating html code we use form element, inside form we used label tag, select tag and button tag.
## HTML code
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Charles tip calci</title>
    <link rel="stylesheet" href="./style.css">
    <script defer src="./index.js"></script>
</head>
<body>
    <div id="container">
      <div id="form_container">
        <h1>Charle's Tip Calculator</h1>
            <form id="form">
                <label>
                    How much was your bill?<br>
                    Rs. <input type="text" id="Amount"><br>
                </label>
                <label>
                    How was your service?<br>
                    <select id="Squality">
                        <option disabled="" selected="" value="0">-- Choose an option --</option>
                        <option value="0.3">30% - Outstanding</option>
                        <option value="0.2">20% - Good</option>
                        <option value="0.15">15% - It was okay</option>
                        <option value="0.1">10% - Bad</option>
                        <option value="0.05">5%  - Terrible</option>
                    </select>
                </label>
                <label>
                    How many people are sharing the bill?<br>
                    <input type="text" id="totalPeople"> people
                </label>
                  <button type="button" id="calcbtn"> Calculate!</button>
                  <label for="tip" style="text-align: center; width: 100%; display: inline;" id="tiplabel">
                    Tip Amount<br>
                    <input type="text" id="totaltip" style="text-align:center ;">
                  </label>
            </form>
          </div>
    </div>

</body>
</html>
```

We applied a simple css properties as below.

## CSS code
```
*{
    margin: 0;
    padding: 0;
}
#container{
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100vh;
    background-image: url("https://video-images.vice.com/_uncategorized/1539696156342-Taj-Mumbai-If-These-Walls-Could-Talk-5-of-12.jpeg");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    padding: 1% 0%;
    font-family: cursive;
}
#form_container{
    width: 30%;
    height: 100%;
    background-color: rgb(233, 228, 228);
    padding: 1%;
}
#form_container>h1{
    text-align: center;
    height: 10%;
    margin: 0%;
}
#form{
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: flex-start;
    height: 90%;
    background-color: rgb(233, 228, 228);
}
#calcbtn{
    width: 100%;
    padding: 4% 0%;
    font-size: 130%;
    background-color: rgb(13, 1, 58);
    color: white;
    border: 2px solid grey;
}
h1{
    color: rgb(7, 95, 136);
}
label{
    color: rgb(7, 95, 136);
    font-size: 130%;
    font-weight: bolder;
}
```
Moving further to the JAVASCRIPT part,
we get all the id by using "getElementById()" method.
We added Event listener of "click" type event to the calculate button.
While calculating the tip we used formula of (billamount*serviceQuality) / numPeople.
## JAVASRCIPT
```
var tiplabel = document.getElementById("tiplabel");
tiplabel.style.display = "none";
var calulate = document.getElementById("calcbtn");
calulate.addEventListener('click',()=>{
var billamount = document.getElementById("Amount").value;
var serviceQuality = document.getElementById("Squality").value;
var numPeople = document.getElementById("totalPeople").value;
document.getElementById ("totaltip").value= " RS "+(billamount*serviceQuality) / numPeople+" !";
tiplabel.style.display = "inline";
})
```
