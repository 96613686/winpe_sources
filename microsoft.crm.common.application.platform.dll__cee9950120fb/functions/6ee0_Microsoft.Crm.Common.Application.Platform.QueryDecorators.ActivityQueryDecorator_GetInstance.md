# Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::GetInstance

- ea: `0x6ee0`
- end: `0x6eea`
- name: `Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::GetInstance`
- size: `10`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7280`

## callees

- `0x6eb0`

## pseudocode

```c

```

## disassembly

```asm
0x6ee0  ldarg.0
0x6ee1  ldarg.1
0x6ee2  ldarg.2
0x6ee3  ldarg.3
0x6ee4  newobj   instance void Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::.ctor(string dateFilter, string stateGroup, string actualEnd, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6ee9  ret
```
