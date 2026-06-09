# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddAssignVariableStep

- ea: `0x3910`
- end: `0x392a`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddAssignVariableStep`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x3400`
- `0x3420`

## pseudocode

```c

```

## disassembly

```asm
0x3910  ldarg.0
0x3911  ldarg.2
0x3912  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.WebServices.WorkflowWebService::GetWorkflowStep(string entityId)
0x3917  stloc.0
0x3918  ldloc.0
0x3919  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x391e  stloc.1
0x391f  ldarg.0
0x3920  ldarg.1
0x3921  ldarg.3
0x3922  ldloc.1
0x3923  ldloc.0
0x3924  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::AddAssignStep(string parentId, string descriptionXml, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase assignStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x3929  ret
```
