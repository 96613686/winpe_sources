# Microsoft.Crm.Web.Tools.ProcessControl.BpfConfiguratorPage::SetScriptFiles

- ea: `0x5dd80`
- end: `0x5debd`
- name: `Microsoft.Crm.Web.Tools.ProcessControl.BpfConfiguratorPage::SetScriptFiles`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5ce20`

## string_xrefs

- `0x5ddc2`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0x5dd92`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0x5ddd2`: `/_static/_common/scripts/Mscrm.Caching.js`
- `0x5dde2`: `/_static/_common/scripts/InlineEditCommon.js`
- `0x5dda2`: `/_static/_common/scripts/SalesCommonImported.js`
- `0x5ddb2`: `/_static/_common/scripts/SalesCommonFramework.js`

## pseudocode

```c

```

## disassembly

```asm
0x5dd80  ldarg.0
0x5dd81  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5dd86  ldc.i4.1
0x5dd87  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x5dd8c  ldarg.0
0x5dd8d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5dd92  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/jquery_ui_1.8."...
0x5dd97  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5dd9c  ldarg.0
0x5dd9d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5dda2  ldstr    aStaticCommonSc_29// "/_static/_common/scripts/SalesCommonImp"...
0x5dda7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5ddac  ldarg.0
0x5ddad  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5ddb2  ldstr    aStaticCommonSc_30// "/_static/_common/scripts/SalesCommonFra"...
0x5ddb7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5ddbc  ldarg.0
0x5ddbd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5ddc2  ldstr    aStaticCommonSc// "/_static/_common/scripts/CrmInternalUti"...
0x5ddc7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5ddcc  ldarg.0
0x5ddcd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5ddd2  ldstr    aStaticCommonSc_13// "/_static/_common/scripts/Mscrm.Caching."...
0x5ddd7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5dddc  ldarg.0
0x5dddd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5dde2  ldstr    aStaticCommonSc_15// "/_static/_common/scripts/InlineEditComm"...
0x5dde7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5ddec  ldarg.0
0x5dded  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5ddf2  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0x5ddf7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5ddfc  ldarg.0
0x5ddfd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5de02  ldstr    aStaticFormsTex// "/_static/_forms/TextInputBehavior.js"
0x5de07  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5de0c  ldarg.0
0x5de0d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5de12  ldstr    aStaticFormsLoo_0// "/_static/_forms/LookupBehavior.js"
0x5de17  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5de1c  ldarg.0
0x5de1d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5de22  ldstr    aStaticFormsNum// "/_static/_forms/NumberInputBehavior.js"
0x5de27  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5de2c  ldarg.0
0x5de2d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5de32  ldstr    aStaticFormsDat// "/_static/_forms/DateTime.js"
0x5de37  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5de3c  ldarg.0
0x5de3d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5de42  ldstr    aStaticFormsChe// "/_static/_forms/Checkbox.js"
0x5de47  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5de4c  ldarg.0
0x5de4d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5de52  ldstr    aStaticFormsTab// "/_static/_forms/tabs.js"
0x5de57  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5de5c  ldarg.0
0x5de5d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5de62  ldstr    aStaticFormsFor// "/_static/_forms/form.js"
0x5de67  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5de6c  ldarg.0
0x5de6d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5de72  ldstr    aStaticControls_21// "/_static/_controls/editableselect/edita"...
0x5de77  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5de7c  ldarg.0
0x5de7d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5de82  ldstr    aStaticControls_8// "/_static/_controls/inlineedit/InlineEdi"...
0x5de87  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5de8c  ldarg.0
0x5de8d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5de92  ldstr    aStaticControls_22// "/_static/_controls/inlineedit/inlineedi"...
0x5de97  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5de9c  ldarg.0
0x5de9d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5dea2  ldstr    aStaticControls_7// "/_static/_controls/FlyoutDialog/FlyoutD"...
0x5dea7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5deac  ldarg.0
0x5dead  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5deb2  ldstr    aStaticToolsSol// "/_static/tools/solution/scripts/Managed"...
0x5deb7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5debc  ret
```
