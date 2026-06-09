# Microsoft.Crm.Sales.Web.Sfa.InvoiceCloseDetailPage::ConfigurePage

- ea: `0x1230`
- end: `0x126e`
- name: `Microsoft.Crm.Sales.Web.Sfa.InvoiceCloseDetailPage::ConfigurePage`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1230`

## pseudocode

```c

```

## disassembly

```asm
0x1230  ldarg.0
0x1231  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::ConfigurePage()
0x1236  ldarg.0
0x1237  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x123c  ldstr    aRequiredFields// "Required_Fields_Background_Color"
0x1241  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1246  stloc.0
0x1247  ldloc.0
0x1248  brfalse.s loc_126D
0x124a  ldloc.0
0x124b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1250  brfalse.s loc_126D
0x1252  ldarg.0
0x1253  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Sales.Web.Sfa.InvoiceCloseDetailPage::selStatus
0x1258  ldstr    aStyle// "Style"
0x125d  ldstr    aBackgroundColo// "background-color:"
0x1262  ldloc.0
0x1263  call     string [mscorlib]System.String::Concat(string, string)
0x1268  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0x126d  ret
```
