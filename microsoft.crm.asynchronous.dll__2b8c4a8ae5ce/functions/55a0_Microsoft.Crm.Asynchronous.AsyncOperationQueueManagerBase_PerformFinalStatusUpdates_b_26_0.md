# Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::<PerformFinalStatusUpdates>b__26_0

- ea: `0x55a0`
- end: `0x5634`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::<PerformFinalStatusUpdates>b__26_0`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x53b0`
- `0x55a0`
- `0x7870`
- `0x78c0`
- `0xa980`
- `0xb3f0`

## pseudocode

```c

```

## disassembly

```asm
0x55a0  ldarg.1
0x55a1  callvirt instance void Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess::UpdateSpecialTransitions()
0x55a6  ldarg.0
0x55a7  call     instance object Microsoft.Crm.Asynchronous.QueueManager::get_SpecialTransitionsLock()
0x55ac  stloc.0
0x55ad  ldc.i4.0
0x55ae  stloc.1
0x55af  ldloc.0
0x55b0  ldloca.s 1
0x55b2  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x55b7  ldnull
0x55b8  stloc.2
0x55b9  ldarg.0
0x55ba  ldarg.2
0x55bb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x55c0  ldloca.s 2
0x55c2  call     instance bool Microsoft.Crm.Asynchronous.QueueManager::TryGetSpecialTransitionsNoLock(valuetype [mscorlib]System.Guid organizationId, [out] class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest>& specialTransitions)
0x55c7  brfalse.s loc_5621
0x55c9  ldloc.2
0x55ca  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest>::GetEnumerator()
0x55cf  stloc.3
0x55d0  br.s     loc_5608
0x55d2  ldloca.s 3
0x55d4  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest>::get_Current()
0x55d9  stloc.s  4
0x55db  ldarg.0
0x55dc  ldloca.s 4
0x55de  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest>::get_Key()
0x55e3  ldloca.s 4
0x55e5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest>::get_Value()
0x55ea  ldc.i4.0
0x55eb  ldc.i4.0
0x55ec  ldarg.1
0x55ed  ldc.r8   0.0
0x55f6  ldarg.2
0x55f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x55fc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5601  ldnull
0x5602  call     instance class Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::DoSpecialTransition(valuetype [mscorlib]System.Guid eventId, valuetype Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest exitRequest, bool removeEvent, bool autoResume, class Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess queueDataAccess, float64 executionTime, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid telemetryActivityId, class Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent)
0x5607  pop
0x5608  ldloca.s 3
0x560a  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest>::MoveNext()
0x560f  brtrue.s loc_55D2
0x5611  leave.s  loc_562D
0x5613  ldloca.s 3
0x5615  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, valuetype Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest>
0x561b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5620  endfinally
0x5621  leave.s  loc_562D
0x5623  ldloc.1
0x5624  brfalse.s loc_562C
0x5626  ldloc.0
0x5627  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x562c  endfinally
0x562d  ldarg.1
0x562e  callvirt instance void Microsoft.Crm.Asynchronous.IAsyncOperationQueueDataAccess::ReturnLockedToReady()
0x5633  ret
```
