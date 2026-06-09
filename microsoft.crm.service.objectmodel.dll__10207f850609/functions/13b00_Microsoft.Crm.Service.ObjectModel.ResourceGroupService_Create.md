# Microsoft.Crm.Service.ObjectModel.ResourceGroupService::Create

- ea: `0x13b00`
- end: `0x13b0b`
- name: `Microsoft.Crm.Service.ObjectModel.ResourceGroupService::Create`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x13b00`: `Create method is not supported on pointer records.`

## pseudocode

```c

```

## disassembly

```asm
0x13b00  ldstr    aCreateMethodIs// "Create method is not supported on point"...
0x13b05  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x13b0a  throw
```
