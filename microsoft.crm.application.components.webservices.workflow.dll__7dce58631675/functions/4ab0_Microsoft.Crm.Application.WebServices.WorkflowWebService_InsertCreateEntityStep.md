# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertCreateEntityStep

- ea: `0x4ab0`
- end: `0x4b11`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertCreateEntityStep`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x4ab0`
- `0x8ba0`
- `0x8f00`
- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x4ab0  ldarg.0
0x4ab1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x4ab6  ldarg.2
0x4ab7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4abc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x4ac1  stloc.0
0x4ac2  ldloc.0
0x4ac3  ldarg.1
0x4ac4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x4ac9  ldarg.0
0x4aca  ldloc.0
0x4acb  ldarg.3
0x4acc  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x4ad1  ldloc.0
0x4ad2  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x4ad7  stloc.1
0x4ad8  ldarg.0
0x4ad9  ldarg.s  4
0x4adb  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x4ae0  ldloc.1
0x4ae1  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x4ae6  ldarg.0
0x4ae7  ldloc.0
0x4ae8  ldarg.s  5
0x4aea  dup
0x4aeb  brtrue.s loc_4AF3
0x4aed  pop
0x4aee  ldstr    asc_A26A// ""
0x4af3  ldarg.s  6
0x4af5  dup
0x4af6  brtrue.s loc_4AFE
0x4af8  pop
0x4af9  ldstr    asc_A26A// ""
0x4afe  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x4b03  stloc.2
0x4b04  leave.s  loc_4B0F
0x4b06  stloc.3
0x4b07  ldarg.0
0x4b08  ldloc.3
0x4b09  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x4b0e  throw
0x4b0f  ldloc.2
0x4b10  ret
```
