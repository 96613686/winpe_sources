# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddElseStep

- ea: `0x4630`
- end: `0x4679`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddElseStep`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x4630`
- `0x8b90`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x4630  ldarg.0
0x4631  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x4636  ldarg.2
0x4637  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x463c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x4641  stloc.0
0x4642  ldloc.0
0x4643  ldarg.1
0x4644  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x4649  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep
0x464e  ldarg.0
0x464f  ldloc.0
0x4650  ldarg.3
0x4651  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x4656  dup
0x4657  ldnull
0x4658  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionBranchStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x465d  stloc.1
0x465e  ldloc.1
0x465f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x4664  ldarg.0
0x4665  ldloc.0
0x4666  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x466b  stloc.2
0x466c  leave.s  loc_4677
0x466e  stloc.3
0x466f  ldarg.0
0x4670  ldloc.3
0x4671  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x4676  throw
0x4677  ldloc.2
0x4678  ret
```
