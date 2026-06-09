# Microsoft.Crm.Sdk.Crm2006.BusinessEntity::.ctor

- ea: `0xc360`
- end: `0xc36c`
- name: `Microsoft.Crm.Sdk.Crm2006.BusinessEntity::.ctor`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10`

## string_xrefs

- `0xc361`: `http://schemas.microsoft.com/crm/2006/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xc360  ldarg.0
0xc361  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2006/W"...
0xc366  call     instance void Microsoft.Crm.Sdk.BusinessEntityBase::.ctor(string typeNamespace)
0xc36b  ret
```
