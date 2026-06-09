# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateAssignOutputArgument

- ea: `0x3590`
- end: `0x35c2`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateAssignOutputArgument`
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
0x3590  ldarg.0
0x3591  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x3596  ldarg.3
0x3597  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x359c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x35a1  stloc.0
0x35a2  ldloc.0
0x35a3  ldarg.1
0x35a4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x35a9  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignOutputArgumentStep
0x35ae  stloc.1
0x35af  ldarg.0
0x35b0  ldloc.0
0x35b1  ldarg.s  4
0x35b3  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x35b8  ldarg.0
0x35b9  ldloc.1
0x35ba  ldarg.2
0x35bb  ldloc.0
0x35bc  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateAssign(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase assignStep, string assignXml, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x35c1  ret
```
