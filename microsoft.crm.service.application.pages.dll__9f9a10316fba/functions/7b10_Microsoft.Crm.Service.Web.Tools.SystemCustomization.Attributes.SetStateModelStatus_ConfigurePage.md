# Microsoft.Crm.Service.Web.Tools.SystemCustomization.Attributes.SetStateModelStatus::ConfigurePage

- ea: `0x7b10`
- end: `0x7b47`
- name: `Microsoft.Crm.Service.Web.Tools.SystemCustomization.Attributes.SetStateModelStatus::ConfigurePage`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x7b3c`: `/_common/styles/dialogs.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x7b10  ldarg.0
0x7b11  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x7b16  ldarg.0
0x7b17  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7b1c  ldstr    aStaticToolsSys// "/_static/tools/systemcustomization/scri"...
0x7b21  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7b26  ldarg.0
0x7b27  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7b2c  ldstr    aStaticToolsSol_0// "/_static/tools/solution/scripts/StatusR"...
0x7b31  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7b36  ldarg.0
0x7b37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7b3c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x7b41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7b46  ret
```
