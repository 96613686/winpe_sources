# Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::.ctor

- ea: `0x2dbd0`
- end: `0x2dbed`
- name: `Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::.ctor`
- size: `29`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x290e0`
- `0x304f0`
- `0x31f00`
- `0x31f60`
- `0x32020`
- `0x34130`
- `0x34400`
- `0x34fb0`
- `0x35380`
- `0x35750`
- `0x38120`
- `0x3b270`
- `0x3b5f0`
- `0x3b820`

## callees

- `0x30830`
- `0x31390`

## string_xrefs

- `0x2dbe2`: `CompositeStepBase:#Microsoft.Crm.Workflow.ObjectModel`

## pseudocode

```c

```

## disassembly

```asm
0x2dbd0  ldarg.0
0x2dbd1  call     instance void Microsoft.Crm.Workflow.ObjectModel.StepBase::.ctor()
0x2dbd6  ldarg.0
0x2dbd7  newobj   instance void Microsoft.Crm.Workflow.ObjectModel.StepCollection::.ctor()
0x2dbdc  stfld    class Microsoft.Crm.Workflow.ObjectModel.StepCollection Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::steps
0x2dbe1  ldarg.0
0x2dbe2  ldstr    aCompositestepb// "CompositeStepBase:#Microsoft.Crm.Workfl"...
0x2dbe7  stfld    string Microsoft.Crm.Workflow.ObjectModel.StepBase::__class
0x2dbec  ret
```
