# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddInvokeSdkMessageStep

- ea: `0x60a0`
- end: `0x60f7`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddInvokeSdkMessageStep`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x8b90`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x60a0  ldarg.0
0x60a1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x60a6  ldarg.1
0x60a7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x60ac  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x60b1  stloc.0
0x60b2  ldloc.0
0x60b3  ldarg.3
0x60b4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x60b9  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x60be  ldarg.0
0x60bf  ldloc.0
0x60c0  ldarg.2
0x60c1  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x60c6  ldloc.0
0x60c7  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x60cc  stloc.1
0x60cd  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::.ctor()
0x60d2  stloc.2
0x60d3  ldloc.2
0x60d4  ldloca.s 3
0x60d6  initobj  [mscorlib]System.Guid
0x60dc  ldloc.3
0x60dd  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::set_SdkMessageId(valuetype [mscorlib]System.Guid)
0x60e2  ldloc.1
0x60e3  ldloc.2
0x60e4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::set_ActivityInfo(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase)
0x60e9  ldloc.1
0x60ea  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x60ef  ldarg.0
0x60f0  ldloc.0
0x60f1  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x60f6  ret
```
