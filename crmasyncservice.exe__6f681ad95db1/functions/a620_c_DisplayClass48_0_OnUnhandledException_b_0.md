# <>c__DisplayClass48_0::<OnUnhandledException>b__0

- ea: `0xa620`
- end: `0xa6bc`
- name: `<>c__DisplayClass48_0::<OnUnhandledException>b__0`
- size: `156`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0xc50`
- `0x1830`
- `0x1850`

## string_xrefs

- `0xa68a`: `Exception while executing async service: {0} - {1}`

## pseudocode

```c

```

## disassembly

```asm
0xa620  ldarg.0
0xa621  ldfld    class Microsoft.Crm.Asynchronous.AsyncService <>c__DisplayClass48_0::<>4__this
0xa626  ldc.i4.1
0xa627  ldc.i4   0xC0004403
0xa62c  conv.u8
0xa62d  ldc.i4.2
0xa62e  newarr   [mscorlib]System.Object
0xa633  dup
0xa634  ldc.i4.0
0xa635  call     string Microsoft.Crm.Asynchronous.AsyncService::get_HostName()
0xa63a  stelem.ref
0xa63b  dup
0xa63c  ldc.i4.1
0xa63d  ldarg.0
0xa63e  ldfld    class [mscorlib]System.UnhandledExceptionEventArgs <>c__DisplayClass48_0::e
0xa643  callvirt instance object [mscorlib]System.UnhandledExceptionEventArgs::get_ExceptionObject()
0xa648  callvirt instance string [mscorlib]System.Object::ToString()
0xa64d  stelem.ref
0xa64e  call     instance void Microsoft.Crm.Asynchronous.AsyncService::WriteEventLog(valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventLogId, object[] parameters)
0xa653  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::get_Instance()
0xa658  ldarg.0
0xa659  ldfld    class Microsoft.Crm.Asynchronous.AsyncService <>c__DisplayClass48_0::<>4__this
0xa65e  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncService::get_AsyncStartStopActivityId()
0xa663  ldstr    aAsync// "Async"
0xa668  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceProcessSettings::get_Identifier()
0xa66d  ldarg.0
0xa66e  ldfld    class [mscorlib]System.UnhandledExceptionEventArgs <>c__DisplayClass48_0::e
0xa673  callvirt instance object [mscorlib]System.UnhandledExceptionEventArgs::get_ExceptionObject()
0xa678  callvirt instance string [mscorlib]System.Object::ToString()
0xa67d  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDiagnosticsEventSource::UnhandledExceptionEvent(valuetype [mscorlib]System.Guid, string, string, string)
0xa682  ldnull
0xa683  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xa688  ldc.i4.s 0x15
0xa68a  ldstr    aExceptionWhile_12// "Exception while executing async service"...
0xa68f  ldc.i4.2
0xa690  newarr   [mscorlib]System.Object
0xa695  dup
0xa696  ldc.i4.0
0xa697  ldarg.0
0xa698  ldfld    class Microsoft.Crm.Asynchronous.AsyncService <>c__DisplayClass48_0::<>4__this
0xa69d  call     instance string [System.ServiceProcess]System.ServiceProcess.ServiceBase::get_ServiceName()
0xa6a2  stelem.ref
0xa6a3  dup
0xa6a4  ldc.i4.1
0xa6a5  ldarg.0
0xa6a6  ldfld    class [mscorlib]System.UnhandledExceptionEventArgs <>c__DisplayClass48_0::e
0xa6ab  callvirt instance object [mscorlib]System.UnhandledExceptionEventArgs::get_ExceptionObject()
0xa6b0  callvirt instance string [mscorlib]System.Object::ToString()
0xa6b5  stelem.ref
0xa6b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa6bb  ret
```
