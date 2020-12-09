<template>
  <input
    type="text"
    class="form-control my-2"
    placeholder="Ingrese actividad a desarrollar"
    v-model.trim="tarea.nombre"
  />
  <hr />

  <h4>Elija categoría:</h4>
  <div class="form-check form-check-inline">
    <input
      type="checkbox"
      id="check-1"
      class="form-check-input"
      v-model="tarea.categorias"
      value="Desarrollo"
    />
    <label for="check1" class="form-check-label">Desarrollo</label>
  </div>
  <div class="form-check form-check-inline">
    <input
      type="checkbox"
      id="check-2"
      class="form-check-input"
      v-model="tarea.categorias"
      value="analista"
    />
    <label for="check1" class="form-check-label">Analista</label>
  </div>
  <div class="form-check form-check-inline">
    <input
      type="checkbox"
      id="check-2"
      class="form-check-input"
      v-model="tarea.categorias"
      value="it"
    />
    <label for="check1" class="form-check-label">IT</label>
  </div>
  <hr />
  <h4>Estado en que se encuentra la actividad:</h4>
  <div class="mt-2">
    <div class="form-check form-check-inline">
      <input
        type="radio"
        id="radio-1"
        class="form-check-input"
        value="avanzada"
        v-model="tarea.estado"
      />
      <label for="radio-1" class="form-check-label">Avanzada</label>
    </div>
  </div>
  <div class="mt-2">
    <div class="form-check form-check-inline">
      <input
        type="radio"
        id="radio-2"
        class="form-check-input"
        value="retrasada"
        v-model="tarea.estado"
      />
      <label for="radio-2" class="form-check-label">Retrasada</label>
    </div>
  </div>
  <hr />

  <h4>Días restantes para entrega:</h4>
  <div class="mt-2">
    <input type="number" class="form-control" v-model.number="tarea.numero" />
  </div>

  <button class="btn btn-dark mt-2" type="submit" :disabled="bloquear">
    Procesar
  </button>
</template>

<script>
export default {
  props: {
    tarea: Object,
  },
  computed: {
    bloquear() {
      return this.tarea.nombre.trim() === "" ? true : false;
    },
  },
};
</script>
