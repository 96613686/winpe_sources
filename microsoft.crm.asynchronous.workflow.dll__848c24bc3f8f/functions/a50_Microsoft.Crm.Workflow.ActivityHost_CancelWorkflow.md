# Microsoft.Crm.Workflow.ActivityHost::CancelWorkflow

- ea: `0xa50`
- end: `0xb47`
- name: `Microsoft.Crm.Workflow.ActivityHost::CancelWorkflow`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x810`

## callees

- `0xa50`
- `0xb70`

## string_xrefs

- `0xb10`: `Encountered attempt to terminate aborted workflow '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0xa50  ldarg.0
0xa51  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::_loadedInstances
0xa56  stloc.0
0xa57  ldc.i4.0
0xa58  stloc.1
0xa59  ldloc.0
0xa5a  ldloca.s 1
0xa5c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xa61  ldarg.0
0xa62  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::_loadedInstances
0xa67  ldarg.1
0xa68  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>>::ContainsKey(var<u1>)
0xa6d  brfalse  loc_B3A
0xa72  ldarg.0
0xa73  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::_loadedInstances
0xa78  ldarg.1
0xa79  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>>::get_Item(void)
0xa7e  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>::get_Item2()
0xa83  stloc.2
0xa84  ldnull
0xa85  ldloc.2
0xa86  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0xa8b  ldc.i4.s 0x1E
0xa8d  ldstr    aCancelingWorkf// "Canceling workflow instance {0}."
0xa92  ldc.i4.1
0xa93  newarr   [mscorlib]System.Object
0xa98  dup
0xa99  ldc.i4.0
0xa9a  ldarg.1
0xa9b  box      [mscorlib]System.Guid
0xaa0  stelem.ref
0xaa1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xaa6  ldarg.0
0xaa7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::_loadedInstances
0xaac  ldarg.1
0xaad  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>>::get_Item(void)
0xab2  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>::get_Item1()
0xab7  newobj   instance void [System.Activities]System.Activities.WorkflowApplicationTerminatedException::.ctor()
0xabc  callvirt instance void [System.Activities]System.Activities.WorkflowApplication::Terminate(class [mscorlib]System.Exception)
0xac1  leave    loc_B46
0xac6  stloc.3
0xac7  ldloc.3
0xac8  isinst   [mscorlib]System.TimeoutException
0xacd  brtrue.s loc_AD7
0xacf  ldloc.3
0xad0  isinst   [System.Activities]System.Activities.InvalidWorkflowException
0xad5  brfalse.s loc_AFF
0xad7  ldarg.0
0xad8  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::_loadedInstances
0xadd  ldarg.1
0xade  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>>::get_Item(void)
0xae3  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [System.Activities]System.Activities.WorkflowApplication, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext>::get_Item1()
0xae8  ldstr    aUnableToTermin// "Unable to terminate workflow: "
0xaed  ldloc.3
0xaee  callvirt instance string [mscorlib]System.Exception::get_Message()
0xaf3  call     string [mscorlib]System.String::Concat(string, string)
0xaf8  callvirt instance void [System.Activities]System.Activities.WorkflowApplication::Abort(string)
0xafd  br.s     loc_B38
0xaff  ldloc.3
0xb00  isinst   [System.Activities]System.Activities.WorkflowApplicationAbortedException
0xb05  brfalse.s loc_B30
0xb07  ldloc.3
0xb08  ldloc.2
0xb09  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0xb0e  ldc.i4.s 0x1E
0xb10  ldstr    aEncounteredAtt_0// "Encountered attempt to terminate aborte"...
0xb15  ldc.i4.1
0xb16  newarr   [mscorlib]System.Object
0xb1b  dup
0xb1c  ldc.i4.0
0xb1d  ldloc.2
0xb1e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0xb23  box      [mscorlib]System.Guid
0xb28  stelem.ref
0xb29  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb2e  br.s     loc_B38
0xb30  ldarg.0
0xb31  ldloc.2
0xb32  ldloc.3
0xb33  call     instance void Microsoft.Crm.Workflow.ActivityHost::LogException(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ICommonWorkflowContext context, class [mscorlib]System.Exception ex)
0xb38  leave.s  loc_B46
0xb3a  leave.s  loc_B46
0xb3c  ldloc.1
0xb3d  brfalse.s loc_B45
0xb3f  ldloc.0
0xb40  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xb45  endfinally
0xb46  ret
```
