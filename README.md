
# Async Mongodb

## Description

Easiest module to connect to mongodb by promise or async/await

## Documentation

| what          | where                                          |
|---------------|------------------------------------------------|
| documentation | https://github.com/MrAbdelrahman10/asyncmongodb  |
| source        | https://github.com/MrAbdelrahman10/asyncmongodb |

### Bugs / Feature Requests

Think you’ve found a bug? Want to see a new feature in `asyncmongodb`? Please open an Issue here [https://github.com/MrAbdelrahman10/asyncmongodb/issues](https://github.com/MrAbdelrahman10/asyncmongodb/issues)

### Change Log

Change history can be found in [`HISTORY.md`](HISTORY.md).

# Installation

The recommended way to get started using the `Async Mongodb` is by using the `npm` (Node Package Manager) to install the dependency in your project.

Given that you have created your own project using `npm init` we install `Async Mongodb` and its dependencies by executing the following `npm` command.

```bash
npm install asyncmongodb2 --save
```

This will download the `asyncmongodb2` and add a dependency entry in your `package.json` file.

## Quick Start

This guide will show you how to set up a simple application using `asyncmongodb2`. 

### Create the `package.json` file

First, create a directory where your application will live.

```bash
mkdir myproject
cd myproject
```

Enter the following command and answer the questions to create the initial structure for your new project:

```bash
npm init
```

Next, install `asyncmongodb2` dependency.

```bash
npm install asyncmongodb2 --save
```

You should see **NPM** download a lot of files. Once it's done you'll find all the downloaded packages under the **node_modules** directory.


### Connect to MongoDB

Create a new **app.js** file and add the following code to try out some basic CRUD
operations using the **AsyncMongoDB**.

Add code to connect to the server and the database **myproject**:

Using **Async/Await**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
(async () => {
    const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
    await amng.connect();
    /**
	 Some Code
	*/
    amng.disconnect();
})();
```

Using **Promise**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
amng.connect()
    .then(/** Some Code **/)
    .then(_ => amng.disconnect())
    .catch((e) => {
        /** Some Code **/
        amng.disconnect()
    });
```

### Find Documents

Use **find()** to return all documents:

Using **Async/Await**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
(async () => {
    const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
    await amng.connect();
    const data = await amng.find({collection: 'countries', where:{}, fields:{}, sort: {name: 1}, limit: 10});
    /**
	 Some Code
	*/
    amng.disconnect();
})();
```

Using **Promise**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
amng.connect()
    .then(_ => mng.find({ collection: 'countries', where: {}, fields: {}, sort: { name: 1 }, skip: 1, limit: 10 }))
    .then(/** Some Code **/)
    .then(_ => amng.disconnect())
    .catch((e) => {
        /** Some Code **/
        amng.disconnect()
    });
```


### Find One Document

Use **findOne()** to return one document:

Using **Async/Await**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
(async () => {
    const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
    await amng.connect();
    const data = await amng.findOne({collection: 'countries', where:{}, sort: { name: 1 }, skip: 1, fields:{}, limit: 10});
    /**
	 Some Code
	*/
    amng.disconnect();
})();
```

Using **Promise**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
amng.connect()
    .then(_ => mng.findOne({ collection: 'countries', where: {}, fields: {}, limit: 10 }))
    .then(/** Some Code **/)
    .then(_ => amng.disconnect())
    .catch((e) => {
        /** Some Code **/
        amng.disconnect()
    });
```

### Insert One Document

Use **insert()** to insert one document:

Using **Async/Await**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
(async () => {
    const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
    await amng.connect();
    const data = await amng.insert({collection: 'countries', row:{name: "Egypt"}});
    /**
	 Some Code
	*/
    amng.disconnect();
})();
```

Using **Promise**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
amng.connect()
    .then(_ => mng.insert({ collection: 'countries', row: { name: "Egypt" } }))
    .then(/** Some Code **/)
    .then(_ => amng.disconnect())
    .catch((e) => {
        /** Some Code **/
        amng.disconnect()
    });
```


### Insert Many Documents

Use **insertMany()** to insert many documents:

Using **Async/Await**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
(async () => {
    const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
    await amng.connect();
    const res = await amng.insertMany({ collection: 'countries', rows: [{ _id: 1, name: 'egypt' }, { _id: 2, name: 'turkey' }, { _id: 3, name: 'malaysia' }], ignoreErrors: true }).catch((e) => e.code);
    /**
	 Some Code
	*/
    amng.disconnect();
})();
```

Using **Promise**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
amng.connect()
    .then(_ => mng.insertMany({ collection: 'countries', rows: [{ _id: 1, name: 'egypt' }, { _id: 2, name: 'turkey' }, { _id: 3, name: 'malaysia' }], ignoreErrors: true }).catch((e) => e.code))
    .then(/** Some Code **/)
    .then(_ => amng.disconnect())
    .catch((e) => {
        /** Some Code **/
        amng.disconnect()
    });
```

### Update One Document

Use **update()** to update one document:

Using **Async/Await**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
(async () => {
    const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
    await amng.connect();
    const data = await amng.update({collection: 'countries', where: {_id: 1}, row:{name: "Egypt"}});
    /**
	 Some Code
	*/
    amng.disconnect();
})();
```

Using **Promise**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
amng.connect()
    .then(_ => mng.update({ collection: 'countries', where: { _id: 1 }, row: { name: "Egypt" } }))
    .then(/** Some Code **/)
    .then(_ => amng.disconnect())
    .catch((e) => {
        /** Some Code **/
        amng.disconnect()
    });
```


### Update Many Documents

Use **updateMany()** to update many documents:

Using **Async/Await**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
(async () => {
    const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
    await amng.connect();
    const res = await amng.updateMany({ collection: 'countries', rows: [{ _id: 1, name: 'egypt' }, { _id: 2, name: 'turkey' }, { _id: 3, name: 'malaysia' }], ignoreErrors: true }).catch((e) => e.code);
    /**
	 Some Code
	*/
    amng.disconnect();
})();
```

Using **Promise**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
amng.connect()
    .then(_ => mng.updateMany({ collection: 'countries', rows: [{ _id: 1, name: 'egypt' }, { _id: 2, name: 'turkey' }, { _id: 3, name: 'malaysia' }], ignoreErrors: true }).catch((e) => e.code))
    //.then(/** Some Code **/)
    .then(_ => amng.disconnect())
    .catch((e) => {
        /** Some Code **/
        amng.disconnect()
    });
```

### Delete One Document

Use **delete()** to delete one document:

Using **Async/Await**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
(async () => {
    const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
    await amng.connect();
    const data = await amng.delete({collection: 'countries', where: {_id: 1}});
    /**
	 Some Code
	*/
    amng.disconnect();
})();
```

Using **Promise**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
amng.connect()
    .then(_ => mng.delete({ collection: 'countries', where: { _id: 1 } }))
    .then(/** Some Code **/)
    .then(_ => amng.disconnect())
    .catch((e) => {
        /** Some Code **/
        amng.disconnect()
    });
```


### Delete Many Documents

Use **deleteMany()** to delete many documents:

Using **Async/Await**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
(async () => {
    const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
    await amng.connect();
    const res = await amng.deleteMany({ collection: 'countries', where: {}, ignoreErrors: true }).catch((e) => e.code);
    /**
	 Some Code
	*/
    amng.disconnect();
})();
```

Using **Promise**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
amng.connect()
    .then(_ => mng.deleteMany({ collection: 'countries', where: {}, ignoreErrors: true }).catch((e) => e.code))
    .then(/** Some Code **/)
    .then(_ => amng.disconnect())
    .catch((e) => {
        /** Some Code **/
        amng.disconnect()
    });
```

### Count Documents

Use **count()** to get count of documents:

Using **Async/Await**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
(async () => {
    const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
    await amng.connect();
    const res = await amng.count({ collection: 'countries', where: {} }).catch((e) => e.code);
    /**
	 Some Code
	*/
    amng.disconnect();
})();
```

Using **Promise**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
amng.connect()
    .then(_ => mng.count({ collection: 'countries', where: {}, ignoreErrors: true }).catch((e) => e.code))
    .then(/** Some Code **/)
    .then(_ => amng.disconnect())
    .catch((e) => {
        /** Some Code **/
        amng.disconnect()
    });
```

### Drop Collection

Use **dropCollection()** to drop collections:

Using **Async/Await**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
(async () => {
    const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
    await amng.connect();
    const res = await amng.dropCollection('countries').catch((e) => e.code);
    /**
	 Some Code
	*/
    amng.disconnect();
})();
```

Using **Promise**
```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
amng.connect()
    .then(_ => mng.dropCollection('countries').catch((e) => e.code))
    .then(/** Some Code **/)
    .then(_ => amng.disconnect())
    .catch((e) => {
        /** Some Code **/
        amng.disconnect()
    });
```

### Create Index
Using **Async/Await**

```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
(async () => {
    const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
    await amng.connect();
    const res = await amng.createIndex({ collection: 'contracts', index: { contractAddress: 1 }, opts: { unique: true } }).catch((e) => e.code);
    /**
	 Some Code
	*/
    amng.disconnect();
})();
    
```


### aggregate
Using **Async/Await**

```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
(async () => {
    const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
    await amng.connect();
    const res = await amng.aggregate({ collection: 'contracts', pipeline: [], options: {}} });
    /**
	 Some Code
	*/
    amng.disconnect();
})();
    
```

### distinct
Using **Async/Await**

```js
// Load Module
const Asyncmongodb = require('asyncmongodb2');
// Connection URL
const url = 'mongodb://localhost:27017';
// Database Name
const dbName = 'myproject';

// Run test
(async () => {
    const amng = new Asyncmongodb({ dbName: dbName, uri: url, options: {} });
    await amng.connect();
    const res = await amng.distinct({ collection: 'contracts', field: {}, query: {} options: {}} });
    /**
	 Some Code
	*/
    amng.disconnect();
})();
    
```