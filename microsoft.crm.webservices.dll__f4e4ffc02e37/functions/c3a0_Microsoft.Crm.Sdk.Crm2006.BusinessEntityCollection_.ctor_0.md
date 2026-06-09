# Microsoft.Crm.Sdk.Crm2006.BusinessEntityCollection::.ctor_0

- ea: `0xc3a0`
- end: `0xc3ae`
- name: `Microsoft.Crm.Sdk.Crm2006.BusinessEntityCollection::.ctor_0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2c0`

## string_xrefs

- `0xc3a1`: `http://schemas.microsoft.com/crm/2006/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xc3a0  ldarg.0
0xc3a1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2006/W"...
0xc3a6  ldarg.1
0xc3a7  ldarg.2
0xc3a8  call     instance void Microsoft.Crm.Sdk.BusinessEntityCollectionBase::.ctor(string typeNamespace, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection entityCollection, bool skipOuterNode)
0xc3ad  ret
```
