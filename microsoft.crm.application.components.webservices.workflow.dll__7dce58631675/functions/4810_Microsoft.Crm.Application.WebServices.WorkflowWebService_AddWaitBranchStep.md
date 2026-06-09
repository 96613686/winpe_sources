# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddWaitBranchStep

- ea: `0x4810`
- end: `0x485e`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddWaitBranchStep`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x4810`
- `0x8b90`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x4810  ldarg.0
0x4811  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x4816  ldarg.2
0x4817  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x481c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x4821  stloc.0
0x4822  ldloc.0
0x4823  ldarg.1
0x4824  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x4829  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep
0x482e  ldarg.0
0x482f  ldloc.0
0x4830  ldarg.3
0x4831  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x4836  dup
0x4837  ldloc.0
0x4838  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.NullExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x483d  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitBranchStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x4842  stloc.1
0x4843  ldloc.1
0x4844  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep::Append(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x4849  ldarg.0
0x484a  ldloc.0
0x484b  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x4850  stloc.2
0x4851  leave.s  loc_485C
0x4853  stloc.3
0x4854  ldarg.0
0x4855  ldloc.3
0x4856  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x485b  throw
0x485c  ldloc.2
0x485d  ret
```
