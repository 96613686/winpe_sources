# Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::.ctor

- ea: `0xf20`
- end: `0xf32`
- name: `Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::.ctor`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x45e0`

## pseudocode

```c

```

## disassembly

```asm
0xf20  ldarg.0
0xf21  ldarg.1
0xf22  ldarg.2
0xf23  ldarg.3
0xf24  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::.ctor(string, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf29  ldarg.0
0xf2a  ldarg.s  4
0xf2c  stfld    bool Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::_replaceLocalStrings
0xf31  ret
```
