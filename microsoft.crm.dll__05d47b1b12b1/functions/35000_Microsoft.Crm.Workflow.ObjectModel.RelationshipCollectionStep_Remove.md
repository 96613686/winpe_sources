# Microsoft.Crm.Workflow.ObjectModel.RelationshipCollectionStep::Remove

- ea: `0x35000`
- end: `0x3501b`
- name: `Microsoft.Crm.Workflow.ObjectModel.RelationshipCollectionStep::Remove`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x28fa0`
- `0x2dc90`

## string_xrefs

- `0x35009`: `Cannot remove a non Relationship step`

## pseudocode

```c

```

## disassembly

```asm
0x35000  ldarg.1
0x35001  isinst   Microsoft.Crm.Workflow.ObjectModel.RelationshipStep
0x35006  ldnull
0x35007  cgt.un
0x35009  ldstr    aCannotRemoveAN_1// "Cannot remove a non Relationship step"
0x3500e  call     void Microsoft.Crm.Workflow.Utils.ExceptionUtility::Assert(bool condition, string message)
0x35013  ldarg.0
0x35014  ldarg.1
0x35015  call     instance void Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::Remove(class Microsoft.Crm.Workflow.ObjectModel.StepBase stepBase)
0x3501a  ret
```
