<script>
  import Button from "../elements/Button.svelte";
  import IconDisplay from "../elements/IconDisplay.svelte";
  import { fade } from "svelte/transition";
  export let selectedWalletModule;
  export let onBack;
  export let installMessage;
</script>

<style>
  section {
    color: inherit;
    display: block;
  }

  footer {
    display: flex;
    justify-content: space-between;
  }
</style>

<section class="bn-onboard-custom bn-onboard-modal-selected-wallet" in:fade>
  <IconDisplay
    iconSrc={selectedWalletModule.iconSrc}
    iconSrcSet={selectedWalletModule.iconSrcSet}
    text={selectedWalletModule.name} />

  {#if installMessage}
    {@html installMessage}
  {/if}

  <footer class="bn-onboard-custom bn-onboard-modal-selected-wallet-footer">
    <a
      href={selectedWalletModule.link}
      rel="noreferrer noopener"
      target="_blank">
      <Button>Install {selectedWalletModule.name}</Button>
    </a>
    <Button onclick={onBack}>Back</Button>
  </footer>
</section>
