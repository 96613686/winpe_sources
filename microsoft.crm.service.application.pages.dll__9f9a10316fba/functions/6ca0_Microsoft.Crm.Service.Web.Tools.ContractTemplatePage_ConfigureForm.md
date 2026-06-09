# Microsoft.Crm.Service.Web.Tools.ContractTemplatePage::ConfigureForm

- ea: `0x6ca0`
- end: `0x6ce5`
- name: `Microsoft.Crm.Service.Web.Tools.ContractTemplatePage::ConfigureForm`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x6ccf`: `_bReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0x6ca0  ldarg.0
0x6ca1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x6ca6  ldc.i4.4
0x6ca7  ldarg.0
0x6ca8  ldftn    instance void Microsoft.Crm.Service.Web.Tools.ContractTemplatePage::DisableForm(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x6cae  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x6cb3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterAfterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x6cb8  ldarg.0
0x6cb9  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x6cbe  ldarg.0
0x6cbf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x6cc4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x6cc9  ldarg.0
0x6cca  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6ccf  ldstr    aBreadonly// "_bReadOnly"
0x6cd4  ldarg.0
0x6cd5  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x6cda  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_ReadOnly()
0x6cdf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x6ce4  ret
```
