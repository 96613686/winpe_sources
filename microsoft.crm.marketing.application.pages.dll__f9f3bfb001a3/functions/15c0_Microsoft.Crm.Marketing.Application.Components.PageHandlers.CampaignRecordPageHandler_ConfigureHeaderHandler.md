# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::ConfigureHeaderHandler

- ea: `0x15c0`
- end: `0x15e2`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignRecordPageHandler::ConfigureHeaderHandler`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x15c0  ldarg.0
0x15c1  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ConfigureHeaderHandler()
0x15c6  ldc.i4   0x1130
0x15cb  call     class [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderFactory::GetConfigHeader(int32)
0x15d0  ldarg.0
0x15d1  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x15d6  ldarg.0
0x15d7  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x15dc  callvirt instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeader::ConfigHeader(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x15e1  ret
```
