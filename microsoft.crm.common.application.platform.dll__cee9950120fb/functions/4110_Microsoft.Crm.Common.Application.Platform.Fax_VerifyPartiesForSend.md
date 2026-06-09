# Microsoft.Crm.Common.Application.Platform.Fax::VerifyPartiesForSend

- ea: `0x4110`
- end: `0x4122`
- name: `Microsoft.Crm.Common.Application.Platform.Fax::VerifyPartiesForSend`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x40d0`

## callees

- `0x2a20`
- `0x4110`

## pseudocode

```c

```

## disassembly

```asm
0x4110  ldarg.0
0x4111  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PartyStatusType Microsoft.Crm.Common.Application.Platform.ActivityBase::GetRecipientsStatuses()
0x4116  ldc.i4.4
0x4117  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x411c  brfalse.s loc_4120
0x411e  ldc.i4.0
0x411f  ret
0x4120  ldc.i4.1
0x4121  ret
```
