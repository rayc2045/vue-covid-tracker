<script>
export default {
  name: 'CountrySelect',
  props: ['countries'],
  data() {
    return {
      selected: 0,
    };
  },
  methods: {
    onChange() {
      const country = this.countries.find((item) => item.ID === this.selected);
      this.$emit('get-country', country);
    },
  },
};
</script>

<template>
  <select
    class="form-select mt-1 mb-10 block w-full border p-3 rounded"
    v-model="selected"
    @change="onChange()"
  >
    <option value="0">Global</option>
    <option v-for="country in countries" :value="country.ID">{{
      country.Country
    }}</option>
  </select>
</template>
