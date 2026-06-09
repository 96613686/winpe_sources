# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertInvokeSdkMessageStep

- ea: `0x6b20`
- end: `0x6b8b`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertInvokeSdkMessageStep`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x6b20`
- `0x8b90`
- `0x8f00`
- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x6b20  ldarg.0
0x6b21  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x6b26  ldarg.1
0x6b27  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6b2c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x6b31  stloc.0
0x6b32  ldloc.0
0x6b33  ldarg.3
0x6b34  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x6b39  ldarg.0
0x6b3a  ldloc.0
0x6b3b  ldarg.2
0x6b3c  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x6b41  ldloc.0
0x6b42  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x6b47  stloc.1
0x6b48  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::.ctor()
0x6b4d  stloc.2
0x6b4e  ldloc.2
0x6b4f  ldloca.s 3
0x6b51  initobj  [mscorlib]System.Guid
0x6b57  ldloc.3
0x6b58  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::set_SdkMessageId(valuetype [mscorlib]System.Guid)
0x6b5d  ldloc.1
0x6b5e  ldloc.2
0x6b5f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::set_ActivityInfo(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase)
0x6b64  ldarg.0
0x6b65  ldarg.s  4
0x6b67  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x6b6c  ldloc.1
0x6b6d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x6b72  ldarg.0
0x6b73  ldloc.0
0x6b74  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x6b79  stloc.s  4
0x6b7b  leave.s  loc_6B88
0x6b7d  stloc.s  5
0x6b7f  ldarg.0
0x6b80  ldloc.s  5
0x6b82  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x6b87  throw
0x6b88  ldloc.s  4
0x6b8a  ret
```
