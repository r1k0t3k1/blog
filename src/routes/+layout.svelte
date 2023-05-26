
<script>
  import { base } from '$app/paths';
  import "carbon-components-svelte/css/g90.css";
  import {
    Header,
    HeaderNav,
    HeaderNavItem,
    HeaderNavMenu,
    SideNav,
    SideNavItems,
    SideNavMenu,
    SideNavMenuItem,
    SideNavLink,
    SideNavDivider,
    SkipToContent,
    Content,
    Grid,
    Row,
    Column,
  } from "carbon-components-svelte";

  let isSideNavOpen = false;

  function toggle() {
    isSideNavOpen = !isSideNavOpen;
  }
</script>

<Header platformName="rikoteki blog" bind:isSideNavOpen>
  <svelte:fragment slot="skip-to-content">
    <SkipToContent />
  </svelte:fragment>
</Header>

<SideNav bind:isOpen={isSideNavOpen}>
  <SideNavItems>
    <SideNavLink href="{base}/" text="home" on:click={toggle}/>
    <SideNavLink href="{base}/about" text="about" on:click={toggle}/>
    <SideNavLink href="{base}/blog" text="blog" on:click={toggle}/>
  </SideNavItems>
</SideNav>

<Content>
  <slot></slot>
</Content>
