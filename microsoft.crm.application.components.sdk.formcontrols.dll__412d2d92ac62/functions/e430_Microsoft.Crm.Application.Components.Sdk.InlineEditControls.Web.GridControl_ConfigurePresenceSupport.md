# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::ConfigurePresenceSupport

- ea: `0xe430`
- end: `0xe470`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::ConfigurePresenceSupport`
- size: `64`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xde80`
- `0x10870`

## callees

- `0xe430`

## string_xrefs

- `0xe465`: `/_static/_common/scripts/presence.js`

## pseudocode

```c

```

## disassembly

```asm
0xe430  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0xe435  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsPresenceEnabled()
0xe43a  stloc.0
0xe43b  ldarg.0
0xe43c  ldstr    aBpresenceenabl// "_bPresenceEnabled"
0xe441  ldloc.0
0xe442  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xe447  ldarg.0
0xe448  ldstr    aLocidGridRefre// "LOCID_GRID_REFRESH_TRY_AGAIN"
0xe44d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe452  ldstr    aOptionalfeatur// "OptionalFeatures.aspx_Text_61"
0xe457  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe45c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xe461  ldloc.0
0xe462  brfalse.s loc_E46F
0xe464  ldarg.0
0xe465  ldstr    aStaticCommonSc_8// "/_static/_common/scripts/presence.js"
0xe46a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe46f  ret
```
