# Microsoft.Crm.Service.Application.Components.EntityPageHeaders.QueueConfigHeader::UpdateConfigHeaderForEntityRecord

- ea: `0xc580`
- end: `0xc59c`
- name: `Microsoft.Crm.Service.Application.Components.EntityPageHeaders.QueueConfigHeader::UpdateConfigHeaderForEntityRecord`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0xc5a0`

## string_xrefs

- `0xc589`: `MailboxService`

## pseudocode

```c

```

## disassembly

```asm
0xc580  ldarg.0
0xc581  ldarg.1
0xc582  ldarg.2
0xc583  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderBase::UpdateConfigHeaderForEntityRecord(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0xc588  ldarg.1
0xc589  ldstr    aMailboxservice// "MailboxService"
0xc58e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xc593  ldarg.0
0xc594  ldarg.1
0xc595  ldarg.2
0xc596  call     instance void Microsoft.Crm.Service.Application.Components.EntityPageHeaders.QueueConfigHeader::AddDefaultMailboxVariable(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager header, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity)
0xc59b  ret
```
