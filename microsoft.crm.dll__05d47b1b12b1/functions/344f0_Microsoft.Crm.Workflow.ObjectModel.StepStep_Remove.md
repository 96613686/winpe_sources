# Microsoft.Crm.Workflow.ObjectModel.StepStep::Remove

- ea: `0x344f0`
- end: `0x34516`
- name: `Microsoft.Crm.Workflow.ObjectModel.StepStep::Remove`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x28fa0`
- `0x2dc90`
- `0x344f0`

## string_xrefs

- `0x34504`: `Cannot remove a non Control/Action Step`

## pseudocode

```c

```

## disassembly

```asm
0x344f0  ldarg.1
0x344f1  isinst   Microsoft.Crm.Workflow.ObjectModel.ControlStep
0x344f6  brtrue.s loc_34503
0x344f8  ldarg.1
0x344f9  isinst   Microsoft.Crm.Workflow.ObjectModel.ActionStep
0x344fe  ldnull
0x344ff  cgt.un
0x34501  br.s     loc_34504
0x34503  ldc.i4.1
0x34504  ldstr    aCannotRemoveAN_0// "Cannot remove a non Control/Action Step"
0x34509  call     void Microsoft.Crm.Workflow.Utils.ExceptionUtility::Assert(bool condition, string message)
0x3450e  ldarg.0
0x3450f  ldarg.1
0x34510  call     instance void Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::Remove(class Microsoft.Crm.Workflow.ObjectModel.StepBase stepBase)
0x34515  ret
```
