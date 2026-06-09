# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertAssignVariableStep

- ea: `0x3930`
- end: `0x394c`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertAssignVariableStep`
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
0x3930  ldarg.0
0x3931  ldarg.2
0x3932  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.WebServices.WorkflowWebService::GetWorkflowStep(string entityId)
0x3937  stloc.0
0x3938  ldloc.0
0x3939  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x393e  stloc.1
0x393f  ldarg.0
0x3940  ldarg.1
0x3941  ldarg.3
0x3942  ldarg.s  4
0x3944  ldloc.1
0x3945  ldloc.0
0x3946  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertAssignStep(string siblingId, string descriptionXml, string direction, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase assignStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x394b  ret
```
