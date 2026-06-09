# Microsoft.Crm.Workflow.Services.WorkflowService::IsLoggingEnabled

- ea: `0x1a550`
- end: `0x1a5de`
- name: `Microsoft.Crm.Workflow.Services.WorkflowService::IsLoggingEnabled`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a5e0`

## callees

- `0x6960`
- `0x6980`
- `0x69a0`
- `0xef70`
- `0xefd0`
- `0x1a530`
- `0x1a550`

## pseudocode

```c

```

## disassembly

```asm
0x1a550  ldc.i4.1
0x1a551  stloc.0
0x1a552  ldarg.1
0x1a553  call     bool Microsoft.Crm.Workflow.Utility.WorkflowUtility::IsSyncWorkflow(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.IWorkflowContext context)
0x1a558  brtrue.s loc_1A562
0x1a55a  ldarg.1
0x1a55b  call     bool Microsoft.Crm.Workflow.Utility.WorkflowUtility::IsCustomOperation(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.IWorkflowContext context)
0x1a560  brfalse.s loc_1A569
0x1a562  ldarg.1
0x1a563  callvirt instance bool Microsoft.Crm.Workflow.ICommonWorkflowContext::get_IsLoggingEnabled()
0x1a568  ret
0x1a569  ldc.i4.3
0x1a56a  newarr   [mscorlib]System.String
0x1a56f  dup
0x1a570  ldc.i4.0
0x1a571  ldstr    aStagestep// "StageStep"
0x1a576  stelem.ref
0x1a577  dup
0x1a578  ldc.i4.1
0x1a579  ldstr    aConditionstep// "ConditionStep"
0x1a57e  stelem.ref
0x1a57f  dup
0x1a580  ldc.i4.2
0x1a581  ldstr    aWaitstep// "WaitStep"
0x1a586  stelem.ref
0x1a587  stloc.1
0x1a588  ldarg.1
0x1a589  callvirt instance bool Microsoft.Crm.Workflow.ICommonWorkflowContext::get_IsAutoDeleteSet()
0x1a58e  brfalse.s loc_1A5DC
0x1a590  ldarg.2
0x1a591  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.Workflow::get_Activities()
0x1a596  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x1a59b  ldc.i4.1
0x1a59c  bne.un.s loc_1A5DC
0x1a59e  ldarg.1
0x1a59f  callvirt instance bool Microsoft.Crm.Workflow.ICommonWorkflowContext::get_IsCrmUIWorkflow()
0x1a5a4  brfalse.s loc_1A5DC
0x1a5a6  ldloc.1
0x1a5a7  stloc.2
0x1a5a8  ldc.i4.0
0x1a5a9  stloc.3
0x1a5aa  br.s     loc_1A5D6
0x1a5ac  ldloc.2
0x1a5ad  ldloc.3
0x1a5ae  ldelem.ref
0x1a5af  stloc.s  4
0x1a5b1  ldarg.0
0x1a5b2  ldarg.2
0x1a5b3  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.Workflow::get_Activities()
0x1a5b8  ldc.i4.0
0x1a5b9  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x1a5be  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference
0x1a5c3  ldloc.s  4
0x1a5c5  call     instance bool Microsoft.Crm.Workflow.Services.WorkflowService::IsStepOfType(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference activityReference, string stepType)
0x1a5ca  brfalse.s loc_1A5D0
0x1a5cc  ldc.i4.1
0x1a5cd  stloc.0
0x1a5ce  br.s     loc_1A5DC
0x1a5d0  ldc.i4.0
0x1a5d1  stloc.0
0x1a5d2  ldloc.3
0x1a5d3  ldc.i4.1
0x1a5d4  add
0x1a5d5  stloc.3
0x1a5d6  ldloc.3
0x1a5d7  ldloc.2
0x1a5d8  ldlen
0x1a5d9  conv.i4
0x1a5da  blt.s    loc_1A5AC
0x1a5dc  ldloc.0
0x1a5dd  ret
```
