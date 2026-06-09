# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::ConfigureFormHandler

- ea: `0x2300`
- end: `0x2345`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::ConfigureFormHandler`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x22f0`

## pseudocode

```c

```

## disassembly

```asm
0x2300  ldarg.0
0x2301  ldsfld   string [mscorlib]System.String::Empty
0x2306  call     instance void Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::set_NewItemScript(string value)
0x230b  ldarg.0
0x230c  ldarg.0
0x230d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x2312  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm
0x2317  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::crmCustomizableForm
0x231c  ldarg.0
0x231d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::crmCustomizableForm
0x2322  ldarg.0
0x2323  ldftn    instance void Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::CustomFields_DataBoundReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs e)
0x2329  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler::.ctor(object, native int)
0x232e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::add_DataBound(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler)
0x2333  ldarg.0
0x2334  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::crmCustomizableForm
0x2339  ldarg.0
0x233a  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x233f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x2344  ret
```
