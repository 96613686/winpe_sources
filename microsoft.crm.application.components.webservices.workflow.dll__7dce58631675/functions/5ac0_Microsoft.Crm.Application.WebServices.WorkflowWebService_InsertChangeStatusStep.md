# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertChangeStatusStep

- ea: `0x5ac0`
- end: `0x5b29`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertChangeStatusStep`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x5ac0`
- `0x8ba0`
- `0x8f00`
- `0x8f20`
- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x5ac0  ldarg.0
0x5ac1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x5ac6  ldarg.2
0x5ac7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5acc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x5ad1  stloc.0
0x5ad2  ldloc.0
0x5ad3  ldarg.1
0x5ad4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x5ad9  ldarg.0
0x5ada  ldloc.0
0x5adb  ldarg.3
0x5adc  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x5ae1  ldloc.0
0x5ae2  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetStateStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x5ae7  stloc.1
0x5ae8  ldarg.0
0x5ae9  ldarg.s  4
0x5aeb  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x5af0  ldloc.1
0x5af1  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x5af6  ldarg.0
0x5af7  ldloc.1
0x5af8  ldloc.0
0x5af9  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::SetChangeStateDefaultValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetStateStep setStateStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x5afe  ldarg.0
0x5aff  ldloc.0
0x5b00  ldarg.s  5
0x5b02  dup
0x5b03  brtrue.s loc_5B0B
0x5b05  pop
0x5b06  ldstr    asc_A26A// ""
0x5b0b  ldarg.s  6
0x5b0d  dup
0x5b0e  brtrue.s loc_5B16
0x5b10  pop
0x5b11  ldstr    asc_A26A// ""
0x5b16  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x5b1b  stloc.2
0x5b1c  leave.s  loc_5B27
0x5b1e  stloc.3
0x5b1f  ldarg.0
0x5b20  ldloc.3
0x5b21  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x5b26  throw
0x5b27  ldloc.2
0x5b28  ret
```
