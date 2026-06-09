# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertWaitBranchStep

- ea: `0x47b0`
- end: `0x480b`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertWaitBranchStep`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x47b0`
- `0x8b90`
- `0x8f00`
- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x47b0  ldarg.0
0x47b1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x47b6  ldarg.2
0x47b7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x47bc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x47c1  stloc.0
0x47c2  ldloc.0
0x47c3  ldarg.1
0x47c4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x47c9  ldarg.0
0x47ca  ldloc.0
0x47cb  ldarg.3
0x47cc  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x47d1  dup
0x47d2  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x47d7  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep
0x47dc  ldloc.0
0x47dd  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.NullExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x47e2  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitBranchStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x47e7  stloc.1
0x47e8  ldarg.0
0x47e9  ldarg.s  4
0x47eb  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x47f0  ldloc.1
0x47f1  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x47f6  ldarg.0
0x47f7  ldloc.0
0x47f8  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x47fd  stloc.2
0x47fe  leave.s  loc_4809
0x4800  stloc.3
0x4801  ldarg.0
0x4802  ldloc.3
0x4803  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x4808  throw
0x4809  ldloc.2
0x480a  ret
```
