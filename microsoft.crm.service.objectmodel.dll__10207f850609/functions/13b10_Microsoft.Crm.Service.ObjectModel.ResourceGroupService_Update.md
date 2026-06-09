# Microsoft.Crm.Service.ObjectModel.ResourceGroupService::Update

- ea: `0x13b10`
- end: `0x13b1b`
- name: `Microsoft.Crm.Service.ObjectModel.ResourceGroupService::Update`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x13b10`: `Update method is not supported on pointer records.`

## pseudocode

```c

```

## disassembly

```asm
0x13b10  ldstr    aUpdateMethodIs// "Update method is not supported on point"...
0x13b15  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x13b1a  throw
```
