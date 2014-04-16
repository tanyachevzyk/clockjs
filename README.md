clockjs
=======
<html>

<head>

<title>Clock</title>

<script language="JavaScript">

var timer=null;

var timerrun=false;

function stoptime() {

	if(timerrun)

	clearTimeout(timer);

	timerrun=false;

}

function starttime() {

	stoptime();

	showtime();

}

function showtime() {

var all=new Date();

var hours=all.getHours();

var minutes=all.getMinutes();

var seconds=all.getSeconds();

var timevalue=" " + ((hours>12) ? hours-12 : hours) 

timevalue += ((minutes<10) ? ":0" : ":") + minutes

timevalue += ((seconds<10) ? ":0" : ":") + seconds

timevalue +=(hours>=12) ? "P.M." : "A.M."

document.clock.next.value=timevalue;

timer=setTimeout('showtime()',1000);

timerrun=true;

}

</script>

<body bgcolor=ffffff text=ff0000 onLoad="starttime()">

<center>

<form name=clock>

<input type=text name=next size=12 value=' '>

</center>

</form>

</body>

</html>
