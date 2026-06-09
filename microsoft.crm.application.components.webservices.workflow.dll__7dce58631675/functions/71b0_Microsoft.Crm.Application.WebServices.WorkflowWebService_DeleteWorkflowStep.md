# Microsoft.Crm.Application.WebServices.WorkflowWebService::DeleteWorkflowStep

- ea: `0x71b0`
- end: `0x7204`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::DeleteWorkflowStep`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x71b0`
- `0x8ba0`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x71b0  ldarg.0
0x71b1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x71b6  ldarg.2
0x71b7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x71bc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x71c1  stloc.0
0x71c2  ldloc.0
0x71c3  ldarg.1
0x71c4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x71c9  stloc.1
0x71ca  ldarg.0
0x71cb  ldloc.0
0x71cc  ldarg.3
0x71cd  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x71d2  ldloc.0
0x71d3  ldloc.1
0x71d4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::DeleteStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x71d9  ldarg.0
0x71da  ldloc.0
0x71db  ldarg.s  4
0x71dd  dup
0x71de  brtrue.s loc_71E6
0x71e0  pop
0x71e1  ldstr    asc_A26A// ""
0x71e6  ldarg.s  5
0x71e8  dup
0x71e9  brtrue.s loc_71F1
0x71eb  pop
0x71ec  ldstr    asc_A26A// ""
0x71f1  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x71f6  stloc.2
0x71f7  leave.s  loc_7202
0x71f9  stloc.3
0x71fa  ldarg.0
0x71fb  ldloc.3
0x71fc  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x7201  throw
0x7202  ldloc.2
0x7203  ret
```
