# Microsoft.Crm.Workflow.Services.CompositeActivityService::Execute

- ea: `0x16410`
- end: `0x16481`
- name: `Microsoft.Crm.Workflow.Services.CompositeActivityService::Execute`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x14860`
- `0x148a0`
- `0x14930`
- `0x16410`
- `0x2d170`
- `0x2d1d0`

## pseudocode

```c

```

## disassembly

```asm
0x16410  ldarg.2
0x16411  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x16416  ldstr    aCustomactivity_0// "CustomActivityStep"
0x1641b  ldc.i4.4
0x1641c  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x16421  brfalse.s loc_16430
0x16423  ldarg.0
0x16424  ldarg.0
0x16425  ldarg.2
0x16426  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLog(class [System.Activities]System.Activities.Activity activity)
0x1642b  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.CompositeActivityService::_logId
0x16430  ldarg.0
0x16431  ldarg.3
0x16432  ldarg.1
0x16433  ldarg.2
0x16434  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x16439  call     instance bool Microsoft.Crm.Workflow.Services.ActivityServiceBase::SetExecutionPointer(class [System.Activities]System.Activities.Variable`1<int32> executionPointer, class [System.Activities]System.Activities.ActivityContext executionContext, string displayName)
0x1643e  pop
0x1643f  ldarg.3
0x16440  ldarg.1
0x16441  callvirt instance var<u1> class [System.Activities]System.Activities.Variable`1<int32>::Get(!!T0)
0x16446  stloc.0
0x16447  ldarg.2
0x16448  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.Composite::get_Activities()
0x1644d  brfalse.s loc_16480
0x1644f  ldarg.2
0x16450  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.Composite::get_Activities()
0x16455  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x1645a  ldloc.0
0x1645b  ble.s    loc_16480
0x1645d  ldarg.2
0x1645e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.Composite::get_Activities()
0x16463  ldloc.0
0x16464  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x16469  stloc.1
0x1646a  ldarg.0
0x1646b  ldloc.1
0x1646c  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLogForStopWorkflowStep(class [System.Activities]System.Activities.Activity activity)
0x16471  ldarg.1
0x16472  ldloc.1
0x16473  ldarg.2
0x16474  callvirt instance class [System.Activities]System.Activities.CompletionCallback Microsoft.Crm.Workflow.Activities.Composite::get_OnChildComplete()
0x16479  ldnull
0x1647a  callvirt instance class [System.Activities]System.Activities.ActivityInstance [System.Activities]System.Activities.NativeActivityContext::ScheduleActivity(class [System.Activities]System.Activities.Activity, class [System.Activities]System.Activities.CompletionCallback, class [System.Activities]System.Activities.FaultCallback)
0x1647f  pop
0x16480  ret
```
