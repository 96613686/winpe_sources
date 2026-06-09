# Microsoft.Crm.Application.Components.UI.CrmUIControl::.ctor

- ea: `0x24040`
- end: `0x24059`
- name: `Microsoft.Crm.Application.Components.UI.CrmUIControl::.ctor`
- size: `25`
- prototype: ``
- caller_count: `31`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6e0`
- `0xa970`
- `0xb590`
- `0x14e30`
- `0x14ef0`
- `0x14fc0`
- `0x15dd0`
- `0x178e0`
- `0x18010`
- `0x18040`
- `0x190c0`
- `0x1a010`
- `0x1a3b0`
- `0x1a3c0`
- `0x1a7f0`
- `0x1b410`
- `0x1ea30`
- `0x207c0`
- `0x20f30`
- `0x218f0`
- `0x21920`
- `0x21ad0`
- `0x23370`
- `0x23800`
- `0x23840`
- `0x24330`
- `0x24350`
- `0x259f0`
- `0x25a70`
- `0x25ed0`
- `0x260e0`

## callees

- `0x23ad0`

## pseudocode

```c

```

## disassembly

```asm
0x24040  ldarg.0
0x24041  ldc.i4.1
0x24042  stfld    bool Microsoft.Crm.Application.Components.UI.CrmUIControl::_includeControlsCss
0x24047  ldarg.0
0x24048  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x2404d  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.UI.CrmUIControl::_expandos
0x24052  ldarg.0
0x24053  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::.ctor()
0x24058  ret
```
