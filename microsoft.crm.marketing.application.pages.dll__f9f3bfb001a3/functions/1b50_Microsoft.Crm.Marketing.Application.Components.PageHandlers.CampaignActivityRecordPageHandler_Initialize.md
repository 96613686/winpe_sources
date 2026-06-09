# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::Initialize

- ea: `0x1b50`
- end: `0x1b6f`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::Initialize`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1b50  ldarg.0
0x1b51  ldarg.1
0x1b52  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::Initialize(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager)
0x1b57  ldarg.1
0x1b58  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x1b5d  newobj   instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.CampaignActivityRecordPageParameterControl::.ctor()
0x1b62  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x1b67  ldarg.0
0x1b68  ldarg.1
0x1b69  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.PageManager Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::_pageManager
0x1b6e  ret
```
