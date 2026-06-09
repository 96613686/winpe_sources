# Microsoft.Crm.Service.ObjectModel.ResourceService::Create

- ea: `0x13d90`
- end: `0x13d9b`
- name: `Microsoft.Crm.Service.ObjectModel.ResourceService::Create`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x13d90`: `Create method is not supported on pointer records.`

## pseudocode

```c

```

## disassembly

```asm
0x13d90  ldstr    aCreateMethodIs// "Create method is not supported on point"...
0x13d95  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x13d9a  throw
```
