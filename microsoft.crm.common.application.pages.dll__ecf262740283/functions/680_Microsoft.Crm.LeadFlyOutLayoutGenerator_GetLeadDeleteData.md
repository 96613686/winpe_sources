# Microsoft.Crm.LeadFlyOutLayoutGenerator::GetLeadDeleteData

- ea: `0x680`
- end: `0x6a1`
- name: `Microsoft.Crm.LeadFlyOutLayoutGenerator::GetLeadDeleteData`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x220`

## string_xrefs

- `0x686`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x680  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.LeadFlyOutJsonWrapper::.ctor()
0x685  dup
0x686  ldstr    aDelete// "Delete"
0x68b  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.LeadFlyOutJsonWrapper::LeadActionName
0x690  dup
0x691  ldstr    aLead// "lead"
0x696  call     string [Microsoft.Crm.Application.Pages]Microsoft.Crm.FlyoutUtil::GetDeleteFlyoutLayout(string)
0x69b  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.LeadFlyOutJsonWrapper::DivLayout
0x6a0  ret
```
