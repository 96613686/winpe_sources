# Microsoft.Crm.Service.ObjectModel.ResourceGroupService::Delete

- ea: `0x13b20`
- end: `0x13b2b`
- name: `Microsoft.Crm.Service.ObjectModel.ResourceGroupService::Delete`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, service_task, broker_com_uri`

## string_xrefs

- `0x13b20`: `Delete method is not supported on pointer records.`

## pseudocode

```c

```

## disassembly

```asm
0x13b20  ldstr    aDeleteMethodIs// "Delete method is not supported on point"...
0x13b25  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x13b2a  throw
```
