# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddInteractionStep

- ea: `0x3e50`
- end: `0x3e98`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddInteractionStep`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x3e50`
- `0x8b90`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x3e50  ldarg.0
0x3e51  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x3e56  ldarg.2
0x3e57  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3e5c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x3e61  stloc.0
0x3e62  ldloc.0
0x3e63  ldarg.1
0x3e64  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x3e69  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x3e6e  ldarg.0
0x3e6f  ldloc.0
0x3e70  ldarg.3
0x3e71  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x3e76  ldloc.0
0x3e77  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x3e7c  stloc.1
0x3e7d  ldloc.1
0x3e7e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x3e83  ldarg.0
0x3e84  ldloc.0
0x3e85  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x3e8a  stloc.2
0x3e8b  leave.s  loc_3E96
0x3e8d  stloc.3
0x3e8e  ldarg.0
0x3e8f  ldloc.3
0x3e90  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x3e95  throw
0x3e96  ldloc.2
0x3e97  ret
```
