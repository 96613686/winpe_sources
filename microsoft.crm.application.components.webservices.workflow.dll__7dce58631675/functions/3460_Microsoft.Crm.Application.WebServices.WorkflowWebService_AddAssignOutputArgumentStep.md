# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddAssignOutputArgumentStep

- ea: `0x3460`
- end: `0x347a`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddAssignOutputArgumentStep`
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
0x3460  ldarg.0
0x3461  ldarg.2
0x3462  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.WebServices.WorkflowWebService::GetWorkflowStep(string entityId)
0x3467  stloc.0
0x3468  ldloc.0
0x3469  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x346e  stloc.1
0x346f  ldarg.0
0x3470  ldarg.1
0x3471  ldarg.3
0x3472  ldloc.1
0x3473  ldloc.0
0x3474  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::AddAssignStep(string parentId, string descriptionXml, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase assignStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x3479  ret
```
