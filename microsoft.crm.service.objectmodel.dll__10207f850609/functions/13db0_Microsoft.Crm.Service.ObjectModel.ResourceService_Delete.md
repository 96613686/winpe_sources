# Microsoft.Crm.Service.ObjectModel.ResourceService::Delete

- ea: `0x13db0`
- end: `0x13dbb`
- name: `Microsoft.Crm.Service.ObjectModel.ResourceService::Delete`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, service_task, broker_com_uri`

## string_xrefs

- `0x13db0`: `Delete method is not supported on pointer records.`

## pseudocode

```c

```

## disassembly

```asm
0x13db0  ldstr    aDeleteMethodIs// "Delete method is not supported on point"...
0x13db5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x13dba  throw
```
