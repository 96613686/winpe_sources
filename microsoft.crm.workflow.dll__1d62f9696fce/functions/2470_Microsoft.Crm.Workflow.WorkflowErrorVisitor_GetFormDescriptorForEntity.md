# Microsoft.Crm.Workflow.WorkflowErrorVisitor::GetFormDescriptorForEntity

- ea: `0x2470`
- end: `0x248e`
- name: `Microsoft.Crm.Workflow.WorkflowErrorVisitor::GetFormDescriptorForEntity`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x2490`
- `0x24a0`

## callees

- `0x1300`
- `0x1ca0`
- `0x1d80`
- `0x2470`

## pseudocode

```c

```

## disassembly

```asm
0x2470  ldnull
0x2471  stloc.0
0x2472  ldarg.0
0x2473  call     instance class Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext Microsoft.Crm.Workflow.WorkflowErrorVisitor::get_ErrorVisitorContext()
0x2478  ldarg.1
0x2479  callvirt instance object Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext::GetFormDescriptorForEntity(string entityName)
0x247e  stloc.0
0x247f  leave.s  loc_248C
0x2481  pop
0x2482  ldarg.2
0x2483  ldc.i4.4
0x2484  ldarg.0
0x2485  call     void Microsoft.Crm.Workflow.WorkflowErrorHelper::UpdateErrorMap(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase workflowStep, valuetype Microsoft.Crm.Workflow.WorkflowErrorTypes errorType, class Microsoft.Crm.Workflow.WorkflowErrorVisitor errorVisitor)
0x248a  leave.s  loc_248C
0x248c  ldloc.0
0x248d  ret
```
