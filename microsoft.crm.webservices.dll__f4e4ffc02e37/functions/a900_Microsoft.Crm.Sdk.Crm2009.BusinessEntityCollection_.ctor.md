# Microsoft.Crm.Sdk.Crm2009.BusinessEntityCollection::.ctor

- ea: `0xa900`
- end: `0xa90c`
- name: `Microsoft.Crm.Sdk.Crm2009.BusinessEntityCollection::.ctor`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2a0`

## string_xrefs

- `0xa901`: `http://schemas.microsoft.com/crm/2009/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xa900  ldarg.0
0xa901  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/crm/2009/W"...
0xa906  call     instance void Microsoft.Crm.Sdk.BusinessEntityCollectionBase::.ctor(string typeNamespace)
0xa90b  ret
```
