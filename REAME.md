# Wait For Papa Parse

A package that handles a file upload and waits for papaparse to finish parsing before returning data (i.e. no more "undefined" errors in the console)

## Installation
`npm install wait-for-papa-parse`

## Usage (Example in ReactJs)
**Must be used with async function.**

```jsx
<form name="inputForm" onChange={this.handleUpload}>
    <input type="file" id="csv-file" name="files" />
</form>
```

```javascript
handleUploadImage = async (e) => {
    const file = e.target.files[0];
    const response = await waitPapaParse(file)
    console.log(response) // {data: [], errors: [], meta: {}}
}
```

Note: The function will return the following Papa Parse Object:

```javascript
{
    data: [],
    errors: [],
    meta: {}
}