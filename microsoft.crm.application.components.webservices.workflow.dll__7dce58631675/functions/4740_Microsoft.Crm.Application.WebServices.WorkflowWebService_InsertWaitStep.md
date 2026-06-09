# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertWaitStep

- ea: `0x4740`
- end: `0x47a1`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertWaitStep`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x4740`
- `0x8b90`
- `0x8f00`
- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x4740  ldarg.0
0x4741  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x4746  ldarg.2
0x4747  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x474c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x4751  stloc.0
0x4752  ldloc.0
0x4753  ldarg.1
0x4754  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x4759  ldarg.0
0x475a  ldloc.0
0x475b  ldarg.3
0x475c  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x4761  ldloc.0
0x4762  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x4767  stloc.1
0x4768  ldarg.0
0x4769  ldarg.s  4
0x476b  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x4770  ldloc.1
0x4771  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x4776  ldloc.1
0x4777  ldloc.0
0x4778  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.NullExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x477d  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitBranchStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x4782  stloc.2
0x4783  ldloc.1
0x4784  ldloc.2
0x4785  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep::Append(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x478a  ldarg.0
0x478b  ldloc.0
0x478c  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x4791  stloc.3
0x4792  leave.s  loc_479F
0x4794  stloc.s  4
0x4796  ldarg.0
0x4797  ldloc.s  4
0x4799  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x479e  throw
0x479f  ldloc.3
0x47a0  ret
```
