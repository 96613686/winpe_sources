# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddSendEmailStep

- ea: `0x5690`
- end: `0x56f5`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddSendEmailStep`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x5690`
- `0x8ba0`
- `0x8f00`
- `0x9200`

## pseudocode

```c

```

## disassembly

```asm
0x5690  ldarg.0
0x5691  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x5696  ldarg.2
0x5697  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x569c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x56a1  stloc.0
0x56a2  ldloc.0
0x56a3  ldarg.1
0x56a4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x56a9  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x56ae  ldarg.0
0x56af  ldloc.0
0x56b0  ldarg.3
0x56b1  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x56b6  ldloc.0
0x56b7  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x56bc  stloc.1
0x56bd  ldloc.1
0x56be  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x56c3  ldarg.0
0x56c4  ldloc.1
0x56c5  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::SetSendEmailDefaultValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep step)
0x56ca  ldarg.0
0x56cb  ldloc.0
0x56cc  ldarg.s  4
0x56ce  dup
0x56cf  brtrue.s loc_56D7
0x56d1  pop
0x56d2  ldstr    asc_A26A// ""
0x56d7  ldarg.s  5
0x56d9  dup
0x56da  brtrue.s loc_56E2
0x56dc  pop
0x56dd  ldstr    asc_A26A// ""
0x56e2  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x56e7  stloc.2
0x56e8  leave.s  loc_56F3
0x56ea  stloc.3
0x56eb  ldarg.0
0x56ec  ldloc.3
0x56ed  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x56f2  throw
0x56f3  ldloc.2
0x56f4  ret
```
