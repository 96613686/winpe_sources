# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncSemaphoreDiagnosticInfo

- ea: `0x11420`
- end: `0x1147a`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncSemaphoreDiagnosticInfo`
- size: `90`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x62e0`
- `0x69a0`
- `0x6ac0`
- `0x93d0`
- `0xa9d0`
- `0xad30`
- `0xaf50`
- `0xb0f0`
- `0xb1a0`
- `0xb280`
- `0xdde0`

## callees

- `0x11420`
- `0x14000`
- `0x14310`

## pseudocode

```c

```

## disassembly

```asm
0x11420  ldarga.s 4
0x11422  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x11427  brfalse.s loc_11432
0x11429  ldarga.s 4
0x1142b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x11430  br.s     loc_11437
0x11432  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11437  stloc.0
0x11438  ldarga.s 0xF
0x1143a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x1143f  brfalse.s loc_1144A
0x11441  ldarga.s 0xF
0x11443  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x11448  br.s     loc_1144F
0x1144a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1144f  stloc.1
0x11450  call     class Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::get_Instance()
0x11455  ldarg.1
0x11456  ldarg.3
0x11457  ldloc.0
0x11458  ldarg.2
0x11459  ldarg.s  0xA
0x1145b  ldarg.s  9
0x1145d  ldarg.s  5
0x1145f  ldarg.s  6
0x11461  ldarg.s  7
0x11463  ldarg.s  8
0x11465  ldarg.s  0xB
0x11467  ldarg.s  0xC
0x11469  ldarg.s  0xD
0x1146b  ldarg.s  0xE
0x1146d  ldloc.1
0x1146e  ldarg.s  0x10
0x11470  ldarg.s  0x12
0x11472  ldarg.s  0x11
0x11474  callvirt instance void Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::LogAsyncSemaphoreDiagnosticInfo(string diagnosticInfoName, string queueName, valuetype [mscorlib]System.Guid organizationId, string semaphoreName, int32 semaphoreMaxCount, int32 currentSemaphoreCount, int32 estimatedSemaphoreInUse, int32 actualSemaphoreInUse, int32 semaphoreLeakedCount, int32 semaphoreReleasedCount, int64 diagnosticModeExecutionTimeInSec, string message, float64 timeIntervalInMinutes, int32 operationType, valuetype [mscorlib]System.Guid eventId, float64 executionTime, float64 inMemoryDelay, float64 dbDelay)
0x11479  ret
```
