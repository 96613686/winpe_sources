# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateWaitTimeoutExpression

- ea: `0x4940`
- end: `0x49be`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateWaitTimeoutExpression`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x4940`
- `0x49f0`
- `0x8b90`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x4940  ldarg.0
0x4941  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x4946  ldarg.3
0x4947  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x494c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x4951  stloc.0
0x4952  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4957  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.ConditionExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x495c  ldloc.0
0x495d  ldarg.1
0x495e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x4963  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitTimeoutStep
0x4968  stloc.1
0x4969  ldloc.0
0x496a  ldarg.2
0x496b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.ConditionExpressionBuilder::CreateConditionExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x4970  stloc.2
0x4971  ldloc.2
0x4972  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.BinaryExpression
0x4977  stloc.3
0x4978  ldloc.3
0x4979  brfalse.s loc_4995
0x497b  ldloc.1
0x497c  ldarg.0
0x497d  ldloc.3
0x497e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionCollection [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.BinaryExpression::get_RightOperands()
0x4983  ldc.i4.0
0x4984  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionCollection::get_Item(int32)
0x4989  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Application.WebServices.WorkflowWebService::ExtractTimeSpanExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase expression)
0x498e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitTimeoutStep::set_TimeoutExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x4993  br.s     loc_499C
0x4995  ldloc.1
0x4996  ldloc.2
0x4997  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitTimeoutStep::set_TimeoutExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x499c  ldarg.0
0x499d  ldloc.0
0x499e  ldarg.s  4
0x49a0  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x49a5  ldarg.0
0x49a6  ldloc.0
0x49a7  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x49ac  stloc.s  4
0x49ae  leave.s  loc_49BB
0x49b0  stloc.s  5
0x49b2  ldarg.0
0x49b3  ldloc.s  5
0x49b5  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x49ba  throw
0x49bb  ldloc.s  4
0x49bd  ret
```
