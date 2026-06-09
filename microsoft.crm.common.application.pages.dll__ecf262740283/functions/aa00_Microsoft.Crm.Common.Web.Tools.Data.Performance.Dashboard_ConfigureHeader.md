# Microsoft.Crm.Common.Web.Tools.Data.Performance.Dashboard::ConfigureHeader

- ea: `0xaa00`
- end: `0xaa2d`
- name: `Microsoft.Crm.Common.Web.Tools.Data.Performance.Dashboard::ConfigureHeader`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0xaa22`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`

## pseudocode

```c

```

## disassembly

```asm
0xaa00  ldarg.0
0xaa01  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ConfigureHeader()
0xaa06  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::.ctor()
0xaa0b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0xaa10  ldarg.0
0xaa11  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa16  ldc.i4.1
0xaa17  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0xaa1c  ldarg.0
0xaa1d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa22  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/jquery_ui_1.8."...
0xaa27  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xaa2c  ret
```
