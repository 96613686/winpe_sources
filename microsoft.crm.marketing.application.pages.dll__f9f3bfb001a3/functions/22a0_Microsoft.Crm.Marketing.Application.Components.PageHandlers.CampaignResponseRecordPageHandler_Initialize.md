# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::Initialize

- ea: `0x22a0`
- end: `0x22b8`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignResponseRecordPageHandler::Initialize`
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
0x22a0  ldarg.0
0x22a1  ldarg.1
0x22a2  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::Initialize(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager)
0x22a7  ldarg.1
0x22a8  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x22ad  newobj   instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.CampaignResponseRecordPageParameterControl::.ctor()
0x22b2  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x22b7  ret
```
