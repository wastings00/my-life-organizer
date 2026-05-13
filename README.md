<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stopwatch</title>
</head>
<body>
    <h1>Stopwatch</h1>
    <div id="timer">00:00:00</div>
    <button onclick="startStop()">Start</button>

    <script>
        let timer;
        let running = false;
        let seconds = 0;

        function startStop() {
            if (running) {
                clearInterval(timer);
                running = false;
                document.querySelector('button').innerText = 'Start';
            } else {
                timer = setInterval(updateTime, 1000);
                running = true;
                document.querySelector('button').innerText = 'Stop';
            }
        }

        function updateTime() {
            seconds++;
            let hrs = Math.floor(seconds / 3600);
            let mins = Math.floor((seconds % 3600) / 60);
            let secs = seconds % 60;

            if (hrs < 10) hrs = '0' + hrs;
            if (mins < 10) mins = '0' + mins;
            if (secs < 10) secs = '0' + secs;

            document.getElementById('timer').innerText = hrs + ':' + mins + ':' + secs;
        }
    </script>
</body>
</html>