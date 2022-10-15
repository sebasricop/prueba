<template>
    <div class="container">
        <div class="row">
            <div class="w-50 mx-auto">
                <h2>Clientes:</h2>

                <div class="col-12 p-4">
                    <div class="list-group">
                        <input
                            class="user"
                            v-model="name"
                            type="radio"
                            name="RadioInputName"
                            value="Tatiana Montoya"
                            id="Radio1"
                        />
                        <label class="list-group-item" for="Radio1"
                            >Tatiana Montoya</label
                        >

                        <input
                            class="user"
                            v-model="name"
                            type="radio"
                            name="RadioInputName"
                            value="Andres Pérez"
                            id="Radio2"
                        />
                        <label class="list-group-item" for="Radio2"
                            >Andres Pérez</label
                        >

                        <input
                            class="user"
                            v-model="name"
                            type="radio"
                            name="RadioInputName"
                            value="Guadalupe Rico Montoya"
                            id="Radio3"
                        />
                        <label class="list-group-item" for="Radio3"
                            >Guadalupe Rico Montoya</label
                        >
                    </div>
                </div>
                <h2>Monto:</h2>

                <div class="input-group flex-nowrap">
                    <input
                        type="number"
                        class="form-control"
                        placeholder="Monto a enviar"
                        v-model="price"
                        aria-label="Username"
                        aria-describedby="addon-wrapping"
                    />
                </div>
                <input
                    name=""
                    id=""
                    v-on:click.prevent="montoEnvio"
                    class="btn btn-primary m-2 w-100"
                    type="button"
                    value="Enviar monto"
                />
                <div class="border border-2 p-2">
                    <h2 class="mt-2">Resumen de la Transacción</h2>
                    <h4>Usuario: {{ name }}</h4>
                    <h4>Monto: {{ price }}</h4>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "prueba",
    data() {
        return {
            name: "",
            price: 0,
        };
    },
    methods: {
        montoEnvio() {
            if (this.name == "") {
                alert(`No has seleccionado un usuario`);
            }
            if (this.price <= 0) {
                alert(`No has Ingresado un monto valido`);
            }
            if (this.name != "" && this.price > 0) {
                alert(`Transacción exitosa`);

                this.name = "";
                this.price = "";
            }

            console.log(this.successText);
            console.log(this.errorText);
        },
    },
};
</script>

<style>
.list-group-item {
    user-select: none;
}

.list-group input[type="radio"] {
    display: none;
}

.list-group input[type="radio"] + .list-group-item {
    cursor: pointer;
}

.list-group input[type="radio"] + .list-group-item:before {
    content: "\2022";
    color: transparent;
    font-weight: bold;
    margin-right: 1em;
}

.list-group input[type="radio"]:checked + .list-group-item {
    background-color: #0275d8;
    color: #fff;
}
.list-group input[type="radio"]:checked + .list-group-item:before {
    color: inherit;
}
</style>
