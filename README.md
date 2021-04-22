# Aue.js
Aue is a js framework!

``` html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8" />
		<title>Aue.js demo</title>
		<script src="js/aue.js"></script>
		<style>
			body {
				text-align: center;
			}
		</style>
	</head>
	<body>

		<div id="app">
			<h1>{{ title }}</h1>
			<p>{{ message }}</p>
			<p>time: {{ time }}</p>
			<input type="button" text="Get time" click="getTime" />
			<br /><br />
			<input id="input" text="{{ inputText }}" />
			<input type="button" text="clear" click="clear" />
			<p>text: {{ inputText }}</p>
			<input type="button" text="click me!" click="fn" />
		</div>

		<script>
			var app = new Aue({
				el: "#app",
				data: {
					title: 'Aue.js',
					message: 'Welcome to Aue.js!',
					time: new Date(),
					inputText: ''
				},
				methods: {
					getTime: function() {
						alert(aue.time);
					},
					clear: function() {
						aue.inputText = '';
					},
					fn: function(self) {
						alert(self.text);
					}
				}
			});

			setInterval(function() {
				aue.time = new Date();
			});

			$("#input").bind("input propertychange", function(event) {
				aue.inputText = $("#input").val();
			});
		</script>
	</body>
</html>
```