# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertChildWorkflowStep

- ea: `0x5040`
- end: `0x50a8`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertChildWorkflowStep`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x5040`
- `0x8ba0`
- `0x8f00`
- `0x9170`
- `0x9190`

## pseudocode

```c

```

## disassembly

```asm
0x5040  ldarg.0
0x5041  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x5046  ldarg.2
0x5047  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x504c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x5051  stloc.0
0x5052  ldloc.0
0x5053  ldarg.1
0x5054  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x5059  ldloc.0
0x505a  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x505f  stloc.1
0x5060  ldarg.0
0x5061  ldloc.0
0x5062  ldarg.3
0x5063  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x5068  ldarg.0
0x5069  ldarg.s  4
0x506b  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x5070  ldloc.1
0x5071  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x5076  ldarg.0
0x5077  ldloc.1
0x5078  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::SetChildWorkflowDefaultValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep childWorkflowStep)
0x507d  ldarg.0
0x507e  ldloc.0
0x507f  ldarg.s  5
0x5081  dup
0x5082  brtrue.s loc_508A
0x5084  pop
0x5085  ldstr    asc_A26A// ""
0x508a  ldarg.s  6
0x508c  dup
0x508d  brtrue.s loc_5095
0x508f  pop
0x5090  ldstr    asc_A26A// ""
0x5095  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x509a  stloc.2
0x509b  leave.s  loc_50A6
0x509d  stloc.3
0x509e  ldarg.0
0x509f  ldloc.3
0x50a0  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x50a5  throw
0x50a6  ldloc.2
0x50a7  ret
```
