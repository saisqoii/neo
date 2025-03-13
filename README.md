<!DOCTYPE html>
<html lang="nl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cute Pink Escape Room</title>
    <style>
        body {
            background-color: #ffccdd;
            color: #d63384;
            font-family: 'Arial', sans-serif;
            text-align: center;
        }
        .container {
            max-width: 400px;
            margin: 50px auto;
            background: white;
            padding: 20px;
            border-radius: 15px;
            box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.1);
        }
        input {
            width: 80%;
            padding: 10px;
            margin-top: 10px;
            border-radius: 5px;
            border: 2px solid #d63384;
        }
        button {
            background: #ff66b2;
            color: white;
            padding: 10px 20px;
            margin-top: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background: #ff3385;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>🎀 Cute Pink Escape Room 🎀</h1>
        <p id="question">Raadsel komt hier...</p>
        <input type="text" id="answer" placeholder="Typ je antwoord...">
        <button onclick="checkAnswer()">Antwoord</button>
        <p id="result"></p>
    </div>

    <script>
        const riddles = [
            { question: "Wat is zacht, roze en smelt op je tong?", answer: "suikerspin" },
            { question: "Welke bloem symboliseert liefde en is vaak roze?", answer: "roos" },
            { question: "Wat zegt een kat als hij blij is?", answer: "miauw" },
            { question: "Welke zoete lekkernij is rond en heeft een gat in het midden?", answer: "donut" },
            { question: "Wat draag je om je outfit schattiger te maken?", answer: "strik" },
            { question: "Welke vrucht is klein, roze en zoet?", answer: "aardbei" },
            { question: "Wat gebruik je om een brief te sluiten met liefde?", answer: "zegel" },
            { question: "Wat is een magisch dier met een hoorn en roze manen?", answer: "eenhoorn" },
            { question: "Wat is zacht, knuffelbaar en gevuld met pluche?", answer: "knuffelbeer" },
            { question: "Wat geeft licht en is roze in een trendy kamer?", answer: "neonlamp" }
        ];
        
        let step = 0;
        document.getElementById("question").innerText = riddles[step].question;

        function checkAnswer() {
            let input = document.getElementById("answer").value.toLowerCase();
            if (input === riddles[step].answer) {
                if (step === riddles.length - 1) {
                    document.getElementById("result").innerText = "🎉 Gefeliciteerd! Je hebt alle raadsels opgelost! 🎉";
                } else {
                    step++;
                    document.getElementById("question").innerText = riddles[step].question;
                    document.getElementById("answer").value = "";
                }
            } else {
                document.getElementById("result").innerText = "❌ Fout antwoord, probeer opnieuw!";
            }
        }
    </script>
</body>
</html>
