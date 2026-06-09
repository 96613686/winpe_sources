# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertQueryDataStep

- ea: `0x22e0`
- end: `0x2332`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertQueryDataStep`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x22e0`
- `0x8b90`
- `0x8f00`
- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x22e0  ldarg.0
0x22e1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x22e6  ldarg.2
0x22e7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x22ec  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x22f1  stloc.0
0x22f2  ldloc.0
0x22f3  ldarg.1
0x22f4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x22f9  ldarg.0
0x22fa  ldloc.0
0x22fb  ldarg.3
0x22fc  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x2301  ldloc.0
0x2302  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x2307  stloc.1
0x2308  ldloc.1
0x2309  ldc.i4.m1
0x230a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.QueryStep::set_FetchCount(int32)
0x230f  ldarg.0
0x2310  ldarg.s  4
0x2312  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x2317  ldloc.1
0x2318  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x231d  ldarg.0
0x231e  ldloc.0
0x231f  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x2324  stloc.2
0x2325  leave.s  loc_2330
0x2327  stloc.3
0x2328  ldarg.0
0x2329  ldloc.3
0x232a  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x232f  throw
0x2330  ldloc.2
0x2331  ret
```
