# Microsoft.Crm.Sdk.Crm2007.BusinessEntityCollection::.ctor

- ea: `0xa960`
- end: `0xa96c`
- name: `Microsoft.Crm.Sdk.Crm2007.BusinessEntityCollection::.ctor`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2a0`

## string_xrefs

- `0xa961`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xa960  ldarg.0
0xa961  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0xa966  call     instance void Microsoft.Crm.Sdk.BusinessEntityCollectionBase::.ctor(string typeNamespace)
0xa96b  ret
```
