# Microsoft.Crm.Common.Application.Platform.QueryDecorators.QueryDecorator::Decorator

- ea: `0x7280`
- end: `0x7292`
- name: `Microsoft.Crm.Common.Application.Platform.QueryDecorators.QueryDecorator::Decorator`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x6ee0`
- `0x6ef0`

## pseudocode

```c

```

## disassembly

```asm
0x7280  ldarg.1
0x7281  ldarg.2
0x7282  ldarg.3
0x7283  ldarg.s  4
0x7285  call     class Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::GetInstance(string dateFilter, string stateGroup, string actualEnd, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x728a  ldarg.s  5
0x728c  callvirt instance void Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::DecorateQuery(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query)
0x7291  ret
```
