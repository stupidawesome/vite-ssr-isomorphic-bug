<script context="module">
    import fetch from "cross-fetch"
    export async function load() {
        // should use node-fetch
        return {
            props: {
                data: await fetch('https://jsonplaceholder.typicode.com/todos/1')
                .then(res => res.json())
            }
        }
    }
</script>

<script>
    export let data
    console.log('data', data)

    async function loadData() {
        // should use XMLHttpRequest
        const res = await fetch('https://jsonplaceholder.typicode.com/todos/1')
                .then(res => res.json())
        console.log(res)
    }
</script>

<button on:click={loadData}>Load</button>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>