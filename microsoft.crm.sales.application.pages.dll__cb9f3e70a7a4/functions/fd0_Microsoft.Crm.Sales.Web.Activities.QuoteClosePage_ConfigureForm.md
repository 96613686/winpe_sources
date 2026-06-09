# Microsoft.Crm.Sales.Web.Activities.QuoteClosePage::ConfigureForm

- ea: `0xfd0`
- end: `0xfe2`
- name: `Microsoft.Crm.Sales.Web.Activities.QuoteClosePage::ConfigureForm`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xfd0  ldarg.0
0xfd1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xfd6  ldarg.0
0xfd7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0xfdc  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0xfe1  ret
```
