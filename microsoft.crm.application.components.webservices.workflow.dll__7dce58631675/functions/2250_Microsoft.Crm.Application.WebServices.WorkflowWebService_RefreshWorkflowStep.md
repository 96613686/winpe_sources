# Microsoft.Crm.Application.WebServices.WorkflowWebService::RefreshWorkflowStep

- ea: `0x2250`
- end: `0x228b`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::RefreshWorkflowStep`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x2250`
- `0x8ba0`

## pseudocode

```c

```

## disassembly

```asm
0x2250  ldarg.0
0x2251  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x2256  ldarg.1
0x2257  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x225c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x2261  stloc.0
0x2262  ldarg.0
0x2263  ldloc.0
0x2264  ldarg.2
0x2265  dup
0x2266  brtrue.s loc_226E
0x2268  pop
0x2269  ldstr    asc_A26A// ""
0x226e  ldarg.3
0x226f  dup
0x2270  brtrue.s loc_2278
0x2272  pop
0x2273  ldstr    asc_A26A// ""
0x2278  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x227d  stloc.1
0x227e  leave.s  loc_2289
0x2280  stloc.2
0x2281  ldarg.0
0x2282  ldloc.2
0x2283  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x2288  throw
0x2289  ldloc.1
0x228a  ret
```
