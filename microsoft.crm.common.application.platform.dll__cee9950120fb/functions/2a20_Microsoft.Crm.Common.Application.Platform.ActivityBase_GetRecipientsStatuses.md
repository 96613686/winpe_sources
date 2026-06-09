# Microsoft.Crm.Common.Application.Platform.ActivityBase::GetRecipientsStatuses

- ea: `0x2a20`
- end: `0x2a27`
- name: `Microsoft.Crm.Common.Application.Platform.ActivityBase::GetRecipientsStatuses`
- size: `7`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3ea0`
- `0x4110`
- `0x6ca0`

## callees

- `0x2a30`

## pseudocode

```c

```

## disassembly

```asm
0x2a20  ldarg.0
0x2a21  call     valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PartyStatusType Microsoft.Crm.Common.Application.Platform.ActivityBase::GetRecipientsStatusType(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity)
0x2a26  ret
```
