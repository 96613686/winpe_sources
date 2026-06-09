# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertStopWorkflowStep

- ea: `0x5dd0`
- end: `0x5e1b`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertStopWorkflowStep`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x5dd0`
- `0x8b90`
- `0x8f00`
- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x5dd0  ldarg.0
0x5dd1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x5dd6  ldarg.2
0x5dd7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5ddc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x5de1  stloc.0
0x5de2  ldloc.0
0x5de3  ldarg.1
0x5de4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x5de9  ldarg.0
0x5dea  ldloc.0
0x5deb  ldarg.3
0x5dec  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x5df1  ldloc.0
0x5df2  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x5df7  stloc.1
0x5df8  ldarg.0
0x5df9  ldarg.s  4
0x5dfb  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x5e00  ldloc.1
0x5e01  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x5e06  ldarg.0
0x5e07  ldloc.0
0x5e08  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x5e0d  stloc.2
0x5e0e  leave.s  loc_5E19
0x5e10  stloc.3
0x5e11  ldarg.0
0x5e12  ldloc.3
0x5e13  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x5e18  throw
0x5e19  ldloc.2
0x5e1a  ret
```
