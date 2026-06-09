# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddQueryDataStep

- ea: `0x2290`
- end: `0x22df`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddQueryDataStep`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x2290`
- `0x8b90`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x2290  ldarg.0
0x2291  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x2296  ldarg.2
0x2297  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x229c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x22a1  stloc.0
0x22a2  ldloc.0
0x22a3  ldarg.1
0x22a4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x22a9  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x22ae  ldarg.0
0x22af  ldloc.0
0x22b0  ldarg.3
0x22b1  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x22b6  ldloc.0
0x22b7  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x22bc  stloc.1
0x22bd  ldloc.1
0x22be  ldc.i4.m1
0x22bf  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::set_FetchCount(int32)
0x22c4  ldloc.1
0x22c5  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x22ca  ldarg.0
0x22cb  ldloc.0
0x22cc  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x22d1  stloc.2
0x22d2  leave.s  loc_22DD
0x22d4  stloc.3
0x22d5  ldarg.0
0x22d6  ldloc.3
0x22d7  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x22dc  throw
0x22dd  ldloc.2
0x22de  ret
```
