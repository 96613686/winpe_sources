# Microsoft.Crm.Application.WebServices.WorkflowWebService::CanWorkflowStageBeDeleted

- ea: `0x6010`
- end: `0x609f`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::CanWorkflowStageBeDeleted`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x6010`

## pseudocode

```c

```

## disassembly

```asm
0x6010  ldc.i4.1
0x6011  stloc.0
0x6012  ldarg.0
0x6013  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x6018  ldarg.2
0x6019  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x601e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x6023  stloc.1
0x6024  ldloc.1
0x6025  ldarg.1
0x6026  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x602b  stloc.2
0x602c  ldloc.2
0x602d  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep
0x6032  stloc.3
0x6033  ldloc.3
0x6034  brfalse.s loc_608C
0x6036  ldloc.3
0x6037  ldloc.1
0x6038  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x603d  ldc.i4.0
0x603e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Item(int32)
0x6043  bne.un.s loc_608C
0x6045  ldloc.3
0x6046  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x604b  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Count()
0x6050  ldc.i4.0
0x6051  ble.s    loc_608C
0x6053  ldc.i4.0
0x6054  stloc.s  4
0x6056  br.s     loc_607D
0x6058  ldloc.1
0x6059  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x605e  ldloc.s  4
0x6060  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Item(int32)
0x6065  stloc.s  5
0x6067  ldloc.s  5
0x6069  ldloc.2
0x606a  beq.s    loc_6077
0x606c  ldloc.s  5
0x606e  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep
0x6073  brfalse.s loc_6077
0x6075  ldc.i4.0
0x6076  stloc.0
0x6077  ldloc.s  4
0x6079  ldc.i4.1
0x607a  add
0x607b  stloc.s  4
0x607d  ldloc.s  4
0x607f  ldloc.1
0x6080  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x6085  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Count()
0x608a  blt.s    loc_6058
0x608c  ldloc.0
0x608d  stloc.s  6
0x608f  leave.s  loc_609C
0x6091  stloc.s  7
0x6093  ldarg.0
0x6094  ldloc.s  7
0x6096  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x609b  throw
0x609c  ldloc.s  6
0x609e  ret
```
