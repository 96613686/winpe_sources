# Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::ConfigurePage

- ea: `0x147f0`
- end: `0x148bf`
- name: `Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::ConfigurePage`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x147d0`
- `0x147e0`
- `0x147f0`
- `0x14d00`

## string_xrefs

- `0x14870`: `isReadOnly`
- `0x1488f`: `isReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x147f0  ldarg.0
0x147f1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x147f6  ldarg.0
0x147f7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x147fc  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x14801  stloc.0
0x14802  ldarg.0
0x14803  call     instance bool Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::IsProfileItemAssociationFiltersPage()
0x14808  brfalse.s loc_14838
0x1480a  ldloc.0
0x1480b  ldarg.0
0x1480c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x14811  ldstr    aMobileofflinep// "MobileOfflineProfileItemAssociationFilt"...
0x14816  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1481b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x14820  ldloc.0
0x14821  ldarg.0
0x14822  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x14827  ldstr    aMobileofflinep_0// "MobileOfflineProfileItemAssociationFilt"...
0x1482c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x14831  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x14836  br.s     loc_14864
0x14838  ldloc.0
0x14839  ldarg.0
0x1483a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1483f  ldstr    aMobileofflinep_1// "MobileOfflineProfileItemFilters_DialogT"...
0x14844  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x14849  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x1484e  ldloc.0
0x1484f  ldarg.0
0x14850  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x14855  ldstr    aMobileofflinep_2// "MobileOfflineProfileItemFilters_DialogD"...
0x1485a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1485f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x14864  ldarg.0
0x14865  ldarg.0
0x14866  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1486b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x14870  ldstr    aIsreadonly// "isReadOnly"
0x14875  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1487a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1487f  brfalse.s loc_14884
0x14881  ldc.i4.0
0x14882  br.s     loc_1489E
0x14884  ldarg.0
0x14885  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1488a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1488f  ldstr    aIsreadonly// "isReadOnly"
0x14894  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x14899  call     bool [mscorlib]System.Boolean::Parse(string)
0x1489e  call     instance void Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::set_IsReadOnly(bool value)
0x148a3  ldarg.0
0x148a4  call     instance bool Microsoft.Crm.Common.Application.Pages.MobileOfflineProfileRuleFilters::get_IsReadOnly()
0x148a9  brfalse.s loc_148BE
0x148ab  ldloc.0
0x148ac  ldc.i4.0
0x148ad  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x148b2  ldloc.0
0x148b3  ldc.i4.2
0x148b4  ldstr    aButtonLabelOk// "Button_Label_OK"
0x148b9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x148be  ret
```
