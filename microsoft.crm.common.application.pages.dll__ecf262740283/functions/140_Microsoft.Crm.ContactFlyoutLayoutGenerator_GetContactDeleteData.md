# Microsoft.Crm.ContactFlyoutLayoutGenerator::GetContactDeleteData

- ea: `0x140`
- end: `0x161`
- name: `Microsoft.Crm.ContactFlyoutLayoutGenerator::GetContactDeleteData`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0xd0`

## string_xrefs

- `0x146`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x140  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ContactFlyOutJsonWrapper::.ctor()
0x145  dup
0x146  ldstr    aDelete// "Delete"
0x14b  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ContactFlyOutJsonWrapper::ActionName
0x150  dup
0x151  ldstr    aContact// "contact"
0x156  call     string [Microsoft.Crm.Application.Pages]Microsoft.Crm.FlyoutUtil::GetDeleteFlyoutLayout(string)
0x15b  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ContactFlyOutJsonWrapper::DivLayout
0x160  ret
```
