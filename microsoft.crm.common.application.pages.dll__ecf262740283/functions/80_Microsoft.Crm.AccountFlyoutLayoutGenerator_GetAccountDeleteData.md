# Microsoft.Crm.AccountFlyoutLayoutGenerator::GetAccountDeleteData

- ea: `0x80`
- end: `0xa1`
- name: `Microsoft.Crm.AccountFlyoutLayoutGenerator::GetAccountDeleteData`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10`

## string_xrefs

- `0x86`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x80  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AccountFlyOutJsonWrapper::.ctor()
0x85  dup
0x86  ldstr    aDelete// "Delete"
0x8b  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AccountFlyOutJsonWrapper::ActionName
0x90  dup
0x91  ldstr    aAccount// "account"
0x96  call     string [Microsoft.Crm.Application.Pages]Microsoft.Crm.FlyoutUtil::GetDeleteFlyoutLayout(string)
0x9b  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AccountFlyOutJsonWrapper::DivLayout
0xa0  ret
```
