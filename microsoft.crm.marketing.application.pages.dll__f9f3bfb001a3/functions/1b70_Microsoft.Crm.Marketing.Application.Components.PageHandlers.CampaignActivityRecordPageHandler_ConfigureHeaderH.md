# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::ConfigureHeaderHandler

- ea: `0x1b70`
- end: `0x1b92`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::ConfigureHeaderHandler`
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
0x1b70  ldarg.0
0x1b71  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ConfigureHeaderHandler()
0x1b76  ldc.i4   0x1132
0x1b7b  call     class [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderFactory::GetConfigHeader(int32)
0x1b80  ldarg.0
0x1b81  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x1b86  ldarg.0
0x1b87  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x1b8c  callvirt instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.EntityPageHeaders.IConfigHeader::ConfigHeader(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x1b91  ret
```
