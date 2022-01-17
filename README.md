## Welcome to GitHub Pages
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="https://cdn.staticfile.org/jquery/1.10.2/jquery.min.js"></script>
</head>
<style>

</style>

<body>
    <div id="show" style="font-size: 20px;text-align: center;margin-top: 50px;">
        <div class="showW"></div>
        <div class="showZ"></div>
        <div class="showS"></div>
        <div class="showX"></div>
        <div class="showJ"></div>
        <div class="showH"></div>
    </div>
</body>
<script>
    TimeDown(".showW", "2022-1-30 17:45:00",'距离HHJ Spring Festival holiday');
    TimeDown(".showZ", "2022-1-30 17:30:00",'距离ZHJ Spring Festival holiday');
     TimeDown(".showS", "2022-10-07 00:00:00",'HHJ-birthday');
    TimeDown(".showX", "2022-08-08 00:00:00",'ZHJ-birthday');
    function TimeDown(id, endDateStr,name) {
        var endDate = new Date(endDateStr);
        var nowDate = new Date();
        var totalSeconds = parseInt((endDate - nowDate) / 1000);
        var days = Math.floor(totalSeconds / (60 * 60 * 24));
        var modulo = totalSeconds % (60 * 60 * 24);
        var hours = Math.floor(modulo / (60 * 60));
        modulo = modulo % (60 * 60);
        var minutes = Math.floor(modulo / 60);
        var seconds = modulo % 60;
        document.querySelector(id).innerHTML = name +":" + days + "天" + hours + "小时" + minutes + "分钟" + seconds + "秒<br><br>";
        setTimeout(function () {
            TimeDown(id, endDateStr,name);
        }, 1000)
    }
    TimeDown()
    setInterval(TimeDown, 1000);
</script>

</html>
