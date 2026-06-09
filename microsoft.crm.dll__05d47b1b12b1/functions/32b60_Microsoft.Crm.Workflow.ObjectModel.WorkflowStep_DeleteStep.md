# Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::DeleteStep

- ea: `0x32b60`
- end: `0x32bb8`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::DeleteStep`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x28f90`
- `0x2dbf0`
- `0x2dc90`
- `0x308c0`
- `0x30900`
- `0x312e0`
- `0x32b60`

## string_xrefs

- `0x32b64`: `Cannot remove workflow step`
- `0x32b84`: `This step cannot be deleted. It is not part of this workflow`
- `0x32ba7`: `This step cannot be deleted. It is not part of this workflow`

## pseudocode

```c

```

## disassembly

```asm
0x32b60  ldarg.1
0x32b61  ldarg.0
0x32b62  bne.un.s loc_32B6E
0x32b64  ldstr    aCannotRemoveWo// "Cannot remove workflow step"
0x32b69  call     void Microsoft.Crm.Workflow.Utils.ExceptionUtility::ThrowException(string message)
0x32b6e  ldarg.1
0x32b6f  callvirt instance class Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x32b74  ldarg.0
0x32b75  bne.un.s loc_32B84
0x32b77  ldarg.1
0x32b78  callvirt instance class Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x32b7d  isinst   Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x32b82  brtrue.s loc_32B8E
0x32b84  ldstr    aThisStepCannot// "This step cannot be deleted. It is not "...
0x32b89  call     void Microsoft.Crm.Workflow.Utils.ExceptionUtility::ThrowException(string message)
0x32b8e  ldarg.1
0x32b8f  callvirt instance class Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x32b94  castclass Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x32b99  dup
0x32b9a  callvirt instance class Microsoft.Crm.Workflow.ObjectModel.StepCollection Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x32b9f  ldarg.1
0x32ba0  callvirt instance bool Microsoft.Crm.Workflow.ObjectModel.StepCollection::Contains(class Microsoft.Crm.Workflow.ObjectModel.StepBase item)
0x32ba5  brtrue.s loc_32BB1
0x32ba7  ldstr    aThisStepCannot// "This step cannot be deleted. It is not "...
0x32bac  call     void Microsoft.Crm.Workflow.Utils.ExceptionUtility::ThrowException(string message)
0x32bb1  ldarg.1
0x32bb2  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::Remove(class Microsoft.Crm.Workflow.ObjectModel.StepBase stepBase)
0x32bb7  ret
```
