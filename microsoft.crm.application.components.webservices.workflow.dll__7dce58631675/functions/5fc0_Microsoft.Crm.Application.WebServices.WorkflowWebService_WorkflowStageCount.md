# Microsoft.Crm.Application.WebServices.WorkflowWebService::WorkflowStageCount

- ea: `0x5fc0`
- end: `0x6003`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::WorkflowStageCount`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x5fc0`

## pseudocode

```c

```

## disassembly

```asm
0x5fc0  ldc.i4.0
0x5fc1  stloc.0
0x5fc2  ldarg.0
0x5fc3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x5fc8  ldarg.1
0x5fc9  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5fce  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x5fd3  stloc.1
0x5fd4  ldc.i4.0
0x5fd5  stloc.2
0x5fd6  br.s     loc_5FF3
0x5fd8  ldloc.1
0x5fd9  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x5fde  ldloc.2
0x5fdf  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Item(int32)
0x5fe4  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep
0x5fe9  brfalse.s loc_5FEF
0x5feb  ldloc.0
0x5fec  ldc.i4.1
0x5fed  add
0x5fee  stloc.0
0x5fef  ldloc.2
0x5ff0  ldc.i4.1
0x5ff1  add
0x5ff2  stloc.2
0x5ff3  ldloc.2
0x5ff4  ldloc.1
0x5ff5  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x5ffa  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Count()
0x5fff  blt.s    loc_5FD8
0x6001  ldloc.0
0x6002  ret
```
