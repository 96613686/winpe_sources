# Microsoft.Crm.Workflow.WorkflowVariableRenameVisitor::VisitChildren

- ea: `0x4510`
- end: `0x4539`
- name: `Microsoft.Crm.Workflow.WorkflowVariableRenameVisitor::VisitChildren`
- size: `41`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3ee0`
- `0x3ff0`
- `0x4020`
- `0x40a0`
- `0x40c0`
- `0x4250`
- `0x4270`
- `0x4280`

## callees

- `0x4510`

## pseudocode

```c

```

## disassembly

```asm
0x4510  ldc.i4.0
0x4511  stloc.0
0x4512  br.s     loc_452A
0x4514  ldarg.1
0x4515  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x451a  ldloc.0
0x451b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Item(int32)
0x4520  ldarg.0
0x4521  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::Apply(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepVisitorBase)
0x4526  ldloc.0
0x4527  ldc.i4.1
0x4528  add
0x4529  stloc.0
0x452a  ldloc.0
0x452b  ldarg.1
0x452c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x4531  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Count()
0x4536  blt.s    loc_4514
0x4538  ret
```
