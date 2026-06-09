# Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::JobLengthTransitionPublisher_OrgJobLengthTransitioned

- ea: `0x6c30`
- end: `0x6c95`
- name: `Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::JobLengthTransitionPublisher_OrgJobLengthTransitioned`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x6c30`
- `0xd520`
- `0xd540`
- `0x10900`
- `0x11380`
- `0x11390`

## pseudocode

```c

```

## disassembly

```asm
0x6c30  ldarg.2
0x6c31  callvirt instance valuetype Microsoft.Crm.Asynchronous.JobLengthRange Microsoft.Crm.Asynchronous.OrgJobLengthTransitionedEventArgs::get_Range()
0x6c36  ldc.i4.1
0x6c37  bne.un.s loc_6C5D
0x6c39  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x6c3e  ldarg.2
0x6c3f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.OrgJobLengthTransitionedEventArgs::get_OrganizationId()
0x6c44  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogOrgEnteredLockedState(valuetype [mscorlib]System.Guid organizationId)
0x6c49  ldarg.0
0x6c4a  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool> Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_longJobsOrgs
0x6c4f  ldarg.2
0x6c50  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.OrgJobLengthTransitionedEventArgs::get_OrganizationId()
0x6c55  ldc.i4.1
0x6c56  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool>::TryAdd(var<u1>, !!T0)
0x6c5b  pop
0x6c5c  ret
0x6c5d  ldarg.0
0x6c5e  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool> Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_longJobsOrgs
0x6c63  ldarg.2
0x6c64  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.OrgJobLengthTransitionedEventArgs::get_OrganizationId()
0x6c69  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool>::ContainsKey(var<u1>)
0x6c6e  brfalse.s loc_6C94
0x6c70  ldarg.0
0x6c71  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool> Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_longJobsOrgs
0x6c76  ldarg.2
0x6c77  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.OrgJobLengthTransitionedEventArgs::get_OrganizationId()
0x6c7c  ldloca.s 0
0x6c7e  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, bool>::TryRemove(var<u1>, !!T0)
0x6c83  pop
0x6c84  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x6c89  ldarg.2
0x6c8a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.OrgJobLengthTransitionedEventArgs::get_OrganizationId()
0x6c8f  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogOrgExitedLockedState(valuetype [mscorlib]System.Guid organizationId)
0x6c94  ret
```
