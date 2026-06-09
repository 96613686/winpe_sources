# Microsoft.Crm.Sdk.Crm2009.BusinessEntityCollection::.ctor_0

- ea: `0xa910`
- end: `0xa91e`
- name: `Microsoft.Crm.Sdk.Crm2009.BusinessEntityCollection::.ctor_0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2c0`

## string_xrefs

- `0xa911`: `http://schemas.microsoft.com/crm/2009/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xa910  ldarg.0
0xa911  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/crm/2009/W"...
0xa916  ldarg.1
0xa917  ldarg.2
0xa918  call     instance void Microsoft.Crm.Sdk.BusinessEntityCollectionBase::.ctor(string typeNamespace, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection entityCollection, bool skipOuterNode)
0xa91d  ret
```
