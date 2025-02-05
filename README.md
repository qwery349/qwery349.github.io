<!DOCTYPE html>
<html>
<head>
    <title>Текстовый редактор</title>
    <style>
        #container {
            width: 800px;
            height: 600px;
            border: 1px solid black;
            padding: 10px;
            font-size: 18px;
        }
        #text {
            width: 100%;
            height: 100%;
            padding: 10px;
            font-size: 18px;
            border: 1px solid black;
        }
    </style>
</head>
<body>
    <div id="container">
        <textarea id="text"></textarea>
    </div>
    <script>
        var textArea = document.getElementById('text');
        textArea.addEventListener('mousemove', function(e) {
            var x = e.clientX - textArea.offsetLeft;
            var y = e.clientY - textArea.offsetTop;
            var rect = textArea.getBoundingClientRect();
            var width = rect.width;
            var height = rect.height;
            var cursorX = Math.min(Math.max(x, 0), width);
            var cursorY = Math.min(Math.max(y, 0), height);
            textArea.selectionStart = cursorX;
            textArea.selectionEnd = cursorX;
            textArea.focus();
        });
    </script>
</body>
</html>
