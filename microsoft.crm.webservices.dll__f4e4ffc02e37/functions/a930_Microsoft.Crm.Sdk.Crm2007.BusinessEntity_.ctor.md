# Microsoft.Crm.Sdk.Crm2007.BusinessEntity::.ctor

- ea: `0xa930`
- end: `0xa93c`
- name: `Microsoft.Crm.Sdk.Crm2007.BusinessEntity::.ctor`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10`

## string_xrefs

- `0xa931`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xa930  ldarg.0
0xa931  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0xa936  call     instance void Microsoft.Crm.Sdk.BusinessEntityBase::.ctor(string typeNamespace)
0xa93b  ret
```
