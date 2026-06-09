# Microsoft.Crm.Sdk.Crm2007.Response::.ctor

- ea: `0xaa50`
- end: `0xaa5c`
- name: `Microsoft.Crm.Sdk.Crm2007.Response::.ctor`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa9f0`

## callees

- `0x6290`

## string_xrefs

- `0xaa51`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xaa50  ldarg.0
0xaa51  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/W"...
0xaa56  call     instance void Microsoft.Crm.Sdk.ResponseBase::.ctor(string typeNamespace)
0xaa5b  ret
```
