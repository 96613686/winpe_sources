# Microsoft.Crm.Sdk.Crm2009.BusinessEntity::.ctor_0

- ea: `0xa8e0`
- end: `0xa8ee`
- name: `Microsoft.Crm.Sdk.Crm2009.BusinessEntity::.ctor_0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x50`

## string_xrefs

- `0xa8e1`: `http://schemas.microsoft.com/crm/2009/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xa8e0  ldarg.0
0xa8e1  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/crm/2009/W"...
0xa8e6  ldarg.1
0xa8e7  ldarg.2
0xa8e8  call     instance void Microsoft.Crm.Sdk.BusinessEntityBase::.ctor(string typeNamespace, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity entity, bool skipOuterNode)
0xa8ed  ret
```
