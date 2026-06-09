# Microsoft.Crm.Workflow.ActivityHost::OnNotificationTimerEvent

- ea: `0x640`
- end: `0x6ce`
- name: `Microsoft.Crm.Workflow.ActivityHost::OnNotificationTimerEvent`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x640`
- `0x1370`
- `0x1830`

## string_xrefs

- `0x6ad`: `WaitSubscriptionDataAccess.RestartWaitingWorkflowInstances`

## pseudocode

```c

```

## disassembly

```asm
0x640  ldarg.0
0x641  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IWorkflowConfiguration [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::_configuration
0x646  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationList::get_Organizations()
0x64b  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Values()
0x650  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::GetEnumerator()
0x655  stloc.0
0x656  br.s     loc_6B9
0x658  ldloc.0
0x659  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::get_Current()
0x65e  stloc.1
0x65f  ldloc.1
0x660  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationState()
0x665  ldc.i4.1
0x666  bne.un.s loc_6B9
0x668  nop
0x669  ldloc.1
0x66a  newobj   instance void Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config)
0x66f  ldarg.0
0x670  ldfld    int32 Microsoft.Crm.Workflow.ActivityHost::_asyncMaximumRetries
0x675  callvirt instance void Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::RestartWaitingWorkflowInstances(int32 maxRetries)
0x67a  ldarg.0
0x67b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::_eventLog
0x680  ldloc.1
0x681  call     void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventLogHelper::LogOrganizationSuccess(class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration)
0x686  leave.s  loc_6B9
0x688  stloc.2
0x689  ldarg.0
0x68a  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ActivityHostBase::_eventLog
0x68f  ldloc.1
0x690  ldloc.2
0x691  call     void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventLogHelper::LogOrganizationFailure(class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration, class [mscorlib]System.Exception)
0x696  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::get_Instance()
0x69b  ldloc.1
0x69c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x6a1  ldloc.2
0x6a2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x6a7  ldc.i4.m1
0x6a8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6ad  ldstr    aWaitsubscripti// "WaitSubscriptionDataAccess.RestartWaiti"...
0x6b2  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::LogAsyncOperationUnhandledException(valuetype [mscorlib]System.Guid, string, int32, valuetype [mscorlib]System.Guid, string)
0x6b7  leave.s  loc_6B9
0x6b9  ldloc.0
0x6ba  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6bf  brtrue.s loc_658
0x6c1  leave.s  loc_6CD
0x6c3  ldloc.0
0x6c4  brfalse.s loc_6CC
0x6c6  ldloc.0
0x6c7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6cc  endfinally
0x6cd  ret
```
