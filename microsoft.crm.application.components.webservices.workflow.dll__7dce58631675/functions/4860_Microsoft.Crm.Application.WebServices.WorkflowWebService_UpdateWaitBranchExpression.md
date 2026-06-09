# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateWaitBranchExpression

- ea: `0x4860`
- end: `0x493e`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateWaitBranchExpression`
- size: `222`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x4860`
- `0x49f0`
- `0x8b90`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x4860  ldarg.0
0x4861  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x4866  ldarg.3
0x4867  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x486c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x4871  stloc.1
0x4872  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4877  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.ConditionExpressionBuilder::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x487c  ldloc.1
0x487d  ldarg.2
0x487e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.ConditionExpressionBuilder::CreateConditionExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x4883  stloc.2
0x4884  ldloc.2
0x4885  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.BinaryExpression
0x488a  stloc.3
0x488b  ldloc.3
0x488c  brfalse.s loc_4908
0x488e  ldloc.3
0x488f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.BinaryExpression::get_LeftOperand()
0x4894  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression
0x4899  stloc.s  4
0x489b  ldloc.s  4
0x489d  brfalse.s loc_4908
0x489f  ldloc.s  4
0x48a1  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::get_Method()
0x48a6  ldc.i4.6
0x48a7  bne.un.s loc_4908
0x48a9  ldloc.1
0x48aa  ldarg.1
0x48ab  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x48b0  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitBranchStep
0x48b5  stloc.0
0x48b6  ldloc.0
0x48b7  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x48bc  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep
0x48c1  ldarg.0
0x48c2  ldloc.3
0x48c3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionCollection [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.BinaryExpression::get_RightOperands()
0x48c8  ldc.i4.0
0x48c9  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionCollection::get_Item(int32)
0x48ce  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase Microsoft.Crm.Application.WebServices.WorkflowWebService::ExtractTimeSpanExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase expression)
0x48d3  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitTimeoutStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x48d8  stloc.s  5
0x48da  ldloc.0
0x48db  ldc.i4.1
0x48dc  ldloc.s  5
0x48de  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x48e3  ldloc.0
0x48e4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x48e9  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep
0x48ee  ldloc.0
0x48ef  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::Remove(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x48f4  ldarg.0
0x48f5  ldloc.1
0x48f6  ldarg.s  4
0x48f8  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x48fd  ldarg.0
0x48fe  ldloc.1
0x48ff  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x4904  stloc.s  6
0x4906  leave.s  loc_493B
0x4908  ldloc.1
0x4909  ldarg.1
0x490a  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x490f  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitBranchStep
0x4914  stloc.0
0x4915  ldloc.0
0x4916  ldloc.2
0x4917  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitBranchStep::set_ConditionExpression(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x491c  ldarg.0
0x491d  ldloc.1
0x491e  ldarg.s  4
0x4920  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x4925  ldarg.0
0x4926  ldloc.1
0x4927  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x492c  stloc.s  6
0x492e  leave.s  loc_493B
0x4930  stloc.s  7
0x4932  ldarg.0
0x4933  ldloc.s  7
0x4935  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x493a  throw
0x493b  ldloc.s  6
0x493d  ret
```
