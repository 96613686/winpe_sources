# Microsoft.Crm.Asynchronous.AsyncEventExceptionCounter::UpdateStatistics

- ea: `0x2860`
- end: `0x28dd`
- name: `Microsoft.Crm.Asynchronous.AsyncEventExceptionCounter::UpdateStatistics`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2860`
- `0x2a70`
- `0x2aa0`
- `0x2d60`
- `0x5f20`
- `0x5f40`
- `0x7b40`
- `0x7b50`
- `0x7dc0`
- `0x122a0`
- `0x13640`

## pseudocode

```c

```

## disassembly

```asm
0x2860  ldarg.1
0x2861  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x2866  isinst   Microsoft.Crm.Asynchronous.AsyncEvent
0x286b  stloc.0
0x286c  ldarg.3
0x286d  callvirt instance bool Microsoft.Crm.Asynchronous.IQueueConfiguration::get_UsePredictiveAsyncOrgLevelThrottle()
0x2872  brfalse.s loc_2886
0x2874  ldarg.0
0x2875  ldloc.0
0x2876  call     instance bool Microsoft.Crm.Asynchronous.AsyncEventExceptionCounter::IsAsyncEventSupportedForStatistics(class Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent)
0x287b  brfalse.s loc_2886
0x287d  ldarg.0
0x287e  ldarg.2
0x287f  call     instance bool Microsoft.Crm.Asynchronous.AsyncEventExceptionCounter::IsAsyncHandlerResultSupportedForStatistics(class Microsoft.Crm.Asynchronous.AsyncHandlerResult result)
0x2884  brtrue.s loc_2887
0x2886  ret
0x2887  ldloc.0
0x2888  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x288d  stloc.1
0x288e  ldloc.0
0x288f  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x2894  stloc.2
0x2895  ldloc.0
0x2896  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Asynchronous.AsyncEvent::get_OwningExtension()
0x289b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_Value()
0x28a0  stloc.3
0x28a1  ldarg.0
0x28a2  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.IOrganizationExceptionCounter> Microsoft.Crm.Asynchronous.AsyncEventExceptionCounter::counter
0x28a7  ldloc.1
0x28a8  ldloc.1
0x28a9  newobj   instance void Microsoft.Crm.Asynchronous.OrganizationExceptionCounter::.ctor(valuetype [mscorlib]System.Guid organizationId)
0x28ae  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.IOrganizationExceptionCounter>::TryAdd(var<u1>, !!T0)
0x28b3  pop
0x28b4  ldarg.0
0x28b5  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.IOrganizationExceptionCounter> Microsoft.Crm.Asynchronous.AsyncEventExceptionCounter::counter
0x28ba  ldloc.1
0x28bb  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.IOrganizationExceptionCounter>::get_Item(void)
0x28c0  ldloc.2
0x28c1  ldloc.3
0x28c2  callvirt instance bool Microsoft.Crm.Asynchronous.IOrganizationExceptionCounter::TryAddEvent(int32 operationType, valuetype [mscorlib]System.Guid operationTypeId)
0x28c7  brfalse.s loc_28DC
0x28c9  ldarg.0
0x28ca  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.IOrganizationExceptionCounter> Microsoft.Crm.Asynchronous.AsyncEventExceptionCounter::counter
0x28cf  ldloc.1
0x28d0  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.IOrganizationExceptionCounter>::get_Item(void)
0x28d5  ldloc.2
0x28d6  ldloc.3
0x28d7  callvirt instance void Microsoft.Crm.Asynchronous.IOrganizationExceptionCounter::IncreaseCounter(int32 operationType, valuetype [mscorlib]System.Guid operationTypeId)
0x28dc  ret
```
