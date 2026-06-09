# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TickerControl::ConfigureHeader

- ea: `0x12030`
- end: `0x12073`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TickerControl::ConfigureHeader`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x12030`

## string_xrefs

- `0x12058`: `LOCID_OPEN_TICKER_MASK`

## pseudocode

```c

```

## disassembly

```asm
0x12030  ldarg.0
0x12031  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x12036  ldarg.0
0x12037  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1203c  ldstr    aStaticFormsTex// "/_static/_forms/textinputbehavior.js"
0x12041  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x12046  call     class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.PerLanguageFeatures [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.PerLanguageFeatures::get_Instance()
0x1204b  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.PerLanguageFeatures::get_ShowStockSymbolAsLink()
0x12050  brfalse.s loc_12072
0x12052  ldarg.0
0x12053  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x12058  ldstr    aLocidOpenTicke// "LOCID_OPEN_TICKER_MASK"
0x1205d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x12062  ldstr    aWebFormsStyles_0// "Web._forms.styles.INPUT.tkr.htc_15_0"
0x12067  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1206c  ldc.i4.0
0x1206d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12072  ret
```
