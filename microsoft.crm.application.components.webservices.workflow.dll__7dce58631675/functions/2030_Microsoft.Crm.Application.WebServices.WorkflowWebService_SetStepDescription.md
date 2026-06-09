# Microsoft.Crm.Application.WebServices.WorkflowWebService::SetStepDescription

- ea: `0x2030`
- end: `0x2067`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::SetStepDescription`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x2030`
- `0x8ba0`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x2030  ldarg.0
0x2031  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x2036  ldarg.1
0x2037  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x203c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x2041  stloc.0
0x2042  ldarg.0
0x2043  ldloc.0
0x2044  ldarg.2
0x2045  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x204a  ldarg.0
0x204b  ldloc.0
0x204c  ldarg.3
0x204d  dup
0x204e  brtrue.s loc_2056
0x2050  pop
0x2051  ldstr    asc_A26A// ""
0x2056  ldarg.s  4
0x2058  dup
0x2059  brtrue.s loc_2061
0x205b  pop
0x205c  ldstr    asc_A26A// ""
0x2061  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x2066  ret
```
