# smart-zip  

You can zip and unzip files, when you zip you can pass a regular expression to exclude files from zip, each file matched at regex will not be inserted at zip file.  
You can choose create top folder or not with the parameter.
  
Work on windows and ios (not tested on linux but i believe it's work to).  

Usage  
-----  

```
npm install smart-zip
```  

```javascript

var smartZip = require("smart-zip");

// Use to don't put files into .zip, each match won't be inserted into .zip
var regexExcludes = ['index.html'];

// Generate zip without top folder
smartZip.zip('app\\', 'zip.zip', false, regexExcludes, function (error) {
	if (error) {
		throw error;
	}
	console.log('zip file created without top folder.');
});

// Generate zip with top folder
smartZip.zip('app\\', 'zipTopLevel.zip', true, regexExcludes, function (error) {
	if (error) {
		throw error;
	}
	console.log('zip file created with top folder.');
});

// Unzip the files
smartZip.unzip("app1.zip", "app1", function (error) {
	if (error) {
		throw error;
	}
	console.log('File unziped.');
});

```  

Thanks  