# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ActionHubControl::ConfigureHeader

- ea: `0x156d0`
- end: `0x15773`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ActionHubControl::ConfigureHeader`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x15700`: `/_static/_common/scripts/SalesCommonImported.js`
- `0x15710`: `/_static/_common/scripts/SalesCommonFramework.js`
- `0x15720`: `/_static/_common/scripts/SalesCrmSoapProxyService.js`
- `0x15730`: `/_static/_common/scripts/Wall.Interfaces.js`
- `0x15740`: `/_static/_common/scripts/Wall.Control.js`

## pseudocode

```c

```

## disassembly

```asm
0x156d0  ldarg.0
0x156d1  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x156d6  ldarg.0
0x156d7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x156dc  ldc.i4.1
0x156dd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x156e2  ldarg.0
0x156e3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x156e8  ldc.i4.1
0x156e9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQueryTemplate(bool)
0x156ee  ldarg.0
0x156ef  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x156f4  ldc.i4.1
0x156f5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJSRender(bool)
0x156fa  ldarg.0
0x156fb  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x15700  ldstr    aStaticCommonSc_0// "/_static/_common/scripts/SalesCommonImp"...
0x15705  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1570a  ldarg.0
0x1570b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x15710  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/SalesCommonFra"...
0x15715  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1571a  ldarg.0
0x1571b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x15720  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/SalesCrmSoapPr"...
0x15725  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1572a  ldarg.0
0x1572b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x15730  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/Wall.Interface"...
0x15735  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1573a  ldarg.0
0x1573b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x15740  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/Wall.Control.j"...
0x15745  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1574a  ldarg.0
0x1574b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x15750  ldstr    aStaticFormsAct_0// "/_static/_forms/actionhubcontrol.js"
0x15755  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1575a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1575f  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x15764  stloc.0
0x15765  ldloca.s 0
0x15767  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1576c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x15771  pop
0x15772  ret
```
