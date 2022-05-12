# firePaaRad
4 på rad
<!DOCTYPE html>
<html lang="">

<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title></title>
    <link rel="stylesheet" href="style.css">
</head>
<h1 id="overskrift">
    Fire på rad
</h1>

<body>
    <div id="scoreboard">
        <div class="scorepoeng">3</div>
        <div class="scorepoeng">6</div>
    </div>

    <div id="spilleomrade">
        <div class="spillebrett">
            <div class="rad">
                <div id="0" class="spilleboks"></div>
                <div id="1" class="spilleboks"></div>
                <div id="2" class="spilleboks"></div>
                <div id="3" class="spilleboks"></div>
            </div>
            <div class="rad">
                <div id="4" class="spilleboks"></div>
                <div id="5" class="spilleboks"></div>
                <div id="6" class="spilleboks"></div>
                <div id="7" class="spilleboks"></div>
            </div>
            <div class="rad">
                <div id="8" class="spilleboks"></div>
                <div id="9" class="spilleboks"></div>
                <div id="10" class="spilleboks"></div>
                <div id="11" class="spilleboks"></div>
            </div>
            <div class="rad">
                <div id="12" class="spilleboks"></div>
                <div id="13" class="spilleboks"></div>
                <div id="14" class="spilleboks"></div>
                <div id="15" class="spilleboks"></div>
            </div>
        </div>
    </div>

    <h2 id="bedskjeder"></h2>
    <button id="restart">Restart spillet</button>
    <script src="script.js"></script>
</body>

</html>
<script> 
  var aktivSpill = true; //starter spillet
const sirkel = "O"; //spiller
const kryss = "X"; //spiller
var spilleren = kryss; //spilleren som starter
const spillStart = []; //hvordan spillet starter

var boks = document.querySelectorAll(".spilleboks"); //henter rutene fra html dokumentet
var rad = document.querySelectorAll(".rad"); //henter radene fra html dokumentet

for (let i = 0; i < boks.length; i++) {
	boks[i].addEventListener("click", boksTrykket)
}; //går gjennom alle rutene og legger til click



function boksTrykket(event) { //tar eventet som argument
	var boksverdi = event.target.boksverdi;
	if (aktivSpill == true) { //sjekker om spillet er i gang
		if (boksverdi !== spillStart) { //hvis verdien av ruten ikke er lik spillstart
			spillStart[boksverdi] = spilleren; //spillstart vil få den nye verdien av boksen som vil være det samme som spilleren som spiller(X)
			event.target.innerHTML = spilleren; //putter spilleren inn i boksen
			spilleren = spilleren === sirkel ? kryss : sirkel; //bytter på spillerne
			return true; //returnerer at spillet er i gang
		} else {
			
			bedskjeder.innerHTML += "Denne ruten er tatt!";
			return true;
		}
	}
};
                                </script>
