<template>
  <div class="container">
    <h3>Form Verileriyle Çalışmak</h3>
    <hr>
    <div class="row">
      <div class="col-md-6">
        <div class="panel panel-warning">
          <div class="panel-heading">
            <h4>Başvuru Formu</h4>
          </div>
          <div class="panel-body">
            <form>
              <div class="row">
                <div class="col-md-12">
                  <div class="form-group">
                    <label for="email">Kullanıcı Adı</label>
                    <input type="text" v-model="userName" id="username" class="form-control">
                  </div>
                  <div class="form-group">
                    <label for="password">Şifre</label>
                    <input type="password" v-model="userPassword" id="password" class="form-control">
                  </div>
                  <div class="form-group">
                    <label for="age">Yaş</label>
                    <input type="number" v-model="userAge" id="age" class="form-control">
                  </div>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12 form-group">
                  <label for="message">Açıklama</label><br>
                  <textarea id="message" v-model="userDescription" rows="3" class="form-control"></textarea>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12">
                  <div class="form-group">
                    <label>
                      <input v-model="userJob" type="checkbox" value="yazilim"> Yazılım
                    </label>
                    <label>
                      <input v-model="userJob" type="checkbox" value="donanim"> Donanım
                    </label>
                  </div>

                </div>
              </div>
              <div class="row">
                <div class="col-md-12 form-group">
                  <label>
                    <input v-model="userGender" type="radio" value="erkek"> Erkek
                  </label>
                  <label>
                    <input v-model="userGender" type="radio" value="kadin"> Kadın
                  </label>
                </div>
              </div>
              <div class="row">
                <div class="col-md-12 from-group">
                  <label>Şehir</label>
                  <select v-model="selecetedCity" class="form-control">
                    <option :selected="items == 'Van'" v-for="items in userCity"> {{
                        items
                    }}</option>
                  </select>
                </div>
              </div>
              <hr>
              <div class="row">
                <div class="col-md-12">
                  <button @click.prevent="submit" class="btn btn-primary">Gönder!
                  </button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
      <div class="col-md-6">
        <div class="panel panel-info" v-if="fromPost">
          <div class="panel-heading">
            <h4>Form Verileri</h4>
          </div>
          <div class="panel-body">
            <p>Kullanıcı Adı: {{ userName }}</p>
            <p>Şifre:{{ userPassword }}</p>
            <p>Yaş:{{ userAge }}</p>
            <p>Açıklama:{{ userDescription }} </p>
            <p><strong>İlgi Alanları</strong></p>
            <ul>
              <li v-for="item in userJob"> {{ item }}</li>
            </ul>
            <p>Cinsiyet: {{ userGender }}</p>
            <p>Şehir: {{ selecetedCity }}</p>
          </div>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      userName: "",
      userPassword: "",
      userAge: null,
      userDescription: "",
      userJob: [],
      userGender: "",
      userCity: ["Van", "İstanbul", "Konya", "İzmir"],
      selecetedCity: "",
      fromPost: false
    }
  },
  methods: {
    submit() {
      this.fromPost = true
    }
  }
}
</script>

<style>

</style>
