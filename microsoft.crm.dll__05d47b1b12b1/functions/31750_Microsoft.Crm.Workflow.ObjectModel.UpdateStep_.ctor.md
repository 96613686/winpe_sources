# Microsoft.Crm.Workflow.ObjectModel.UpdateStep::.ctor

- ea: `0x31750`
- end: `0x31779`
- name: `Microsoft.Crm.Workflow.ObjectModel.UpdateStep::.ctor`
- size: `41`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2c300`
- `0x2e460`
- `0x2f010`
- `0x31780`

## callees

- `0x28f20`
- `0x30830`
- `0x309f0`
- `0x330e0`

## string_xrefs

- `0x3176e`: `UpdateStep:#Microsoft.Crm.Workflow.ObjectModel`

## pseudocode

```c

```

## disassembly

```asm
0x31750  ldarg.0
0x31751  call     instance void Microsoft.Crm.Workflow.ObjectModel.StepBase::.ctor()
0x31756  ldarg.1
0x31757  ldstr    aWorkflowstep// "workflowStep"
0x3175c  call     void Microsoft.Crm.Workflow.Utils.ExceptionUtility::ThrowIfNull(object expression, string message)
0x31761  ldarg.0
0x31762  ldarg.1
0x31763  callvirt instance string Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetNextStepId()
0x31768  call     instance void Microsoft.Crm.Workflow.ObjectModel.StepBase::SetNameAndId(string stepId)
0x3176d  ldarg.0
0x3176e  ldstr    aUpdatestepMicr// "UpdateStep:#Microsoft.Crm.Workflow.Obje"...
0x31773  stfld    string Microsoft.Crm.Workflow.ObjectModel.StepBase::__class
0x31778  ret
```
