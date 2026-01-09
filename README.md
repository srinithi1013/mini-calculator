<img width="1920" height="1080" alt="Screenshot (12)" src="https://github.com/user-attachments/assets/a695aa93-4b1f-4726-a472-fec233ddceda" />
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Calculator</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f2f2f2;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .calculator {
            background-color: #ffffff;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.2);
        }

        #display {
            width: 100%;
            height: 50px;
            font-size: 20px;
            margin-bottom: 10px;
            text-align: right;
            padding-right: 10px;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 60px);
            gap: 10px;
        }

        button {
            height: 50px;
            font-size: 18px;
            cursor: pointer;
        }

        .equal {
            background-color: #4CAF50;
            color: white;
        }

        .clear {
            background-color: #f44336;
            color: white;
        }
    </style>

    <script>
        function appendValue(value) {
            document.getElementById("display").value += value;
        }

        function clearDisplay() {
            document.getElementById("display").value = "";
        }

        function calculate() {
            try {
                let result = eval(document.getElementById("display").value);
                document.getElementById("display").value = result;
            } catch {
                document.getElementById("display").value = "Error";
            }
        }
    </script>
</head>

<body>
    <div class="calculator">
        <input type="text" id="display" disabled>

        <div class="buttons">
            <button onclick="appendValue('7')">7</button>
            <button onclick="appendValue('8')">8</button>
            <button onclick="appendValue('9')">9</button>
            <button onclick="appendValue('/')">÷</button>

            <button onclick="appendValue('4')">4</button>
            <button onclick="appendValue('5')">5</button>
            <button onclick="appendValue('6')">6</button>
            <button onclick="appendValue('*')">×</button>

            <button onclick="appendValue('1')">1</button>
            <button onclick="appendValue('2')">2</button>
            <button onclick="appendValue('3')">3</button>
            <button onclick="appendValue('-')">−</button>

            <button onclick="appendValue('0')">0</button>
            <button onclick="appendValue('.')">.</button>
            <button class="clear" onclick="clearDisplay()">C</button>
            <button class="equal" onclick="calculate()">=</button>

            <button onclick="appendValue('+')">+</button>
        </div>
    </div>
</body>
</html>

