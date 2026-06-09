# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::Initialize

- ea: `0x15a0`
- end: `0x15b8`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::Initialize`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x15a0  ldarg.0
0x15a1  ldarg.1
0x15a2  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::Initialize(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager)
0x15a7  ldarg.1
0x15a8  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x15ad  newobj   instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.CampaignRecordPageParameterControl::.ctor()
0x15b2  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x15b7  ret
```
