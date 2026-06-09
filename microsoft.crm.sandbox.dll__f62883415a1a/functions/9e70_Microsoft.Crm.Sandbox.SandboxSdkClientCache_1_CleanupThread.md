# Microsoft.Crm.Sandbox.SandboxSdkClientCache`1::CleanupThread

- ea: `0x9e70`
- end: `0xa0d0`
- name: `Microsoft.Crm.Sandbox.SandboxSdkClientCache`1::CleanupThread`
- size: `608`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1420`
- `0x1450`
- `0x14d0`
- `0x3500`
- `0x80a0`
- `0x9e70`

## string_xrefs

- `0x9e77`: `SandboxClientCache.CleanupThread: enter`
- `0x9e90`: `SandboxClientCache.CleanupThread: CleanupThread sleeping: {0}`
- `0x9ed3`: `SandboxClientCache.CleanupThread: AutoEventCleanupThread signalled`
- `0x9ef2`: `SandboxClientCache.CleanupThread: CleanupThread shutdown`
- `0x9f0e`: `SandboxClientCache.CleanupThread: CleanupThread wake up: {0}`
- `0x9f3a`: `SandboxClientCache.CleanupThread: before: _clientDictionary.Count: {0}`
- `0xa01d`: `rSandboxClientCache.CleanupThread: emoved client: {0}`
- `0xa06a`: `SandboxClientCache.CleanupThread: after: _clientDictionary.Count: {0}`
- `0xa098`: `SandboxClientCache.CleanupThread: exit: CleanupThread`
- `0xa0b8`: `SandboxClientCache.CleanupThread: EXCEPTION {0}`

## pseudocode

```c

```

## disassembly

