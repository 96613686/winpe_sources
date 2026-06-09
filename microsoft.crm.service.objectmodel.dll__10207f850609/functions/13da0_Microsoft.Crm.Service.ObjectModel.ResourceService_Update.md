# Microsoft.Crm.Service.ObjectModel.ResourceService::Update

- ea: `0x13da0`
- end: `0x13dab`
- name: `Microsoft.Crm.Service.ObjectModel.ResourceService::Update`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x13da0`: `Update method is not supported on pointer records.`

## pseudocode

```c

```

## disassembly

```asm
0x13da0  ldstr    aUpdateMethodIs// "Update method is not supported on point"...
0x13da5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x13daa  throw
```
