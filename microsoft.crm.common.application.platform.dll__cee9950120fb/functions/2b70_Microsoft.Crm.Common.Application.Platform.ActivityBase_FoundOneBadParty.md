# Microsoft.Crm.Common.Application.Platform.ActivityBase::FoundOneBadParty

- ea: `0x2b70`
- end: `0x2b8c`
- name: `Microsoft.Crm.Common.Application.Platform.ActivityBase::FoundOneBadParty`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2940`
- `0x2a30`

## callees

- `0x2b70`

## pseudocode

```c

```

## disassembly

```asm
0x2b70  ldarg.0
0x2b71  ldc.i4.2
0x2b72  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x2b77  brfalse.s loc_2B8A
0x2b79  ldarg.0
0x2b7a  ldc.i4.1
0x2b7b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x2b80  brfalse.s loc_2B8A
0x2b82  ldarg.0
0x2b83  ldc.i4.4
0x2b84  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x2b89  ret
0x2b8a  ldc.i4.0
0x2b8b  ret
```
