# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertInteractionStep

- ea: `0x3ea0`
- end: `0x3ef2`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertInteractionStep`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x3ea0`
- `0x8b90`
- `0x8f00`
- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x3ea0  ldarg.0
0x3ea1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x3ea6  ldarg.2
0x3ea7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3eac  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x3eb1  stloc.0
0x3eb2  ldloc.0
0x3eb3  ldarg.1
0x3eb4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x3eb9  ldarg.0
0x3eba  ldloc.0
0x3ebb  ldarg.3
0x3ebc  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x3ec1  ldloc.0
0x3ec2  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x3ec7  stloc.1
0x3ec8  ldarg.0
0x3ec9  ldarg.s  4
0x3ecb  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x3ed0  ldloc.1
0x3ed1  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x3ed6  ldloc.1
0x3ed7  ldc.i4.0
0x3ed8  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InteractionStep::set_IsResponseMetadataBound(bool)
0x3edd  ldarg.0
0x3ede  ldloc.0
0x3edf  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x3ee4  stloc.2
0x3ee5  leave.s  loc_3EF0
0x3ee7  stloc.3
0x3ee8  ldarg.0
0x3ee9  ldloc.3
0x3eea  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x3eef  throw
0x3ef0  ldloc.2
0x3ef1  ret
```
