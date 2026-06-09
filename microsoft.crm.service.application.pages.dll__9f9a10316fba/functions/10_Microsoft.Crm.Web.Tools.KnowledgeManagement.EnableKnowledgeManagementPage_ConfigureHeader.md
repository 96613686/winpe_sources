# Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::ConfigureHeader

- ea: `0x10`
- end: `0x7d`
- name: `Microsoft.Crm.Web.Tools.KnowledgeManagement.EnableKnowledgeManagementPage::ConfigureHeader`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x32`: `/_static/_common/scripts/SalesCommonFramework.js`
- `0x42`: `/_static/_common/scripts/Wall.Interfaces.js`
- `0x52`: `/_static/_common/scripts/Wall.Control.js`
- `0x62`: `/_static/_controls/SearchWidget/ExternalInteractionService.js`

## pseudocode

```c

```

## disassembly

```asm
0x10  ldarg.0
0x11  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x16  ldc.i4.1
0x17  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x1c  ldarg.0
0x1d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x22  ldstr    aStaticToolsKno// "/_static/tools/knowledgeManagement/scri"...
0x27  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x2c  ldarg.0
0x2d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x32  ldstr    aStaticCommonSc// "/_static/_common/scripts/SalesCommonFra"...
0x37  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x3c  ldarg.0
0x3d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x42  ldstr    aStaticCommonSc_0// "/_static/_common/scripts/Wall.Interface"...
0x47  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x4c  ldarg.0
0x4d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x52  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/Wall.Control.j"...
0x57  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x5c  ldarg.0
0x5d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x62  ldstr    aStaticControls// "/_static/_controls/SearchWidget/Externa"...
0x67  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x6c  ldarg.0
0x6d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x72  ldstr    aToolsKnowledge// "/tools/knowledgemanagement/kmsettingswi"...
0x77  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7c  ret
```
