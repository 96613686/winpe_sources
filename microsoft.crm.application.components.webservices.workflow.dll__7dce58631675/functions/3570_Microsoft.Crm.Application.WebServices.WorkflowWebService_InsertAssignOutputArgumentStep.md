# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertAssignOutputArgumentStep

- ea: `0x3570`
- end: `0x358c`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertAssignOutputArgumentStep`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x3400`
- `0x3480`

## pseudocode

```c

```

## disassembly

```asm
0x3570  ldarg.0
0x3571  ldarg.2
0x3572  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.WebServices.WorkflowWebService::GetWorkflowStep(string entityId)
0x3577  stloc.0
0x3578  ldloc.0
0x3579  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x357e  stloc.1
0x357f  ldarg.0
0x3580  ldarg.1
0x3581  ldarg.3
0x3582  ldarg.s  4
0x3584  ldloc.1
0x3585  ldloc.0
0x3586  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertAssignStep(string siblingId, string descriptionXml, string direction, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase assignStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x358b  ret
```
