# Microsoft.Crm.Workflow.ActivityHost::PauseWorkflow

- ea: `0x910`
- end: `0xa4d`
- name: `Microsoft.Crm.Workflow.ActivityHost::PauseWorkflow`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x810`

## callees

- `0x910`
- `0xb50`
- `0xb70`

## string_xrefs

- `0xa0c`: `Encountered attempt to unload aborted workflow '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x910  ldarg.0
0x911  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::_loadedInstances
0x916  stloc.0
0x917  ldc.i4.0
0x918  stloc.1
0x919  ldloc.0
0x91a  ldloca.s 1
0x91c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x921  ldarg.0
0x922  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::_loadedInstances
0x927  ldarg.1
0x928  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>>::ContainsKey(var<u1>)
0x92d  brfalse  loc_A40
0x932  ldarg.0
0x933  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::_loadedInstances
0x938  ldarg.1
0x939  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>>::get_Item(void)
0x93e  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>::get_Item2()
0x943  stloc.2
0x944  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowOperationPausedResult::.ctor()
0x949  stloc.3
0x94a  ldnull
0x94b  ldloc.2
0x94c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x951  ldc.i4.s 0x1E
0x953  ldstr    aPausingWorkflo// "Pausing workflow instance {0}."
0x958  ldc.i4.1
0x959  newarr   [mscorlib]System.Object
0x95e  dup
0x95f  ldc.i4.0
0x960  ldarg.1
0x961  box      [mscorlib]System.Guid
0x966  stelem.ref
0x967  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x96c  ldarg.0
0x96d  ldloc.3
0x96e  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::OnPostWorkflowThreadEnded(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult)
0x973  ldloc.2
0x974  ldloc.3
0x975  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::EndProcessing(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult)
0x97a  ldloc.2
0x97b  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::get_InstanceState()
0x980  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime::get_MaxValue()
0x985  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::set_PostponeUntil(valuetype [mscorlib]System.DateTime)
0x98a  ldarg.0
0x98b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::_loadedInstances
0x990  ldarg.1
0x991  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>>::get_Item(void)
0x996  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>::get_Item2()
0x99b  ldc.i4.1
0x99c  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext::set_GoingIdle(bool)
0x9a1  ldarg.0
0x9a2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::_loadedInstances
0x9a7  ldarg.1
0x9a8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>>::get_Item(void)
0x9ad  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>::get_Item1()
0x9b2  callvirt instance void [System.Activities]System.Activities.WorkflowApplication::Unload()
0x9b7  leave    loc_A4C
0x9bc  stloc.s  4
0x9be  ldloc.s  4
0x9c0  isinst   [mscorlib]System.TimeoutException
0x9c5  brtrue.s loc_9D0
0x9c7  ldloc.s  4
0x9c9  isinst   [System.Activities]System.Activities.InvalidWorkflowException
0x9ce  brfalse.s loc_9F9
0x9d0  ldarg.0
0x9d1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::_loadedInstances
0x9d6  ldarg.1
0x9d7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>>::get_Item(void)
0x9dc  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>::get_Item1()
0x9e1  ldstr    aUnableToPauseW// "Unable to pause workflow operation: "
0x9e6  ldloc.s  4
0x9e8  callvirt instance string [mscorlib]System.Exception::get_Message()
0x9ed  call     string [mscorlib]System.String::Concat(string, string)
0x9f2  callvirt instance void [System.Activities]System.Activities.WorkflowApplication::Abort(string)
0x9f7  br.s     loc_A35
0x9f9  ldloc.s  4
0x9fb  isinst   [System.Activities]System.Activities.WorkflowApplicationAbortedException
0xa00  brfalse.s loc_A2C
0xa02  ldloc.s  4
0xa04  ldloc.2
0xa05  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0xa0a  ldc.i4.s 0x1E
0xa0c  ldstr    aEncounteredAtt// "Encountered attempt to unload aborted w"...
0xa11  ldc.i4.1
0xa12  newarr   [mscorlib]System.Object
0xa17  dup
0xa18  ldc.i4.0
0xa19  ldloc.2
0xa1a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0xa1f  box      [mscorlib]System.Guid
0xa24  stelem.ref
0xa25  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa2a  br.s     loc_A35
0xa2c  ldarg.0
0xa2d  ldloc.2
0xa2e  ldloc.s  4
0xa30  call     instance void Microsoft.Crm.Workflow.ActivityHost::LogException(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext context, class [mscorlib]System.Exception ex)
0xa35  leave.s  loc_A4C
0xa37  ldarg.0
0xa38  ldloc.2
0xa39  ldloc.3
0xa3a  call     instance void Microsoft.Crm.Workflow.ActivityHost::EndAsyncEvent(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext context, class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult result)
0xa3f  endfinally
0xa40  leave.s  loc_A4C
0xa42  ldloc.1
0xa43  brfalse.s loc_A4B
0xa45  ldloc.0
0xa46  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xa4b  endfinally
0xa4c  ret
```
