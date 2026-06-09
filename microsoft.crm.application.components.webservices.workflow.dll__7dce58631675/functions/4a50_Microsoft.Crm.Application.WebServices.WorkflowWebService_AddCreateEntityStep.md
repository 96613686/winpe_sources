# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddCreateEntityStep

- ea: `0x4a50`
- end: `0x4aae`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddCreateEntityStep`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x4a50`
- `0x8ba0`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x4a50  ldarg.0
0x4a51  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x4a56  ldarg.2
0x4a57  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4a5c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x4a61  stloc.0
0x4a62  ldloc.0
0x4a63  ldarg.1
0x4a64  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x4a69  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x4a6e  ldarg.0
0x4a6f  ldloc.0
0x4a70  ldarg.3
0x4a71  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x4a76  ldloc.0
0x4a77  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x4a7c  stloc.1
0x4a7d  ldloc.1
0x4a7e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x4a83  ldarg.0
0x4a84  ldloc.0
0x4a85  ldarg.s  4
0x4a87  dup
0x4a88  brtrue.s loc_4A90
0x4a8a  pop
0x4a8b  ldstr    asc_A26A// ""
0x4a90  ldarg.s  5
0x4a92  dup
0x4a93  brtrue.s loc_4A9B
0x4a95  pop
0x4a96  ldstr    asc_A26A// ""
0x4a9b  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x4aa0  stloc.2
0x4aa1  leave.s  loc_4AAC
0x4aa3  stloc.3
0x4aa4  ldarg.0
0x4aa5  ldloc.3
0x4aa6  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x4aab  throw
0x4aac  ldloc.2
0x4aad  ret
```
