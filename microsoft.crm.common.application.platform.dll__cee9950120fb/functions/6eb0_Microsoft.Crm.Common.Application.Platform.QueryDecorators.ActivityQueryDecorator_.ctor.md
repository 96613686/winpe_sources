# Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::.ctor

- ea: `0x6eb0`
- end: `0x6ed4`
- name: `Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::.ctor`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x6ee0`

## pseudocode

```c

```

## disassembly

```asm
0x6eb0  ldarg.0
0x6eb1  call     instance void [mscorlib]System.Object::.ctor()
0x6eb6  ldarg.0
0x6eb7  ldarg.1
0x6eb8  stfld    string Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::_dateFilter
0x6ebd  ldarg.0
0x6ebe  ldarg.2
0x6ebf  stfld    string Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::_stateGroup
0x6ec4  ldarg.0
0x6ec5  ldarg.3
0x6ec6  stfld    string Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::_actualEnd
0x6ecb  ldarg.0
0x6ecc  ldarg.s  4
0x6ece  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::_context
0x6ed3  ret
```
