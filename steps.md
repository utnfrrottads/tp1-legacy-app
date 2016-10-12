#steps
1. npm install -g express-generator
2. mkdir sequelize-mysql
3. cd sequelize-mysql
4. express -f
5. npm install
6. npm install --save sequelize sequelize-cli mysql sqlite3
7. checkear que no existen config, models ni migrations
8. npm install -g sequelize sequelize-cli
9. sequelize init
10. sequelize model:create --name User --attributes username:string
11. sequelize model:create --name Task --attributes title:string
12. add task association Task.belongsTo(models.User);
13. add user User.hasMany(models.Task)
14. add on bin/www
      var models = require('../models')

      models.sequelize.sync().then(function() {
          server.listen(port);
          server.on('error', onError);
          server.on('listening', onListening);
      });
15. set on app.js
    //sequelize setup
    app.set('models', require('./models'))
