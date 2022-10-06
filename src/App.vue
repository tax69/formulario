<template>
  <div id="app">
    <nav class="navbar navbar-dark bg-primary">
      <a href="/" class="navbar-brand">Formulario De Participacion</a>
    </nav>

    <!-- contenido prinsipal -->
    <div class="container">
      <div class="row mt-5">
        <div class="col-sm-4">
          <div class="card">
            <div class="card-header">
              <h3>ingrese un nuevo participante</h3>
            </div>
            <div class="card-body">
              <form>
                <div class="from-group">
                  <input type="text" class="from-control" v-model="newWebsite.name"
                  placeholder="Nombre">
                </div>
                <div class="from-group">
                  <input type="text" class="from-control" v-model="newWebsite.correo"
                  placeholder="Correo">
                </div>
                <div class="from-group">
                  <input type="text" class="from-control" v-model="newWebsite.institucion"
                  placeholder="Institucion">
                </div>
                <button type="submit" class="btn btn-primary">
                  save
                </button>
              </form>
            </div>
          </div>
        </div>
        <div class="col-sm-8 text-center">
          <img src="./assets/logo.png">
          <div class="card">
            <div class="card-header">
              <h3>Lista De Participantes</h3>
            </div>
            <div class="card-body">
              <table class="table table-striped table-bordered">
                <thead>
                  <tr>
                    <th>Nombre</th>
                    <th>correo</th>
                    <th>institucion</th>
                  </tr>
                </thead>
                <tbody>

                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
    </div>
    
  </div>
</template>

<script>
import Firebase from 'firebase';
import config from './config';
let app = Firebase.initializeApp(config);
let db = app.database();
let websitesRef = db.reg('websites');

export default {
  name: 'App',

  firebase:{
    websites: websitesR
   
  },
  data(){
    return{
      newWebsite:{
        nombre:'',
        correo:'',
        institucion:''
      }
    }
  }
}
</script>

<style>
#app {

}
</style>
