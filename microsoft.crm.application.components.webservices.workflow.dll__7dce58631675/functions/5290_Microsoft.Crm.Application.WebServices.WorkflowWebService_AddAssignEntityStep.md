# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddAssignEntityStep

- ea: `0x5290`
- end: `0x52fa`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddAssignEntityStep`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x5290`
- `0x8ba0`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x5290  ldarg.0
0x5291  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x5296  ldarg.2
0x5297  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x529c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x52a1  stloc.0
0x52a2  ldloc.0
0x52a3  ldarg.1
0x52a4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x52a9  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x52ae  ldarg.0
0x52af  ldloc.0
0x52b0  ldarg.3
0x52b1  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x52b6  ldloc.0
0x52b7  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x52bc  stloc.1
0x52bd  ldloc.1
0x52be  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x52c3  ldloc.1
0x52c4  ldloc.1
0x52c5  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.StepControlHelper::GetDefaultEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x52ca  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x52cf  ldarg.0
0x52d0  ldloc.0
0x52d1  ldarg.s  4
0x52d3  dup
0x52d4  brtrue.s loc_52DC
0x52d6  pop
0x52d7  ldstr    asc_A26A// ""
0x52dc  ldarg.s  5
0x52de  dup
0x52df  brtrue.s loc_52E7
0x52e1  pop
0x52e2  ldstr    asc_A26A// ""
0x52e7  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x52ec  stloc.2
0x52ed  leave.s  loc_52F8
0x52ef  stloc.3
0x52f0  ldarg.0
0x52f1  ldloc.3
0x52f2  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x52f7  throw
0x52f8  ldloc.2
0x52f9  ret
```
