# Microsoft.Crm.Application.Components.UI.RegionalOptions::ConfigureHeader

- ea: `0x21f40`
- end: `0x21f85`
- name: `Microsoft.Crm.Application.Components.UI.RegionalOptions::ConfigureHeader`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3380`
- `0x38d0`
- `0x21f40`
- `0x23b60`
- `0x24080`

## string_xrefs

- `0x21f5a`: `/_static/tools/_common/scripts/regionaloptions.js`

## pseudocode

```c

```

## disassembly

```asm
0x21f40  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x21f45  brfalse.s loc_21F4E
0x21f47  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x21f4c  brfalse.s loc_21F84
0x21f4e  ldarg.0
0x21f4f  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0x21f54  ldarg.0
0x21f55  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x21f5a  ldstr    aStaticToolsCom_0// "/_static/tools/_common/scripts/regional"...
0x21f5f  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x21f64  ldarg.0
0x21f65  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x21f6a  ldstr    aLocidRegioncod// "LOCID_REGIONCODE_REQUIRED"
0x21f6f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x21f74  ldstr    aWebToolsRegion// "Web.Tools.RegionalOptions.MissingLocale"...
0x21f79  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21f7e  ldc.i4.0
0x21f7f  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x21f84  ret
```