```asm
0x9e70  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9e75  ldc.i4.s 0x26
0x9e77  ldstr    aSandboxclientc_8// "SandboxClientCache.CleanupThread: enter"
0x9e7c  ldc.i4.0
0x9e7d  newarr   [mscorlib]System.Object
0x9e82  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x9e87  ldc.i4.0
0x9e88  stloc.0
0x9e89  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9e8e  ldc.i4.s 0x21
0x9e90  ldstr    aSandboxclientc_9// "SandboxClientCache.CleanupThread: Clean"...
0x9e95  ldc.i4.1
0x9e96  newarr   [mscorlib]System.Object
0x9e9b  dup
0x9e9c  ldc.i4.0
0x9e9d  ldloc.0
0x9e9e  box      [mscorlib]System.Int32
0x9ea3  stelem.ref
0x9ea4  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x9ea9  ldarg.0
0x9eaa  call     instance class Microsoft.Crm.Sandbox.SandboxWorkerConfiguration class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::get_WorkerConfiguration()
0x9eaf  ldc.i4.2
0x9eb0  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::get_Item(valuetype Microsoft.Crm.Sandbox.SandboxWorkerProperty key)
0x9eb5  stloc.1
0x9eb6  ldarg.0
0x9eb7  call     instance class [mscorlib]System.Threading.AutoResetEvent class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::get_AutoEventCleanupThread()
0x9ebc  ldc.i4.0
0x9ebd  ldc.i4.0
0x9ebe  ldloc.1
0x9ebf  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x9ec4  ldc.i4.0
0x9ec5  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(valuetype [mscorlib]System.TimeSpan, bool)
0x9eca  brfalse.s loc_9F07
0x9ecc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9ed1  ldc.i4.s 0x21
0x9ed3  ldstr    aSandboxclientc_10// "SandboxClientCache.CleanupThread: AutoE"...
0x9ed8  ldc.i4.0
0x9ed9  newarr   [mscorlib]System.Object
0x9ede  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x9ee3  ldarg.0
0x9ee4  call     instance bool class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::get_Shutdown()
0x9ee9  brfalse.s loc_9F27
0x9eeb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9ef0  ldc.i4.s 0x26
0x9ef2  ldstr    aSandboxclientc_11// "SandboxClientCache.CleanupThread: Clean"...
0x9ef7  ldc.i4.0
0x9ef8  newarr   [mscorlib]System.Object
0x9efd  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x9f02  br       loc_A091
0x9f07  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9f0c  ldc.i4.s 0x21
0x9f0e  ldstr    aSandboxclientc_12// "SandboxClientCache.CleanupThread: Clean"...
0x9f13  ldc.i4.1
0x9f14  newarr   [mscorlib]System.Object
0x9f19  dup
0x9f1a  ldc.i4.0
0x9f1b  ldloc.0
0x9f1c  box      [mscorlib]System.Int32
0x9f21  stelem.ref
0x9f22  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x9f27  ldloc.0
0x9f28  ldc.i4.1
0x9f29  add
0x9f2a  stloc.0
0x9f2b  ldc.i4.s 0x11
0x9f2d  ldloc.0
0x9f2e  call     void Microsoft.Crm.Sandbox.SandboxUtility::CrashForWatson(valuetype Microsoft.Crm.Sandbox.SandboxProperty property, int32 loopCount)
0x9f33  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9f38  ldc.i4.s 0x21
0x9f3a  ldstr    aSandboxclientc_13// "SandboxClientCache.CleanupThread: befor"...
0x9f3f  ldc.i4.1
0x9f40  newarr   [mscorlib]System.Object
0x9f45  dup
0x9f46  ldc.i4.0
0x9f47  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>> class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_clientDictionary
0x9f4c  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>>::get_Count()
0x9f51  box      [mscorlib]System.Int32
0x9f56  stelem.ref
0x9f57  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x9f5c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<var<u1>>::.ctor()
0x9f61  stloc.2
0x9f62  ldarg.0
0x9f63  call     instance class Microsoft.Crm.Sandbox.SandboxWorkerConfiguration class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::get_WorkerConfiguration()
0x9f68  ldc.i4.3
0x9f69  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::get_Item(valuetype Microsoft.Crm.Sandbox.SandboxWorkerProperty key)
0x9f6e  stloc.3
0x9f6f  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_clientLock
0x9f74  ldc.i4.2
0x9f75  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x9f7a  stloc.s  4
0x9f7c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>> class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_clientDictionary
0x9f81  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>>::GetEnumerator()
0x9f86  stloc.s  5
0x9f88  br.s     loc_9FC7
0x9f8a  ldloca.s 5
0x9f8c  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, var<u1>>::get_Current()
0x9f91  stloc.s  6
0x9f93  ldloca.s 6
0x9f95  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, var<u1>>::get_Value()
0x9f9a  stloc.s  7
0x9f9c  ldloc.s  7
0x9f9e  box      var<u1>
0x9fa3  callvirt instance valuetype [mscorlib]System.DateTime class Microsoft.Crm.Sandbox.SandboxClientBase`1<class Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_LastUsed()
0x9fa8  stloc.s  8
0x9faa  ldloca.s 8
0x9fac  ldloc.3
0x9fad  conv.r8
0x9fae  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddSeconds(float64)
0x9fb3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x9fb8  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x9fbd  brfalse.s loc_9FC7
0x9fbf  ldloc.2
0x9fc0  ldloc.s  7
0x9fc2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<var<u1>>::Add(var<u1>)
0x9fc7  ldloca.s 5
0x9fc9  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, var<u1>>::MoveNext()
0x9fce  brtrue.s loc_9F8A
0x9fd0  leave.s  loc_9FE0
0x9fd2  ldloca.s 5
0x9fd4  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, var<u1>>
0x9fda  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9fdf  endfinally
0x9fe0  ldloc.2
0x9fe1  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<var<u1>>::GetEnumerator()
0x9fe6  stloc.s  9
0x9fe8  br.s     loc_A03C
0x9fea  ldloca.s 9
0x9fec  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>>::get_Current()
0x9ff1  stloc.s  0xA
0x9ff3  ldloc.s  0xA
0x9ff5  box      var<u1>
0x9ffa  callvirt instance void class Microsoft.Crm.Sandbox.SandboxClientBase`1<class Microsoft.Crm.Sandbox.ISandboxSdkListener>::Stop()
0x9fff  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>> class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_clientDictionary
0xa004  ldloc.s  0xA
0xa006  box      var<u1>
0xa00b  callvirt instance string class Microsoft.Crm.Sandbox.SandboxClientBase`1<class Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_UriText()
0xa010  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>>::Remove(var<u1>)
0xa015  pop
0xa016  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa01b  ldc.i4.s 0x21
0xa01d  ldstr    aRsandboxclient// "rSandboxClientCache.CleanupThread: emov"...
0xa022  ldc.i4.1
0xa023  newarr   [mscorlib]System.Object
0xa028  dup
0xa029  ldc.i4.0
0xa02a  ldloc.s  0xA
0xa02c  box      var<u1>
0xa031  callvirt instance string class Microsoft.Crm.Sandbox.SandboxClientBase`1<class Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_UriText()
0xa036  stelem.ref
0xa037  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0xa03c  ldloca.s 9
0xa03e  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>>::MoveNext()
0xa043  brtrue.s loc_9FEA
0xa045  leave.s  loc_A055
0xa047  ldloca.s 9
0xa049  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>>
0xa04f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa054  endfinally
0xa055  leave.s  loc_A063
0xa057  ldloc.s  4
0xa059  brfalse.s loc_A062
0xa05b  ldloc.s  4
0xa05d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa062  endfinally
0xa063  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa068  ldc.i4.s 0x21
0xa06a  ldstr    aSandboxclientc_14// "SandboxClientCache.CleanupThread: after"...
0xa06f  ldc.i4.1
0xa070  newarr   [mscorlib]System.Object
0xa075  dup
0xa076  ldc.i4.0
0xa077  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>> class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_clientDictionary
0xa07c  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>>::get_Count()
0xa081  box      [mscorlib]System.Int32
0xa086  stelem.ref
0xa087  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0xa08c  br       loc_9E89
0xa091  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa096  ldc.i4.s 0x26
0xa098  ldstr    aSandboxclientc_15// "SandboxClientCache.CleanupThread: exit:"...
0xa09d  ldc.i4.0
0xa09e  newarr   [mscorlib]System.Object
0xa0a3  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0xa0a8  leave.s  loc_A0CF
0xa0aa  pop
0xa0ab  rethrow
0xa0ad  stloc.s  0xB
0xa0af  ldloc.s  0xB
0xa0b1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa0b6  ldc.i4.s 0x26
0xa0b8  ldstr    aSandboxclientc_16// "SandboxClientCache.CleanupThread: EXCEP"...
0xa0bd  ldc.i4.1
0xa0be  newarr   [mscorlib]System.Object
0xa0c3  dup
0xa0c4  ldc.i4.0
0xa0c5  ldloc.s  0xB
0xa0c7  stelem.ref
0xa0c8  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0xa0cd  rethrow
0xa0cf  ret
```
