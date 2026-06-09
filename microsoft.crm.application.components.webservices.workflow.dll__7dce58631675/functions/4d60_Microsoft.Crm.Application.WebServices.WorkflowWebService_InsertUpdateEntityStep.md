# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertUpdateEntityStep

- ea: `0x4d60`
- end: `0x4dc8`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertUpdateEntityStep`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x4d60`
- `0x8ba0`
- `0x8f00`
- `0x9170`
- `0x91c0`

## pseudocode

```c

```

## disassembly

```asm
0x4d60  ldarg.0
0x4d61  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x4d66  ldarg.2
0x4d67  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4d6c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x4d71  stloc.0
0x4d72  ldloc.0
0x4d73  ldarg.1
0x4d74  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x4d79  ldarg.0
0x4d7a  ldloc.0
0x4d7b  ldarg.3
0x4d7c  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x4d81  ldloc.0
0x4d82  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x4d87  stloc.1
0x4d88  ldarg.0
0x4d89  ldarg.s  4
0x4d8b  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x4d90  ldloc.1
0x4d91  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x4d96  ldarg.0
0x4d97  ldloc.1
0x4d98  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::SetUpdateStepDefaultValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep step)
0x4d9d  ldarg.0
0x4d9e  ldloc.0
0x4d9f  ldarg.s  5
0x4da1  dup
0x4da2  brtrue.s loc_4DAA
0x4da4  pop
0x4da5  ldstr    asc_A26A// ""
0x4daa  ldarg.s  6
0x4dac  dup
0x4dad  brtrue.s loc_4DB5
0x4daf  pop
0x4db0  ldstr    asc_A26A// ""
0x4db5  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x4dba  stloc.2
0x4dbb  leave.s  loc_4DC6
0x4dbd  stloc.3
0x4dbe  ldarg.0
0x4dbf  ldloc.3
0x4dc0  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x4dc5  throw
0x4dc6  ldloc.2
0x4dc7  ret
```
