<template>
  <UserForm
    :groups="groups"
    :schools="schools"
    :years="years"
    :notice="notice"
    databaseReference="administradores"
    userRemovedGroup="administrador"
    title="Administradores"
  />
</template>

<script>
import UserForm from "../../components/Dashboard/UserForm";
import { db } from "../../firebase";

export default {
  name: "ManagersEdit",
  data: () => ({
    notice:
      "# Apenas aqueles com liderança devem ser adicionados como Administradores...",

    groups: ["Líder", "Vice-Líder", "Orientador", "Desenvolvedor"],
    schools: ["Joana D'Arc", "Jorge Amado", "Irrelevante"],
    years: ["9° Ano", "1° Ano", "2° Ano", "3° Ano", "Irrelevante"],

    tableBody: []
  }),
  components: {
    UserForm
  },
  firebase: {
    tableBody: db.ref("administradores")
  }
};
</script>