# Microsoft.Crm.Asynchronous.ALMSchemaMetadataDiscrepancyTask::.ctor

- ea: `0x6e0`
- end: `0x6ed`
- name: `Microsoft.Crm.Asynchronous.ALMSchemaMetadataDiscrepancyTask::.ctor`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3a0`

## callees

- `0x4c0`

## string_xrefs

- `0x6e2`: `ALMSchemaMetadataDiscrepancyTask`

## pseudocode

```c

```

## disassembly

```asm
0x6e0  ldarg.0
0x6e1  ldarg.1
0x6e2  ldstr    aAlmschemametad// "ALMSchemaMetadataDiscrepancyTask"
0x6e7  call     instance void Microsoft.Crm.Asynchronous.ALMAnomalyDetectionTaskBase::.ctor(valuetype [mscorlib]System.Guid organizationId, string taskName)
0x6ec  ret
```
