# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddStopWorkflowStep

- ea: `0x5d80`
- end: `0x5dc8`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddStopWorkflowStep`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x5d80`
- `0x8b90`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x5d80  ldarg.0
0x5d81  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x5d86  ldarg.2
0x5d87  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5d8c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x5d91  stloc.0
0x5d92  ldloc.0
0x5d93  ldarg.1
0x5d94  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x5d99  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x5d9e  ldarg.0
0x5d9f  ldloc.0
0x5da0  ldarg.3
0x5da1  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x5da6  ldloc.0
0x5da7  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StopWorkflowStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x5dac  stloc.1
0x5dad  ldloc.1
0x5dae  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x5db3  ldarg.0
0x5db4  ldloc.0
0x5db5  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x5dba  stloc.2
0x5dbb  leave.s  loc_5DC6
0x5dbd  stloc.3
0x5dbe  ldarg.0
0x5dbf  ldloc.3
0x5dc0  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x5dc5  throw
0x5dc6  ldloc.2
0x5dc7  ret
```
