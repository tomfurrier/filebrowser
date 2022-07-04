<template>
  <div class="card floating">
    <div class="card-title">
      <h2>{{ $t("prompts.upload") }}</h2>
    </div>
    <div class="card-action full">
      <p>
        {{ $t("prompts.setExpirationMessage") }}
      </p>
      <input
        class="input input--block"
        v-focus
        type="number"
        v-model.trim="expirationDays"
        min="0"
        max="99999"
        required
      />

      <div @click="uploadFile" class="action">
        <i class="material-icons">insert_drive_file</i>
        <div class="title">{{ $t("buttons.file") }}</div>
      </div>
     
      <!-- <div @click="uploadFolder" class="action">
        <i class="material-icons">folder</i>
        <div class="title">{{ $t("buttons.folder") }}</div>
      </div> -->
    </div>
  </div>
</template>

<script>
export default {
  name: "upload",
  data: function () {
    return {
      expirationDays: "",
    };
  },
  created() {
    this.expirationDays = "0";
  },
  methods: {
    uploadFile: function () {
      console.log("expirationDays: " + this.expirationDays);
      document.getElementById("upload-input").value = "";
      document.getElementById("upload-input").click();
    },
    // uploadFolder: function () {
    //   document.getElementById("upload-folder-input").value = "";
    //   document.getElementById("upload-folder-input").click();
    // },
  },
};
</script>
