# Microsoft.Crm.Application.WebServices.WorkflowWebService::DeleteVariable

- ea: `0x33c0`
- end: `0x33fa`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::DeleteVariable`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x33c0`
- `0x8b90`

## pseudocode

```c

```

## disassembly

```asm
0x33c0  ldarg.0
0x33c1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x33c6  ldarg.1
0x33c7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x33cc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x33d1  stloc.0
0x33d2  ldloc.0
0x33d3  ldarg.2
0x33d4  ldarg.2
0x33d5  ldstr    aUiscriptInput// "UIScript_Input_"
0x33da  ldc.i4.4
0x33db  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x33e0  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::RemoveVariable(string, bool)
0x33e5  ldarg.0
0x33e6  ldloc.0
0x33e7  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x33ec  stloc.1
0x33ed  leave.s  loc_33F8
0x33ef  stloc.2
0x33f0  ldarg.0
0x33f1  ldloc.2
0x33f2  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x33f7  throw
0x33f8  ldloc.1
0x33f9  ret
```
