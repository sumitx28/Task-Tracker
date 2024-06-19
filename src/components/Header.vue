<template lang="en">
    <header>
        <h1>{{title}}</h1>
        <Button @click="onClick()" :text="showAddTask ? 'Close' : 'Add Task'" :color="showAddTask ? 'red' : 'green'"/>
    </header>
</template>

<script>
import Button from './Button';

export default {
    name: 'Header',
    props: {
        title: {
            type: String,
            default: "Hello World"
        },
        showAddTask: Boolean
    },
    components: {
        Button
    },
    methods: {
        onClick() {
            this.$emit('btn-click');
        },
    },
    emits: ['btn-click']
}
</script>

<style scope>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
}
</style>