# Microsoft.Crm.Application.WebServices.TransactionCurrencyExpressionProvider::.ctor

- ea: `0x1610`
- end: `0x161e`
- name: `Microsoft.Crm.Application.WebServices.TransactionCurrencyExpressionProvider::.ctor`
- size: `14`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xe60`
- `0x1370`

## callees

- `0x1600`

## pseudocode

```c

```

## disassembly

```asm
0x1610  ldarg.0
0x1611  call     instance void [mscorlib]System.Object::.ctor()
0x1616  ldarg.0
0x1617  ldarg.1
0x1618  call     instance void Microsoft.Crm.Application.WebServices.TransactionCurrencyExpressionProvider::set_OrganizationContext(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext value)
0x161d  ret
```
