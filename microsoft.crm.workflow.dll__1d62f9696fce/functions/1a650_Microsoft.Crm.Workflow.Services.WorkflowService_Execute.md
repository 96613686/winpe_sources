# Microsoft.Crm.Workflow.Services.WorkflowService::Execute

- ea: `0x1a650`
- end: `0x1a6c9`
- name: `Microsoft.Crm.Workflow.Services.WorkflowService::Execute`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x14860`
- `0x148a0`
- `0x14ad0`
- `0x14f20`
- `0x1a5e0`
- `0x1a650`
- `0x1a760`

## pseudocode

```c

```

## disassembly

```asm
0x1a650  ldarg.0
0x1a651  ldarg.1
0x1a652  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::InitializeExecutionPropreties(class [System.Activities]System.Activities.NativeActivityContext executionContext)
0x1a657  ldarg.0
0x1a658  ldarg.1
0x1a659  ldarg.2
0x1a65a  call     instance void Microsoft.Crm.Workflow.Services.WorkflowService::SetWorkflowLoggingProperty(class [System.Activities]System.Activities.NativeActivityContext executionContext, class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.Workflow workflow)
0x1a65f  ldarg.s  4
0x1a661  ldarg.1
0x1a662  callvirt instance var<u1> class [System.Activities]System.Activities.Variable`1<class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>>::Get(!!T0)
0x1a667  stloc.0
0x1a668  ldarg.1
0x1a669  callvirt T0x2B000007
0x1a66e  ldloc.0
0x1a66f  callvirt instance void Microsoft.Crm.Workflow.Services.ExecutionPointersService::set_PointersDictionary(class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> value)
0x1a674  ldarg.0
0x1a675  ldarg.3
0x1a676  ldarg.1
0x1a677  ldarg.2
0x1a678  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x1a67d  call     instance bool Microsoft.Crm.Workflow.Services.ActivityServiceBase::SetExecutionPointer(class [System.Activities]System.Activities.Variable`1<int32> executionPointer, class [System.Activities]System.Activities.ActivityContext executionContext, string displayName)
0x1a682  pop
0x1a683  ldarg.3
0x1a684  ldarg.1
0x1a685  callvirt instance var<u1> class [System.Activities]System.Activities.Variable`1<int32>::Get(!!T0)
0x1a68a  stloc.1
0x1a68b  ldloc.1
0x1a68c  ldarg.2
0x1a68d  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.Workflow::get_Activities()
0x1a692  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Count()
0x1a697  bge.s    loc_1A6C8
0x1a699  ldarg.2
0x1a69a  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.Workflow::get_Activities()
0x1a69f  ldloc.1
0x1a6a0  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x1a6a5  stloc.2
0x1a6a6  ldarg.0
0x1a6a7  ldloc.2
0x1a6a8  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference
0x1a6ad  ldarg.1
0x1a6ae  call     instance void Microsoft.Crm.Workflow.Services.WorkflowService::UpdateWorkflowStage(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference stage, class [System.Activities]System.Activities.NativeActivityContext executionContext)
0x1a6b3  ldarg.0
0x1a6b4  ldloc.2
0x1a6b5  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLogForStopWorkflowStep(class [System.Activities]System.Activities.Activity activity)
0x1a6ba  ldarg.1
0x1a6bb  ldloc.2
0x1a6bc  ldarg.2
0x1a6bd  callvirt instance class [System.Activities]System.Activities.CompletionCallback [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.Workflow::get_OnChildComplete()
0x1a6c2  callvirt instance class [System.Activities]System.Activities.ActivityInstance [System.Activities]System.Activities.NativeActivityContext::ScheduleActivity(class [System.Activities]System.Activities.Activity, class [System.Activities]System.Activities.CompletionCallback)
0x1a6c7  pop
0x1a6c8  ret
```
