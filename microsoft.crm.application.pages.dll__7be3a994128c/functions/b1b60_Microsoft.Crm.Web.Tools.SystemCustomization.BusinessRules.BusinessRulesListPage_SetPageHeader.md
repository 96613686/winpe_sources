# Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.BusinessRulesListPage::SetPageHeader

- ea: `0xb1b60`
- end: `0xb1c5f`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.BusinessRulesListPage::SetPageHeader`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb1b30`

## callees

- `0xd6830`

## string_xrefs

- `0xb1c12`: `/_static/_common/scripts/CommandBarActions.js`
- `0xb1c22`: `/_static/_common/scripts/jquery1.7.2.min.js`
- `0xb1c02`: `/_static/_common/scripts/ribbonactions.js`
- `0xb1b92`: `/_static/_common/scripts/InlineEditCommon.js`
- `0xb1bb2`: `/_static/_common/scripts/CrmServiceProxyFramework.js`

## pseudocode

```c

```

## disassembly

```asm
0xb1b60  ldarg.0
0xb1b61  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb1b66  ldc.i4.8
0xb1b67  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetHeader(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType)
0xb1b6c  ldarg.0
0xb1b6d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb1b72  ldstr    aStaticGridCmds// "/_static/_grid/cmds/util.js"
0xb1b77  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb1b7c  ldarg.0
0xb1b7d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb1b82  ldstr    aStaticToolsSys_0// "/_static/tools/systemcustomization/scri"...
0xb1b87  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb1b8c  ldarg.0
0xb1b8d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb1b92  ldstr    aStaticCommonSc_15// "/_static/_common/scripts/InlineEditComm"...
0xb1b97  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb1b9c  ldarg.0
0xb1b9d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb1ba2  ldstr    aStaticControls_8// "/_static/_controls/inlineedit/InlineEdi"...
0xb1ba7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb1bac  ldarg.0
0xb1bad  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb1bb2  ldstr    aStaticCommonSc_34// "/_static/_common/scripts/CrmServiceProx"...
0xb1bb7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb1bbc  ldarg.0
0xb1bbd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb1bc2  ldstr    aStaticControls_23// "/_static/_controls/ProcessControl/Proce"...
0xb1bc7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb1bcc  ldarg.0
0xb1bcd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb1bd2  ldstr    aStaticToolsSys_2// "/_static/tools/systemcustomization/busi"...
0xb1bd7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb1bdc  ldarg.0
0xb1bdd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb1be2  ldstr    aStaticToolsSol_5// "/_static/tools/Solution/Scripts/Managed"...
0xb1be7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb1bec  ldarg.0
0xb1bed  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb1bf2  ldstr    aStaticToolsDep_0// "/_static/tools/Dependency/Scripts/Depen"...
0xb1bf7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb1bfc  ldarg.0
0xb1bfd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb1c02  ldstr    aStaticCommonSc_14// "/_static/_common/scripts/ribbonactions."...
0xb1c07  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb1c0c  ldarg.0
0xb1c0d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb1c12  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/CommandBarActi"...
0xb1c17  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb1c1c  ldarg.0
0xb1c1d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb1c22  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/jquery1.7.2.mi"...
0xb1c27  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb1c2c  ldarg.0
0xb1c2d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb1c32  ldarg.0
0xb1c33  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb1c38  ldc.i4.0
0xb1c39  call     void Microsoft.Crm.Application.Pages.tools.SystemCustomization.Common.SegmentationUtility::SetSegmentationHeaders(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header currentHeader, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager currentResourceManager, [opt] bool skipSubcomponentTypes)
0xb1c3e  ldarg.0
0xb1c3f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb1c44  ldstr    aLocidActionSel_1// "LOCID_ACTION_SELECTONEBUSINESSRULE"
0xb1c49  ldarg.0
0xb1c4a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb1c4f  ldstr    aGridActionTooM// "Grid_Action_Too_Many_Custom_Messages_Se"...
0xb1c54  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb1c59  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xb1c5e  ret
```
