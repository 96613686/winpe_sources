# Microsoft.Crm.NotificationManager::NotificationWatcherThreadProc

- ea: `0x14250`
- end: `0x143a1`
- name: `Microsoft.Crm.NotificationManager::NotificationWatcherThreadProc`
- size: `337`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x13080`
- `0x130a0`
- `0x130e0`
- `0x14250`
- `0x14c30`
- `0x14d50`
- `0x1eaa0`
- `0x1f4f0`
- `0x1f510`
- `0x54c10`
- `0x54cc0`
- `0x664b0`

## string_xrefs

- `0x1426a`: `NotificationWatcherThread Started. `
- `0x14347`: `NotificationWatcherThreadProcExit`
- `0x14394`: `NotificationWatcherThreadProc Stopped. `

## pseudocode

```c

```

## disassembly

```asm
0x14250  newobj   instance void <>c__DisplayClass37_0::.ctor()
0x14255  stloc.0
0x14256  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1425b  ldc.i4.s 0x14
0x1425d  ldstr    a0// "{0}"
0x14262  ldc.i4.1
0x14263  newarr   [mscorlib]System.Object
0x14268  dup
0x14269  ldc.i4.0
0x1426a  ldstr    aNotificationwa// "NotificationWatcherThread Started. "
0x1426f  stelem.ref
0x14270  call     void Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x14275  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1427a  pop
0x1427b  ldsfld   string [mscorlib]System.String::Empty
0x14280  pop
0x14281  ldsfld   string [mscorlib]System.String::Empty
0x14286  pop
0x14287  ldloc.0
0x14288  ldarg.0
0x14289  unbox.any NotificationThreadType
0x1428e  ldc.i4.1
0x1428f  ceq
0x14291  stfld    bool <>c__DisplayClass37_0::isOnlineSitewideThread
0x14296  ldloc.0
0x14297  newobj   instance void Microsoft.Crm.ProcessingResult::.ctor()
0x1429c  stfld    class Microsoft.Crm.ProcessingResult <>c__DisplayClass37_0::result
0x142a1  newobj   instance void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmRootExecutionContext::.ctor()
0x142a6  stloc.1
0x142a7  call     class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmLoggerFactory::get_LoggerFactory()
0x142ac  ldtoken  Microsoft.Crm.NotificationManager
0x142b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x142b6  callvirt instance string [mscorlib]System.Type::get_FullName()
0x142bb  callvirt instance class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory::CreateLogger(string)
0x142c0  ldloc.1
0x142c1  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class NotificationThreadActivityType>::get_Instance()
0x142c6  ldloc.0
0x142c7  ldfld    class [mscorlib]System.Func`1<bool> <>c__DisplayClass37_0::<>9__0
0x142cc  dup
0x142cd  brtrue.s loc_142E5
0x142cf  pop
0x142d0  ldloc.0
0x142d1  ldloc.0
0x142d2  ldftn    instance bool <>c__DisplayClass37_0::<NotificationWatcherThreadProc>b__0()
0x142d8  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x142dd  dup
0x142de  stloc.2
0x142df  stfld    class [mscorlib]System.Func`1<bool> <>c__DisplayClass37_0::<>9__0
0x142e4  ldloc.2
0x142e5  call     T0x2B000045
0x142ea  brfalse.s loc_142A1
0x142ec  leave    loc_143A0
0x142f1  ldloc.0
0x142f2  ldfld    class Microsoft.Crm.ProcessingResult <>c__DisplayClass37_0::result
0x142f7  callvirt instance class Microsoft.Crm.NotificationEvent Microsoft.Crm.ProcessingResult::get_LastProcessedEvent()
0x142fc  stloc.3
0x142fd  ldloc.3
0x142fe  brfalse.s loc_14308
0x14300  ldloc.3
0x14301  callvirt instance string Microsoft.Crm.NotificationEvent::get_EventData()
0x14306  br.s     loc_1430D
0x14308  ldsfld   string [mscorlib]System.String::Empty
0x1430d  stloc.s  4
0x1430f  ldloc.3
0x14310  brfalse.s loc_14329
0x14312  ldloc.3
0x14313  callvirt instance valuetype Microsoft.Crm.NotificationEventType Microsoft.Crm.NotificationEvent::get_EventId()
0x14318  stloc.s  7
0x1431a  ldloca.s 7
0x1431c  constrained. Microsoft.Crm.NotificationEventType
0x14322  callvirt instance string [mscorlib]System.Object::ToString()
0x14327  br.s     loc_1432E
0x14329  ldsfld   string [mscorlib]System.String::Empty
0x1432e  stloc.s  5
0x14330  ldloc.3
0x14331  brfalse.s loc_1433B
0x14333  ldloc.3
0x14334  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.NotificationEvent::get_OrganizationId()
0x14339  br.s     loc_14340
0x1433b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x14340  stloc.s  6
0x14342  call     class Microsoft.Crm.Core.Telemetry.EventSources.NotificationWatcherThreadProcTelemetryEvents Microsoft.Crm.Core.Telemetry.EventSources.NotificationWatcherThreadProcTelemetryEvents::get_Instance()
0x14347  ldstr    aNotificationwa_0// "NotificationWatcherThreadProcExit"
0x1434c  ldsfld   class [mscorlib]System.Threading.Thread Microsoft.Crm.NotificationManager::mainNotificationWatcherThread
0x14351  dup
0x14352  brtrue.s loc_14361
0x14354  pop
0x14355  ldloca.s 8
0x14357  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1435d  ldloc.s  8
0x1435f  br.s     loc_1436B
0x14361  call     instance int32 [mscorlib]System.Threading.Thread::get_ManagedThreadId()
0x14366  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1436b  stloc.s  8
0x1436d  ldloca.s 8
0x1436f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x14374  ldloc.s  4
0x14376  ldloc.s  5
0x14378  ldloc.s  6
0x1437a  callvirt instance void Microsoft.Crm.Core.Telemetry.EventSources.NotificationWatcherThreadProcTelemetryEvents::NotificationWatcherThreadProcExit(string eventName, int32 threadId, string notificationEventData, string notificationEventType, valuetype [mscorlib]System.Guid organizationId)
0x1437f  ldnull
0x14380  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x14385  ldc.i4.s 0x14
0x14387  ldstr    a0// "{0}"
0x1438c  ldc.i4.1
0x1438d  newarr   [mscorlib]System.Object
0x14392  dup
0x14393  ldc.i4.0
0x14394  ldstr    aNotificationwa_1// "NotificationWatcherThreadProc Stopped. "
0x14399  stelem.ref
0x1439a  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x1439f  endfinally
0x143a0  ret
```
