# Microsoft.Crm.Sdk.Crm2007.BusinessEntityCollection::.ctor_0

- ea: `0xa970`
- end: `0xa97e`
- name: `Microsoft.Crm.Sdk.Crm2007.BusinessEntityCollection::.ctor_0`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xabd0`

## callees

- `0x2c0`

## string_xrefs

- `0xa971`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xa970  ldarg.0
0xa971  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0xa976  ldarg.1
0xa977  ldarg.2
0xa978  call     instance void Microsoft.Crm.Sdk.BusinessEntityCollectionBase::.ctor(string typeNamespace, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection entityCollection, bool skipOuterNode)
0xa97d  ret
```
