<script setup>
import { useForm } from '@inertiajs/vue3';


const from = useForm({
    make: '',
    model: '',
    owner: '',
    plate: '',
})

const submit = () => {
    from.submit('post', '/cars')
}

</script>

<template>
    <h1 class="text-4xl border border-b-gray-700">Create Car</h1>

    <div style="max-width: 400px;" class="p-4">
       <form @submit.prevent="submit">
           <div class="mb-3">
               <label for="make">Make</label>
               <input type="text" id="make" class="w-full" v-model="form.make">
            </div>
            <div class="mb-3">
               <label for="model">Model</label>
               <input type="text" id="model" class="w-full" v-model="form.model">
            </div>
            <div class="mb-3">
               <label for="plate">Plate</label>
               <input type="text" id="plate" class="w-full" v-model="form.plate">
            </div>
            <div class="mb-3">
               <label for="owner">Owner</label>
               <input type="text" id="owner" class="w-full" v-model="form.owner">
            </div>
            <button type="submit" class="bg-blue-600 text-white py-2 px-4 rounded">Save Car</button>
        </form>
    </div>
</template>
