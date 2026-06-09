# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddChildWorkflowStep

- ea: `0x4fd0`
- end: `0x5035`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddChildWorkflowStep`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x4fd0`
- `0x8ba0`
- `0x8f00`
- `0x9190`

## pseudocode

```c

```

## disassembly

```asm
0x4fd0  ldarg.0
0x4fd1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x4fd6  ldarg.2
0x4fd7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4fdc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x4fe1  stloc.0
0x4fe2  ldloc.0
0x4fe3  ldarg.1
0x4fe4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x4fe9  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x4fee  ldloc.0
0x4fef  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x4ff4  stloc.1
0x4ff5  ldarg.0
0x4ff6  ldloc.0
0x4ff7  ldarg.3
0x4ff8  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x4ffd  ldloc.1
0x4ffe  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x5003  ldarg.0
0x5004  ldloc.1
0x5005  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::SetChildWorkflowDefaultValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep childWorkflowStep)
0x500a  ldarg.0
0x500b  ldloc.0
0x500c  ldarg.s  4
0x500e  dup
0x500f  brtrue.s loc_5017
0x5011  pop
0x5012  ldstr    asc_A26A// ""
0x5017  ldarg.s  5
0x5019  dup
0x501a  brtrue.s loc_5022
0x501c  pop
0x501d  ldstr    asc_A26A// ""
0x5022  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x5027  stloc.2
0x5028  leave.s  loc_5033
0x502a  stloc.3
0x502b  ldarg.0
0x502c  ldloc.3
0x502d  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x5032  throw
0x5033  ldloc.2
0x5034  ret
```
