# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TickerControl::ConfigureHeader

- ea: `0x2aca0`
- end: `0x2acd3`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TickerControl::ConfigureHeader`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x17cd0`
- `0x2aca0`

## string_xrefs

- `0x2acb8`: `LOCID_OPEN_TICKER_MASK`

## pseudocode

```c

```

## disassembly

```asm
0x2aca0  ldarg.0
0x2aca1  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::ConfigureHeader()
0x2aca6  call     class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.PerLanguageFeatures [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.PerLanguageFeatures::get_Instance()
0x2acab  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.PerLanguageFeatures::get_ShowStockSymbolAsLink()
0x2acb0  brfalse.s loc_2ACD2
0x2acb2  ldarg.0
0x2acb3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x2acb8  ldstr    aLocidOpenTicke// "LOCID_OPEN_TICKER_MASK"
0x2acbd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2acc2  ldstr    aWebFormsStyles_0// "Web._forms.styles.INPUT.tkr.htc_15_0"
0x2acc7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2accc  ldc.i4.0
0x2accd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2acd2  ret
```
