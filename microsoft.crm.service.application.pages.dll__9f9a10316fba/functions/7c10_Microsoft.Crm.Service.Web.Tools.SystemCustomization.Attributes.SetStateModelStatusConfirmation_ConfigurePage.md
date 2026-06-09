# Microsoft.Crm.Service.Web.Tools.SystemCustomization.Attributes.SetStateModelStatusConfirmation::ConfigurePage

- ea: `0x7c10`
- end: `0x7c47`
- name: `Microsoft.Crm.Service.Web.Tools.SystemCustomization.Attributes.SetStateModelStatusConfirmation::ConfigurePage`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x7c3c`: `/_common/styles/dialogs.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x7c10  ldarg.0
0x7c11  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x7c16  ldarg.0
0x7c17  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7c1c  ldstr    aStaticToolsSys// "/_static/tools/systemcustomization/scri"...
0x7c21  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7c26  ldarg.0
0x7c27  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7c2c  ldstr    aStaticToolsSol_0// "/_static/tools/solution/scripts/StatusR"...
0x7c31  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7c36  ldarg.0
0x7c37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7c3c  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x7c41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x7c46  ret
```
