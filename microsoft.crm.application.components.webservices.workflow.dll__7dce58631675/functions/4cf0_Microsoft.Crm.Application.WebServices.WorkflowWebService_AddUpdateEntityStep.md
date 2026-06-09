# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddUpdateEntityStep

- ea: `0x4cf0`
- end: `0x4d55`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddUpdateEntityStep`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x4cf0`
- `0x8ba0`
- `0x8f00`
- `0x91c0`

## pseudocode

```c

```

## disassembly

```asm
0x4cf0  ldarg.0
0x4cf1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x4cf6  ldarg.2
0x4cf7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4cfc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x4d01  stloc.0
0x4d02  ldloc.0
0x4d03  ldarg.1
0x4d04  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x4d09  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x4d0e  ldarg.0
0x4d0f  ldloc.0
0x4d10  ldarg.3
0x4d11  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x4d16  ldloc.0
0x4d17  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x4d1c  stloc.1
0x4d1d  ldloc.1
0x4d1e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x4d23  ldarg.0
0x4d24  ldloc.1
0x4d25  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::SetUpdateStepDefaultValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep step)
0x4d2a  ldarg.0
0x4d2b  ldloc.0
0x4d2c  ldarg.s  4
0x4d2e  dup
0x4d2f  brtrue.s loc_4D37
0x4d31  pop
0x4d32  ldstr    asc_A26A// ""
0x4d37  ldarg.s  5
0x4d39  dup
0x4d3a  brtrue.s loc_4D42
0x4d3c  pop
0x4d3d  ldstr    asc_A26A// ""
0x4d42  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x4d47  stloc.2
0x4d48  leave.s  loc_4D53
0x4d4a  stloc.3
0x4d4b  ldarg.0
0x4d4c  ldloc.3
0x4d4d  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x4d52  throw
0x4d53  ldloc.2
0x4d54  ret
```
