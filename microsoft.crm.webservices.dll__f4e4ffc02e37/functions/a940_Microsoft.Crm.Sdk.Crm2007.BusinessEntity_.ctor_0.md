# Microsoft.Crm.Sdk.Crm2007.BusinessEntity::.ctor_0

- ea: `0xa940`
- end: `0xa94e`
- name: `Microsoft.Crm.Sdk.Crm2007.BusinessEntity::.ctor_0`
- size: `14`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x84f0`
- `0xab80`

## callees

- `0x50`

## string_xrefs

- `0xa941`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xa940  ldarg.0
0xa941  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0xa946  ldarg.1
0xa947  ldarg.2
0xa948  call     instance void Microsoft.Crm.Sdk.BusinessEntityBase::.ctor(string typeNamespace, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity entity, bool skipOuterNode)
0xa94d  ret
```
