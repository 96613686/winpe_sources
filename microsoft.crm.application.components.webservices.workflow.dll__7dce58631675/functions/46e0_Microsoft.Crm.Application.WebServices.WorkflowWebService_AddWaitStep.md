# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddWaitStep

- ea: `0x46e0`
- end: `0x473e`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddWaitStep`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x46e0`
- `0x8b90`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x46e0  ldarg.0
0x46e1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x46e6  ldarg.2
0x46e7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x46ec  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x46f1  stloc.0
0x46f2  ldloc.0
0x46f3  ldarg.1
0x46f4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x46f9  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x46fe  ldarg.0
0x46ff  ldloc.0
0x4700  ldarg.3
0x4701  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x4706  ldloc.0
0x4707  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x470c  stloc.1
0x470d  ldloc.1
0x470e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x4713  ldloc.1
0x4714  ldloc.0
0x4715  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.NullExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x471a  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitBranchStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WaitStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x471f  stloc.2
0x4720  ldloc.1
0x4721  ldloc.2
0x4722  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x4727  ldarg.0
0x4728  ldloc.0
0x4729  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x472e  stloc.3
0x472f  leave.s  loc_473C
0x4731  stloc.s  4
0x4733  ldarg.0
0x4734  ldloc.s  4
0x4736  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x473b  throw
0x473c  ldloc.3
0x473d  ret
```
