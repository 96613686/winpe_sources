# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddChildInteractiveWorkflowStep

- ea: `0x27d0`
- end: `0x281f`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddChildInteractiveWorkflowStep`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x27d0`
- `0x2880`
- `0x8b90`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x27d0  ldarg.0
0x27d1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x27d6  ldarg.2
0x27d7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x27dc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x27e1  stloc.0
0x27e2  ldloc.0
0x27e3  ldarg.1
0x27e4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x27e9  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x27ee  ldarg.0
0x27ef  ldloc.0
0x27f0  ldarg.3
0x27f1  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x27f6  ldloc.0
0x27f7  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x27fc  stloc.1
0x27fd  ldloc.1
0x27fe  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x2803  ldarg.0
0x2804  ldloc.1
0x2805  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::SetChildInteractiveWorkflowDefaultValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep childWorkflowStep)
0x280a  ldarg.0
0x280b  ldloc.0
0x280c  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x2811  stloc.2
0x2812  leave.s  loc_281D
0x2814  stloc.3
0x2815  ldarg.0
0x2816  ldloc.3
0x2817  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x281c  throw
0x281d  ldloc.2
0x281e  ret
```
