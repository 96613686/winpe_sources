# Microsoft.Crm.Sandbox.SandboxAppDomainHelper::GetCurrentThreadStackTraceAndTrace

- ea: `0xe70`
- end: `0x1001`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainHelper::GetCurrentThreadStackTraceAndTrace`
- size: `401`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xe70`
- `0x1990`
- `0x1f90`
- `0x1fb0`
- `0x2120`
- `0x2140`

## string_xrefs

- `0xe80`: `GetCurrentThreadStackTraceAndAbort: Invalid executeThreadParams`
- `0xe9a`: `GetCurrentThreadStackTraceAndAbort: Invalid TargetThread`
- `0xeb4`: `GetCurrentThreadStackTraceAndAbort: Invalid TraceParameters`
- `0xf28`: `SafeThread`
- `0xf8b`: `Error getting plugin stacktrace when timing out: `
- `0xfef`: `GetCurrentThreadStackTraceAndAbort: Timeout stacktrace for plugin: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xe70  ldarg.1
0xe71  isinst   GetStackThreadStackTraceParam
0xe76  stloc.0
0xe77  ldloc.0
0xe78  brtrue.s loc_E8C
0xe7a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe7f  ldc.i4.1
0xe80  ldstr    aGetcurrentthre// "GetCurrentThreadStackTraceAndAbort: Inv"...
0xe85  ldnull
0xe86  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0xe8b  ret
0xe8c  ldloc.0
0xe8d  callvirt instance class [mscorlib]System.Threading.Thread GetStackThreadStackTraceParam::get_TargetThread()
0xe92  brtrue.s loc_EA6
0xe94  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe99  ldc.i4.1
0xe9a  ldstr    aGetcurrentthre_0// "GetCurrentThreadStackTraceAndAbort: Inv"...
0xe9f  ldnull
0xea0  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0xea5  ret
0xea6  ldloc.0
0xea7  callvirt instance object GetStackThreadStackTraceParam::get_TraceParameters()
0xeac  brtrue.s loc_EC0
0xeae  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xeb3  ldc.i4.1
0xeb4  ldstr    aGetcurrentthre_1// "GetCurrentThreadStackTraceAndAbort: Inv"...
0xeb9  ldnull
0xeba  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0xebf  ret
0xec0  ldsfld   string [mscorlib]System.String::Empty
0xec5  stloc.1
0xec6  newobj   instance void <>c__DisplayClass17_0::.ctor()
0xecb  stloc.2
0xecc  ldloc.0
0xecd  callvirt instance object GetStackThreadStackTraceParam::get_TraceParameters()
0xed2  stsfld   object Microsoft.Crm.Sandbox.SandboxTraceContextHelper::TraceParameters
0xed7  ldloc.2
0xed8  ldloc.0
0xed9  callvirt instance class [mscorlib]System.Threading.Thread GetStackThreadStackTraceParam::get_TargetThread()
0xede  stfld    class [mscorlib]System.Threading.Thread <>c__DisplayClass17_0::executeThread
0xee3  ldc.i4.1
0xee4  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0xee9  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0xeee  newobj   instance void <>c__DisplayClass17_1::.ctor()
0xef3  stloc.3
0xef4  ldloc.3
0xef5  ldloc.2
0xef6  stfld    class <>c__DisplayClass17_0 <>c__DisplayClass17_1::CS$<>8__locals1
0xefb  ldloc.3
0xefc  ldc.i4.0
0xefd  newobj   instance void [mscorlib]System.Threading.ManualResetEvent::.ctor(bool)
0xf02  stfld    class [mscorlib]System.Threading.ManualResetEvent <>c__DisplayClass17_1::safeThreadReady
0xf07  ldloc.3
0xf08  ldc.i4.0
0xf09  newobj   instance void [mscorlib]System.Threading.ManualResetEvent::.ctor(bool)
0xf0e  stfld    class [mscorlib]System.Threading.ManualResetEvent <>c__DisplayClass17_1::safeThreadGracefullyFinish
0xf13  ldloc.3
0xf14  ldftn    instance void <>c__DisplayClass17_1::<GetCurrentThreadStackTraceAndTrace>b__0()
0xf1a  newobj   instance void [mscorlib]System.Threading.ThreadStart::.ctor(object, native int)
0xf1f  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ThreadStart)
0xf24  stloc.s  4
0xf26  ldloc.s  4
0xf28  ldstr    aSafethread// "SafeThread"
0xf2d  callvirt instance void [mscorlib]System.Threading.Thread::set_Name(string)
0xf32  ldloc.s  4
0xf34  callvirt instance void [mscorlib]System.Threading.Thread::Start()
0xf39  ldloc.3
0xf3a  ldfld    class [mscorlib]System.Threading.ManualResetEvent <>c__DisplayClass17_1::safeThreadReady
0xf3f  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0xf44  pop
0xf45  ldloc.3
0xf46  ldfld    class <>c__DisplayClass17_0 <>c__DisplayClass17_1::CS$<>8__locals1
0xf4b  ldfld    class [mscorlib]System.Threading.Thread <>c__DisplayClass17_0::executeThread
0xf50  callvirt instance void [mscorlib]System.Threading.Thread::Suspend()
0xf55  leave.s  loc_F5A
0xf57  pop
0xf58  leave.s  loc_F5A
0xf5a  ldloc.3
0xf5b  ldfld    class <>c__DisplayClass17_0 <>c__DisplayClass17_1::CS$<>8__locals1
0xf60  ldfld    class [mscorlib]System.Threading.Thread <>c__DisplayClass17_0::executeThread
0xf65  ldc.i4.0
0xf66  newobj   instance void [mscorlib]System.Diagnostics.StackTrace::.ctor(class [mscorlib]System.Threading.Thread, bool)
0xf6b  callvirt instance string [mscorlib]System.Object::ToString()
0xf70  stloc.1
0xf71  ldloc.3
0xf72  ldfld    class <>c__DisplayClass17_0 <>c__DisplayClass17_1::CS$<>8__locals1
0xf77  ldfld    class [mscorlib]System.Threading.Thread <>c__DisplayClass17_0::executeThread
0xf7c  callvirt instance void [mscorlib]System.Threading.Thread::Resume()
0xf81  leave.s  loc_FE1
0xf83  stloc.s  5
0xf85  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf8a  ldc.i4.1
0xf8b  ldstr    aErrorGettingPl// "Error getting plugin stacktrace when ti"...
0xf90  ldloc.s  5
0xf92  call     string [mscorlib]System.String::Concat(object, object)
0xf97  ldnull
0xf98  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0xf9d  leave.s  loc_FE1
0xf9f  ldloc.3
0xfa0  ldfld    class [mscorlib]System.Threading.ManualResetEvent <>c__DisplayClass17_1::safeThreadGracefullyFinish
0xfa5  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0xfaa  pop
0xfab  ldloc.s  4
0xfad  callvirt instance void [mscorlib]System.Threading.Thread::Join()
0xfb2  endfinally
0xfb3  ldloc.3
0xfb4  ldfld    class [mscorlib]System.Threading.ManualResetEvent <>c__DisplayClass17_1::safeThreadGracefullyFinish
0xfb9  brfalse.s loc_FC6
0xfbb  ldloc.3
0xfbc  ldfld    class [mscorlib]System.Threading.ManualResetEvent <>c__DisplayClass17_1::safeThreadGracefullyFinish
0xfc1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfc6  endfinally
0xfc7  ldloc.3
0xfc8  ldfld    class [mscorlib]System.Threading.ManualResetEvent <>c__DisplayClass17_1::safeThreadReady
0xfcd  brfalse.s loc_FDA
0xfcf  ldloc.3
0xfd0  ldfld    class [mscorlib]System.Threading.ManualResetEvent <>c__DisplayClass17_1::safeThreadReady
0xfd5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfda  endfinally
0xfdb  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0xfe0  endfinally
0xfe1  ldloc.1
0xfe2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfe7  brtrue.s loc_1000
0xfe9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xfee  ldc.i4.1
0xfef  ldstr    aGetcurrentthre_2// "GetCurrentThreadStackTraceAndAbort: Tim"...
0xff4  ldloc.1
0xff5  call     string [mscorlib]System.String::Format(string, object)
0xffa  ldnull
0xffb  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x1000  ret
```
