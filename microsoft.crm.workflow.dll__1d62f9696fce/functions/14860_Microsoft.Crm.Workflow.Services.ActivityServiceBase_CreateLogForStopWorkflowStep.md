# Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLogForStopWorkflowStep

- ea: `0x14860`
- end: `0x148a0`
- name: `Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLogForStopWorkflowStep`
- size: `64`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x16410`
- `0x16490`
- `0x1a650`
- `0x1a6d0`

## callees

- `0x14860`
- `0x14930`

## pseudocode

```c

```

## disassembly

```asm
0x14860  ldarg.1
0x14861  isinst   [System.Activities]System.Activities.Statements.TerminateWorkflow
0x14866  stloc.0
0x14867  ldloc.0
0x14868  brtrue.s loc_14894
0x1486a  ldarg.1
0x1486b  isinst   [System.Activities]System.Activities.Statements.Sequence
0x14870  stloc.1
0x14871  ldloc.1
0x14872  brfalse.s loc_14894
0x14874  ldloc.1
0x14875  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x1487a  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x1487f  ldc.i4.1
0x14880  ble.s    loc_14894
0x14882  ldloc.1
0x14883  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [System.Activities]System.Activities.Statements.Sequence::get_Activities()
0x14888  ldc.i4.1
0x14889  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x1488e  isinst   [System.Activities]System.Activities.Statements.TerminateWorkflow
0x14893  stloc.0
0x14894  ldloc.0
0x14895  brfalse.s loc_1489F
0x14897  ldarg.0
0x14898  ldloc.0
0x14899  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLog(class [System.Activities]System.Activities.Activity activity)
0x1489e  pop
0x1489f  ret
```
