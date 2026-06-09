# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddInteractionPageStep

- ea: `0x3db0`
- end: `0x3df8`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddInteractionPageStep`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x3db0`
- `0x8b90`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x3db0  ldarg.0
0x3db1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x3db6  ldarg.2
0x3db7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3dbc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x3dc1  stloc.0
0x3dc2  ldloc.0
0x3dc3  ldarg.1
0x3dc4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x3dc9  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x3dce  ldarg.0
0x3dcf  ldloc.0
0x3dd0  ldarg.3
0x3dd1  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x3dd6  ldloc.0
0x3dd7  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionPageStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x3ddc  stloc.1
0x3ddd  ldloc.1
0x3dde  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x3de3  ldarg.0
0x3de4  ldloc.0
0x3de5  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x3dea  stloc.2
0x3deb  leave.s  loc_3DF6
0x3ded  stloc.3
0x3dee  ldarg.0
0x3def  ldloc.3
0x3df0  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x3df5  throw
0x3df6  ldloc.2
0x3df7  ret
```
