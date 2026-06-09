# Microsoft.Crm.Workflow.ObjectModel.CreateStep::.ctor

- ea: `0x2e0b0`
- end: `0x2e0d9`
- name: `Microsoft.Crm.Workflow.ObjectModel.CreateStep::.ctor`
- size: `41`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x2c300`
- `0x2e170`

## callees

- `0x28f20`
- `0x30830`
- `0x309f0`
- `0x330e0`

## string_xrefs

- `0x2e0ce`: `CreateStep:#Microsoft.Crm.Workflow.ObjectModel`

## pseudocode

```c

```

## disassembly

```asm
0x2e0b0  ldarg.0
0x2e0b1  call     instance void Microsoft.Crm.Workflow.ObjectModel.StepBase::.ctor()
0x2e0b6  ldarg.1
0x2e0b7  ldstr    aWorkflowstep// "workflowStep"
0x2e0bc  call     void Microsoft.Crm.Workflow.Utils.ExceptionUtility::ThrowIfNull(object expression, string message)
0x2e0c1  ldarg.0
0x2e0c2  ldarg.1
0x2e0c3  callvirt instance string Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetNextStepId()
0x2e0c8  call     instance void Microsoft.Crm.Workflow.ObjectModel.StepBase::SetNameAndId(string stepId)
0x2e0cd  ldarg.0
0x2e0ce  ldstr    aCreatestepMicr// "CreateStep:#Microsoft.Crm.Workflow.Obje"...
0x2e0d3  stfld    string Microsoft.Crm.Workflow.ObjectModel.StepBase::__class
0x2e0d8  ret
```
