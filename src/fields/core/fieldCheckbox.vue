<template lang="pug">
	.radio-list(:disabled="disabled", v-attributes="'wrapper'")		.radio-list(:disabled="disabled", v-attributes="'wrapper'")
		label(v-for="item in items", :class="getItemCssClasses(item)", v-attributes="'label'")			label(v-for="item in items", :class="getItemCssClasses(item)", v-attributes="'label'")
			input(:id="getFieldID(schema, true)", type="radio", :disabled="isItemDisabled(item)", :name="id", @click="onSelection(item)", :value="getItemValue(item)", :checked="isItemChecked(item)", :class="schema.fieldClasses", :required="schema.required", v-attributes="'input'")				el-radio(:id="getFieldID(schema, true)", type="radio", :label="getItemName(item)" :disabled="isItemDisabled(item)", :name="id", @click="onSelection(item)", :value="getItemValue(item)", :checked="isItemChecked(item)", :class="schema.fieldClasses", :required="schema.required", v-attributes="'input'")
			| {{ getItemName(item) }}
</template>

<script>
import abstractField from "../abstractField";

export default {
	mixins: [abstractField]
};
</script>

<style lang="scss">
.vue-form-generator .field-checkbox input {
	margin-left: 12px;
}
</style>
