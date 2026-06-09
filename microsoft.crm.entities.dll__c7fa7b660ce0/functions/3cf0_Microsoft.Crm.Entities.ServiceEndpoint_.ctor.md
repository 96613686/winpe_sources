# Microsoft.Crm.Entities.ServiceEndpoint::.ctor

- ea: `0x3cf0`
- end: `0x3cfd`
- name: `Microsoft.Crm.Entities.ServiceEndpoint::.ctor`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x3cf1`: `ServiceEndpoint`

## pseudocode

```c

```

## disassembly

```asm
0x3cf0  ldarg.0
0x3cf1  ldstr    aServiceendpoin// "ServiceEndpoint"
0x3cf6  ldarg.1
0x3cf7  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::.ctor(string, valuetype [mscorlib]System.Guid)
0x3cfc  ret
```
