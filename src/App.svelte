<script>
    export let name;
</script>

<style>
    form {
        --text-color: #afafaf;
        max-width: 500px;
    }

    .field {
        width: 100%;
        position: relative;
        border-bottom: 2px dashed var(--text-color);
        margin: 4rem auto 1rem;
    }

    .field::after {
        content: "";
        position: relative;
        display: block;
        height: 4px;
        width: 100%;
        background: #d16dff;
        transform: scaleX(0);
        transform-origin: 0%;
        transition: transform 300ms ease;
        top: 2px;
    }

    .field:focus-within {
        border-color: transparent;
    }

    .field:focus-within::after {
        transform: scaleX(1);
    }

    .label {
        color: var(--text-color);
        font-size: 1.2rem;
    }

    .label {
        z-index: -1;
        position: absolute;
        transform: translateY(-2rem);
        transform-origin: 0%;
        transition: transform 400ms;
    }

    .field:focus-within .label, .input:not(:placeholder-shown) + .label {
        transform: scale(0.8) translateY(-5rem);
    }

    .input {
        outline: none;
        border: none;
        overflow: hidden;
        margin: 0;
        width: 100%;
        padding: .25rem 0;
        background: none;
        color: white;
        font-size: 1.2rem;
        font-weight: bold;
    }

    .input:valid {
        color: yellowgreen;
    }

    .input:invalid {
        color: orangered;
    }
</style>

<main>
    <form>
        <div class="field">
            <input type="email" name="email" class="input" placeholder=" ">
            <label for="email" class="label">Email</label>
        </div>

        <div class="field">
            <input type="password" class="input" placeholder=" ">
            <label for="password" class="label">Password</label>
        </div>
    </form>
</main>
