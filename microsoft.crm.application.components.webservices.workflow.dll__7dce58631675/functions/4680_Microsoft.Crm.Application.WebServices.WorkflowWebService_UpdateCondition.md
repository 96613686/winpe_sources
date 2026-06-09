# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateCondition

- ea: `0x4680`
- end: `0x46d4`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateCondition`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x4680`
- `0x8b90`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x4680  ldarg.0
0x4681  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x4686  ldarg.3
0x4687  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x468c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x4691  stloc.0
0x4692  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4697  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.ConditionExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x469c  ldloc.0
0x469d  ldarg.2
0x469e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.ConditionExpressionBuilder::CreateConditionExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x46a3  stloc.1
0x46a4  ldloc.0
0x46a5  ldarg.1
0x46a6  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x46ab  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionBranchStep
0x46b0  ldloc.1
0x46b1  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionBranchStep::set_ConditionExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x46b6  ldarg.0
0x46b7  ldloc.0
0x46b8  ldarg.s  4
0x46ba  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x46bf  ldarg.0
0x46c0  ldloc.0
0x46c1  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x46c6  stloc.2
0x46c7  leave.s  loc_46D2
0x46c9  stloc.3
0x46ca  ldarg.0
0x46cb  ldloc.3
0x46cc  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x46d1  throw
0x46d2  ldloc.2
0x46d3  ret
```
