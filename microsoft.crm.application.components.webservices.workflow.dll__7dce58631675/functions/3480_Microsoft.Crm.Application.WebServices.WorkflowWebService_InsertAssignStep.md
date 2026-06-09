# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertAssignStep

- ea: `0x3480`
- end: `0x34b5`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertAssignStep`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x3570`
- `0x3930`

## callees

- `0x3480`
- `0x8b90`
- `0x8f00`
- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x3480  ldarg.s  5
0x3482  ldarg.1
0x3483  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x3488  ldarg.0
0x3489  ldarg.s  5
0x348b  ldarg.2
0x348c  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x3491  ldarg.0
0x3492  ldarg.3
0x3493  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x3498  ldarg.s  4
0x349a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x349f  ldarg.0
0x34a0  ldarg.s  5
0x34a2  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x34a7  stloc.0
0x34a8  leave.s  loc_34B3
0x34aa  stloc.1
0x34ab  ldarg.0
0x34ac  ldloc.1
0x34ad  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x34b2  throw
0x34b3  ldloc.0
0x34b4  ret
```
