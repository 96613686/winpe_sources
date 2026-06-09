# Microsoft.Crm.Sdk.Crm2009.BusinessEntity::.ctor

- ea: `0xa8d0`
- end: `0xa8dc`
- name: `Microsoft.Crm.Sdk.Crm2009.BusinessEntity::.ctor`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10`

## string_xrefs

- `0xa8d1`: `http://schemas.microsoft.com/crm/2009/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xa8d0  ldarg.0
0xa8d1  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/crm/2009/W"...
0xa8d6  call     instance void Microsoft.Crm.Sdk.BusinessEntityBase::.ctor(string typeNamespace)
0xa8db  ret
```
