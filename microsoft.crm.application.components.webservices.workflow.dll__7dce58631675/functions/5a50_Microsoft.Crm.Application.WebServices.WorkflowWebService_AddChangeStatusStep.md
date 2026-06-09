# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddChangeStatusStep

- ea: `0x5a50`
- end: `0x5ab6`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddChangeStatusStep`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x5a50`
- `0x8ba0`
- `0x8f00`
- `0x8f20`

## pseudocode

```c

```

## disassembly

```asm
0x5a50  ldarg.0
0x5a51  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x5a56  ldarg.2
0x5a57  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5a5c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x5a61  stloc.0
0x5a62  ldloc.0
0x5a63  ldarg.1
0x5a64  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x5a69  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x5a6e  ldarg.0
0x5a6f  ldloc.0
0x5a70  ldarg.3
0x5a71  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x5a76  ldloc.0
0x5a77  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetStateStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x5a7c  stloc.1
0x5a7d  ldloc.1
0x5a7e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x5a83  ldarg.0
0x5a84  ldloc.1
0x5a85  ldloc.0
0x5a86  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::SetChangeStateDefaultValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetStateStep setStateStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x5a8b  ldarg.0
0x5a8c  ldloc.0
0x5a8d  ldarg.s  4
0x5a8f  dup
0x5a90  brtrue.s loc_5A98
0x5a92  pop
0x5a93  ldstr    asc_A26A// ""
0x5a98  ldarg.s  5
0x5a9a  dup
0x5a9b  brtrue.s loc_5AA3
0x5a9d  pop
0x5a9e  ldstr    asc_A26A// ""
0x5aa3  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x5aa8  stloc.2
0x5aa9  leave.s  loc_5AB4
0x5aab  stloc.3
0x5aac  ldarg.0
0x5aad  ldloc.3
0x5aae  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x5ab3  throw
0x5ab4  ldloc.2
0x5ab5  ret
```
