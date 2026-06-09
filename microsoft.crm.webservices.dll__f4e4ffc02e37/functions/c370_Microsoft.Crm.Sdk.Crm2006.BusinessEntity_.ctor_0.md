# Microsoft.Crm.Sdk.Crm2006.BusinessEntity::.ctor_0

- ea: `0xc370`
- end: `0xc37e`
- name: `Microsoft.Crm.Sdk.Crm2006.BusinessEntity::.ctor_0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x50`

## string_xrefs

- `0xc371`: `http://schemas.microsoft.com/crm/2006/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xc370  ldarg.0
0xc371  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2006/W"...
0xc376  ldarg.1
0xc377  ldarg.2
0xc378  call     instance void Microsoft.Crm.Sdk.BusinessEntityBase::.ctor(string typeNamespace, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity entity, bool skipOuterNode)
0xc37d  ret
```
