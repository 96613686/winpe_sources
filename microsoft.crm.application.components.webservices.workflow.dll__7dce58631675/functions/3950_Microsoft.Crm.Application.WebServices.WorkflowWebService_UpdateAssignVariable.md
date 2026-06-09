# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateAssignVariable

- ea: `0x3950`
- end: `0x3982`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateAssignVariable`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x34c0`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x3950  ldarg.0
0x3951  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x3956  ldarg.3
0x3957  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x395c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x3961  stloc.0
0x3962  ldloc.0
0x3963  ldarg.1
0x3964  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x3969  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep
0x396e  stloc.1
0x396f  ldarg.0
0x3970  ldloc.0
0x3971  ldarg.s  4
0x3973  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x3978  ldarg.0
0x3979  ldloc.1
0x397a  ldarg.2
0x397b  ldloc.0
0x397c  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateAssign(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase assignStep, string assignXml, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x3981  ret
```
