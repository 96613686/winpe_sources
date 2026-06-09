# Microsoft.Crm.Sdk.Crm2006.BusinessEntityCollection::.ctor

- ea: `0xc390`
- end: `0xc39c`
- name: `Microsoft.Crm.Sdk.Crm2006.BusinessEntityCollection::.ctor`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2a0`

## string_xrefs

- `0xc391`: `http://schemas.microsoft.com/crm/2006/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xc390  ldarg.0
0xc391  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2006/W"...
0xc396  call     instance void Microsoft.Crm.Sdk.BusinessEntityCollectionBase::.ctor(string typeNamespace)
0xc39b  ret
```
