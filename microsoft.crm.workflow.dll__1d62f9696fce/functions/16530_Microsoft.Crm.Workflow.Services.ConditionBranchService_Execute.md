# Microsoft.Crm.Workflow.Services.ConditionBranchService::Execute

- ea: `0x16530`
- end: `0x165a1`
- name: `Microsoft.Crm.Workflow.Services.ConditionBranchService::Execute`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x9090`
- `0x14f10`
- `0x16530`
- `0x2d4e0`
- `0x2d500`
- `0x2d520`

## pseudocode

```c

```

## disassembly

```asm
0x16530  ldarg.2
0x16531  callvirt instance class [System.Activities]System.Activities.InArgument`1<bool> Microsoft.Crm.Workflow.Activities.ConditionBranch::get_Condition()
0x16536  ldarg.1
0x16537  callvirt instance var<u1> class [System.Activities]System.Activities.InArgument`1<bool>::Get(!!T0)
0x1653c  stloc.0
0x1653d  ldarg.1
0x1653e  callvirt T0x2B000007
0x16543  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Workflow.Services.ExecutionPointersService::get_PointersDictionary()
0x16548  stloc.1
0x16549  ldloc.1
0x1654a  brfalse.s loc_1655C
0x1654c  ldloc.1
0x1654d  ldarg.2
0x1654e  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x16553  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::ContainsKey(var<u1>)
0x16558  brfalse.s loc_1655C
0x1655a  ldc.i4.1
0x1655b  stloc.0
0x1655c  ldarg.0
0x1655d  ldarg.1
0x1655e  ldstr    aConditionbranc// "conditionBranchResult"
0x16563  call     T0x2B00000F
0x16568  ldloc.0
0x16569  callvirt instance void Microsoft.Crm.Workflow.ConditionBranchResultProperty::set_Result(bool value)
0x1656e  ldloc.0
0x1656f  brfalse.s loc_16588
0x16571  ldarg.2
0x16572  callvirt instance class [System.Activities]System.Activities.Activity Microsoft.Crm.Workflow.Activities.ConditionBranch::get_Then()
0x16577  brfalse.s loc_16588
0x16579  ldarg.1
0x1657a  ldarg.2
0x1657b  callvirt instance class [System.Activities]System.Activities.Activity Microsoft.Crm.Workflow.Activities.ConditionBranch::get_Then()
0x16580  ldnull
0x16581  ldnull
0x16582  callvirt instance class [System.Activities]System.Activities.ActivityInstance [System.Activities]System.Activities.NativeActivityContext::ScheduleActivity(class [System.Activities]System.Activities.Activity, class [System.Activities]System.Activities.CompletionCallback, class [System.Activities]System.Activities.FaultCallback)
0x16587  pop
0x16588  ldloc.0
0x16589  brtrue.s loc_165A0
0x1658b  ldarg.2
0x1658c  callvirt instance class [System.Activities]System.Activities.Activity Microsoft.Crm.Workflow.Activities.ConditionBranch::get_Else()
0x16591  brfalse.s loc_165A0
0x16593  ldarg.1
0x16594  ldarg.2
0x16595  callvirt instance class [System.Activities]System.Activities.Activity Microsoft.Crm.Workflow.Activities.ConditionBranch::get_Else()
0x1659a  callvirt instance class [System.Activities]System.Activities.ActivityInstance [System.Activities]System.Activities.NativeActivityContext::ScheduleActivity(class [System.Activities]System.Activities.Activity)
0x1659f  pop
0x165a0  ret
```
