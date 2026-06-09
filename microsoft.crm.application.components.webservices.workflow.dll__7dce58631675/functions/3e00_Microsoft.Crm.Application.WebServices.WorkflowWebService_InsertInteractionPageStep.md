# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertInteractionPageStep

- ea: `0x3e00`
- end: `0x3e4b`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertInteractionPageStep`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x3e00`
- `0x8b90`
- `0x8f00`
- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x3e00  ldarg.0
0x3e01  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x3e06  ldarg.2
0x3e07  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3e0c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x3e11  stloc.0
0x3e12  ldloc.0
0x3e13  ldarg.1
0x3e14  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x3e19  ldarg.0
0x3e1a  ldloc.0
0x3e1b  ldarg.3
0x3e1c  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x3e21  ldloc.0
0x3e22  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionPageStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x3e27  stloc.1
0x3e28  ldarg.0
0x3e29  ldarg.s  4
0x3e2b  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x3e30  ldloc.1
0x3e31  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x3e36  ldarg.0
0x3e37  ldloc.0
0x3e38  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x3e3d  stloc.2
0x3e3e  leave.s  loc_3E49
0x3e40  stloc.3
0x3e41  ldarg.0
0x3e42  ldloc.3
0x3e43  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x3e48  throw
0x3e49  ldloc.2
0x3e4a  ret
```
