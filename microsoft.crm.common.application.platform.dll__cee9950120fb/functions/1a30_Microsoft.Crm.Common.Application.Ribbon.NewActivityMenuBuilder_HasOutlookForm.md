# Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::HasOutlookForm

- ea: `0x1a30`
- end: `0x1a4b`
- name: `Microsoft.Crm.Common.Application.Ribbon.NewActivityMenuBuilder::HasOutlookForm`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x19b0`

## callees

- `0x1a30`

## pseudocode

```c

```

## disassembly

```asm
0x1a30  ldarg.1
0x1a31  ldc.i4   0x1069
0x1a36  beq.s    loc_1A49
0x1a38  ldarg.1
0x1a39  ldc.i4   0x1074
0x1a3e  beq.s    loc_1A49
0x1a40  ldarg.1
0x1a41  ldc.i4   0x106A
0x1a46  ceq
0x1a48  ret
0x1a49  ldc.i4.1
0x1a4a  ret
```
