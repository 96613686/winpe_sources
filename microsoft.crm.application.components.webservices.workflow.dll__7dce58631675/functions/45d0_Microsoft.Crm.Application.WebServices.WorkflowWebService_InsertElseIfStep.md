# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertElseIfStep

- ea: `0x45d0`
- end: `0x4630`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertElseIfStep`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x45d0`
- `0x8b90`
- `0x8f00`
- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x45d0  ldarg.0
0x45d1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x45d6  ldarg.2
0x45d7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x45dc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x45e1  stloc.0
0x45e2  ldloc.0
0x45e3  ldarg.1
0x45e4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x45e9  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionBranchStep
0x45ee  ldarg.0
0x45ef  ldloc.0
0x45f0  ldarg.3
0x45f1  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x45f6  dup
0x45f7  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x45fc  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep
0x4601  ldloc.0
0x4602  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.NullExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x4607  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionBranchStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x460c  stloc.1
0x460d  ldarg.0
0x460e  ldarg.s  4
0x4610  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x4615  ldloc.1
0x4616  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x461b  ldarg.0
0x461c  ldloc.0
0x461d  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x4622  stloc.2
0x4623  leave.s  loc_462E
0x4625  stloc.3
0x4626  ldarg.0
0x4627  ldloc.3
0x4628  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x462d  throw
0x462e  ldloc.2
0x462f  ret
```
