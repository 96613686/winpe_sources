# Microsoft.Crm.Asynchronous.QueueManager::DiagnoseOrgMaxParallelThreadCountSemapohore

- ea: `0xaf50`
- end: `0xb0eb`
- name: `Microsoft.Crm.Asynchronous.QueueManager::DiagnoseOrgMaxParallelThreadCountSemapohore`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0xa9d0`

## callees

- `0x2730`
- `0x6d60`
- `0xaf50`
- `0xb0f0`
- `0x10900`
- `0x11420`
- `0x17a50`

## string_xrefs

- `0xaf50`: `OrgThreadCountSemaphore`

## pseudocode

```c

```

## disassembly

```asm
0xaf50  ldstr    aOrgthreadcount// "OrgThreadCountSemaphore"
0xaf55  stloc.0
0xaf56  ldarg.0
0xaf57  ldfld    class Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine Microsoft.Crm.Asynchronous.QueueManager::_executionEngine
0xaf5c  callvirt instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim> Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::get_OrgMaxParalleThreadCountSemaphore()
0xaf61  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim>::GetEnumerator()
0xaf66  stloc.1
0xaf67  br       loc_B0D3
0xaf6c  newobj   instance void <>c__DisplayClass48_0::.ctor()
0xaf71  stloc.2
0xaf72  ldloc.2
0xaf73  ldloc.1
0xaf74  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim>>::get_Current()
0xaf79  stfld    valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim> <>c__DisplayClass48_0::kvp
0xaf7e  ldloc.2
0xaf7f  ldflda   valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim> <>c__DisplayClass48_0::kvp
0xaf84  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim>::get_Value()
0xaf89  stloc.3
0xaf8a  ldarg.1
0xaf8b  ldloc.2
0xaf8c  ldflda   valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim> <>c__DisplayClass48_0::kvp
0xaf91  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim>::get_Key()
0xaf96  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int32>::ContainsKey(var<u1>)
0xaf9b  brfalse.s loc_AFB2
0xaf9d  ldarg.1
0xaf9e  ldloc.2
0xaf9f  ldflda   valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim> <>c__DisplayClass48_0::kvp
0xafa4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim>::get_Key()
0xafa9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int32>::get_Item(void)
0xafae  stloc.s  4
0xafb0  br.s     loc_B01D
0xafb2  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0xafb7  ldstr    aOrgmaxparallel// "OrgMaxParallelSettingsNotFound"
0xafbc  ldstr    asc_276F8// ""
0xafc1  ldarg.0
0xafc2  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0xafc7  ldloc.2
0xafc8  ldflda   valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim> <>c__DisplayClass48_0::kvp
0xafcd  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim>::get_Key()
0xafd2  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xafd7  ldc.i4.0
0xafd8  ldc.i4.0
0xafd9  ldc.i4.0
0xafda  ldc.i4.0
0xafdb  ldc.i4.0
0xafdc  ldc.i4.0
0xafdd  ldc.i4.0
0xafde  conv.i8
0xafdf  ldstr    asc_276F8// ""
0xafe4  ldc.r8   0.0
0xafed  ldc.i4.0
0xafee  ldloca.s 8
0xaff0  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xaff6  ldloc.s  8
0xaff8  ldc.r8   0.0
0xb001  ldc.r8   0.0
0xb00a  ldc.r8   0.0
0xb013  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncSemaphoreDiagnosticInfo(string diagnosticInfoName, [opt] string semaphoreName, [opt] string queueName, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> organizationId, [opt] int32 estimatedSemaphoreInUse, [opt] int32 actualSemaphoreInUse, [opt] int32 semaphoreLeak, [opt] int32 releaseCount, [opt] int32 currentSemaphoreCount, [opt] int32 semaphoreMaxCount, [opt] int64 elapsedTimeInSec, [opt] string message, [opt] float64 timeIntervalInMinutes, [opt] int32 operationType, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> eventId, [opt] float64 executionTime, [opt] float64 inMemoryDelay, [opt] float64 dbDelay)
0xb018  br       loc_B0D3
0xb01d  ldarg.0
0xb01e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object> Microsoft.Crm.Asynchronous.QueueManager::_executingOperations
0xb023  ldloc.2
0xb024  ldftn    instance bool <>c__DisplayClass48_0::<DiagnoseOrgMaxParallelThreadCountSemapohore>b__0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object> m)
0xb02a  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object>, bool>::.ctor(object, native int)
0xb02f  call     T0x2B000015
0xb034  stloc.s  5
0xb036  ldloc.s  4
0xb038  ldloc.3
0xb039  callvirt instance int32 [mscorlib]System.Threading.SemaphoreSlim::get_CurrentCount()
0xb03e  sub
0xb03f  stloc.s  6
0xb041  ldarg.0
0xb042  ldloc.3
0xb043  ldloc.s  6
0xb045  ldloc.s  5
0xb047  ldloc.s  4
0xb049  ldloc.0
0xb04a  ldc.i4.m1
0xb04b  call     instance bool Microsoft.Crm.Asynchronous.QueueManager::DetectAndMitigateLeak(class [mscorlib]System.Threading.SemaphoreSlim semaphore, int32 expectedValue, int32 actualCount, int32 maxSemaphoreCount, string semaphoreName, [opt] int32 operationType)
0xb050  pop
0xb051  ldloc.s  6
0xb053  ldloc.s  5
0xb055  sub
0xb056  stloc.s  7
0xb058  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0xb05d  ldstr    aSemaphorestatu// "SemaphoreStatus"
0xb062  ldloc.0
0xb063  ldarg.0
0xb064  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0xb069  ldloc.s  4
0xb06b  stloc.s  9
0xb06d  ldloc.3
0xb06e  callvirt instance int32 [mscorlib]System.Threading.SemaphoreSlim::get_CurrentCount()
0xb073  stloc.s  0xA
0xb075  ldloc.s  6
0xb077  stloc.s  0xB
0xb079  ldloc.s  5
0xb07b  stloc.s  0xC
0xb07d  ldloc.2
0xb07e  ldflda   valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim> <>c__DisplayClass48_0::kvp
0xb083  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim>::get_Key()
0xb088  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xb08d  ldloc.s  0xB
0xb08f  ldloc.s  0xC
0xb091  ldloc.s  7
0xb093  ldc.i4.0
0xb094  ldloc.s  0xA
0xb096  ldloc.s  9
0xb098  ldc.i4.0
0xb099  conv.i8
0xb09a  ldstr    asc_276F8// ""
0xb09f  ldc.r8   0.0
0xb0a8  ldc.i4.0
0xb0a9  ldloca.s 8
0xb0ab  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xb0b1  ldloc.s  8
0xb0b3  ldc.r8   0.0
0xb0bc  ldc.r8   0.0
0xb0c5  ldc.r8   0.0
0xb0ce  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncSemaphoreDiagnosticInfo(string diagnosticInfoName, [opt] string semaphoreName, [opt] string queueName, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> organizationId, [opt] int32 estimatedSemaphoreInUse, [opt] int32 actualSemaphoreInUse, [opt] int32 semaphoreLeak, [opt] int32 releaseCount, [opt] int32 currentSemaphoreCount, [opt] int32 semaphoreMaxCount, [opt] int64 elapsedTimeInSec, [opt] string message, [opt] float64 timeIntervalInMinutes, [opt] int32 operationType, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> eventId, [opt] float64 executionTime, [opt] float64 inMemoryDelay, [opt] float64 dbDelay)
0xb0d3  ldloc.1
0xb0d4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb0d9  brtrue   loc_AF6C
0xb0de  leave.s  loc_B0EA
0xb0e0  ldloc.1
0xb0e1  brfalse.s loc_B0E9
0xb0e3  ldloc.1
0xb0e4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb0e9  endfinally
0xb0ea  ret
```
