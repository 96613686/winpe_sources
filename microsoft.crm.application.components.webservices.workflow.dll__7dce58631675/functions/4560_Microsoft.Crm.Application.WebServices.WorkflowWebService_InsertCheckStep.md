# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertCheckStep

- ea: `0x4560`
- end: `0x45c1`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertCheckStep`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x4560`
- `0x8b90`
- `0x8f00`
- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x4560  ldarg.0
0x4561  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x4566  ldarg.2
0x4567  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x456c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x4571  stloc.0
0x4572  ldloc.0
0x4573  ldarg.1
0x4574  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x4579  ldarg.0
0x457a  ldloc.0
0x457b  ldarg.3
0x457c  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x4581  ldloc.0
0x4582  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x4587  stloc.1
0x4588  ldarg.0
0x4589  ldarg.s  4
0x458b  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x4590  ldloc.1
0x4591  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x4596  ldloc.1
0x4597  ldloc.0
0x4598  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.NullExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x459d  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionBranchStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x45a2  stloc.2
0x45a3  ldloc.1
0x45a4  ldloc.2
0x45a5  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x45aa  ldarg.0
0x45ab  ldloc.0
0x45ac  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x45b1  stloc.3
0x45b2  leave.s  loc_45BF
0x45b4  stloc.s  4
0x45b6  ldarg.0
0x45b7  ldloc.s  4
0x45b9  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x45be  throw
0x45bf  ldloc.3
0x45c0  ret
```
