# Microsoft.Crm.Common.Application.Platform.Email::get_SenderStatus

- ea: `0x3300`
- end: `0x3317`
- name: `Microsoft.Crm.Common.Application.Platform.Email::get_SenderStatus`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3ea0`

## callees

- `0x2940`

## pseudocode

```c

```

## disassembly

```asm
0x3300  ldarg.0
0x3301  ldstr    aFrom// "from"
0x3306  call     instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x330b  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0x3310  ldnull
0x3311  call     valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PartyStatusType Microsoft.Crm.Common.Application.Platform.ActivityBase::CheckPartyStatus(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection parties, string activityLogicalName)
0x3316  ret
```
