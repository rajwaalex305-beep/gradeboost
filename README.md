# gradeboost
<!DOCTYPE html>
<html lang="pl">
<head>
<meta charset="UTF-8">
<title>Kalkulator ocen</title>
<style>
body {
  font-family: Arial;
  background: #0f172a;
  color: white;
  text-align: center;
  padding: 50px;
}
input {
  padding: 10px;
  margin: 5px;
  width: 50px;
}
button {
  padding: 10px 20px;
  background: #22c55e;
  border: none;
  color: white;
  font-size: 16px;
}
.result {
  margin-top: 20px;
  font-size: 20px;
}
</style>
</head>
<body>

<h1>Kalkulator ocen 🔥</h1>

<p>Wpisz oceny (np. 3 4 5)</p>

<input id="grades" placeholder="np. 3 4 5">

<br><br>

<button onclick="calculate()">Oblicz</button>

<div class="result" id="result"></div>

<script>
function calculate() {
  let input = document.getElementById("grades").value;
  let grades = input.split(" ").map(Number);

  let sum = grades.reduce((a,b) => a+b, 0);
  let avg = sum / grades.length;

  let target = 4;
  let needed = (target * (grades.length + 1)) - sum;

  document.getElementById("result").innerHTML =
    "Twoja średnia: " + avg.toFixed(2) + "<br>" +
    "Potrzebujesz: " + Math.ceil(needed);
}
</script>

</body>
</html>
