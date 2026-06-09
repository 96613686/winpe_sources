# Microsoft.Crm.Workflow.ObjectModel.EntityStep::Remove

- ea: `0x34210`
- end: `0x3422b`
- name: `Microsoft.Crm.Workflow.ObjectModel.EntityStep::Remove`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x28fa0`
- `0x2dc90`

## string_xrefs

- `0x34219`: `Cannot remove a non stage step`

## pseudocode

```c

```

## disassembly

```asm
0x34210  ldarg.1
0x34211  isinst   Microsoft.Crm.Workflow.ObjectModel.StageStep
0x34216  ldnull
0x34217  cgt.un
0x34219  ldstr    aCannotRemoveAN// "Cannot remove a non stage step"
0x3421e  call     void Microsoft.Crm.Workflow.Utils.ExceptionUtility::Assert(bool condition, string message)
0x34223  ldarg.0
0x34224  ldarg.1
0x34225  call     instance void Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::Remove(class Microsoft.Crm.Workflow.ObjectModel.StepBase stepBase)
0x3422a  ret
```
