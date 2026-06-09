# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddAssignStep

- ea: `0x3420`
- end: `0x3452`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddAssignStep`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x3460`
- `0x3910`

## callees

- `0x3420`
- `0x8b90`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x3420  ldarg.s  4
0x3422  ldarg.1
0x3423  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x3428  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x342d  ldarg.0
0x342e  ldarg.s  4
0x3430  ldarg.2
0x3431  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x3436  ldarg.3
0x3437  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x343c  ldarg.0
0x343d  ldarg.s  4
0x343f  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x3444  stloc.0
0x3445  leave.s  loc_3450
0x3447  stloc.1
0x3448  ldarg.0
0x3449  ldloc.1
0x344a  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x344f  throw
0x3450  ldloc.0
0x3451  ret
```
