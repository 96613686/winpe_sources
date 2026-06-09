# Microsoft.Crm.Sandbox.SandboxCounter::PublishCounters

- ea: `0x3f00`
- end: `0x487a`
- name: `Microsoft.Crm.Sandbox.SandboxCounter::PublishCounters`
- size: `2426`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x4880`
- `0x4890`

## callees

- `0x1450`
- `0x3f00`
- `0x48a0`
- `0x4ae0`
- `0x4b80`
- `0x4be0`
- `0x4c00`
- `0x5530`
- `0x6cd0`
- `0x6cf0`
- `0x6d10`
- `0x6d40`
- `0x6e80`

## string_xrefs

- `0x4190`: `hostConfiguration`
- `0x43b3`: `SandboxCounters.PublishCounters: assemblyCacheHitRate: {0}`
- `0x43d4`: `SandboxCounters.PublishCounters: _assemblyCacheDiskSpace: {0}`
- `0x43f9`: `SandboxCounters.PublishCounters: _assemblyCacheCount: {0}`
- `0x453d`: `SandboxCounters.PublishCounters: _activePlugins.Count: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3f00  ldarg.0
0x3f01  ldnull
0x3f02  cgt.un
0x3f04  stloc.0
0x3f05  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxCounter::_countersLock
0x3f0a  ldc.i4.0
0x3f0b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x3f10  stloc.s  0x14
0x3f12  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxCounter> Microsoft.Crm.Sandbox.SandboxCounter::_counters
0x3f17  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxCounter>::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<var<u1>, !!T0>)
0x3f1c  stloc.1
0x3f1d  leave.s  loc_3F2B
0x3f1f  ldloc.s  0x14
0x3f21  brfalse.s loc_3F2A
0x3f23  ldloc.s  0x14
0x3f25  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f2a  endfinally
0x3f2b  ldc.i4.0
0x3f2c  stloc.2
0x3f2d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3f32  newobj   instance void Microsoft.Crm.Sandbox.SandboxCounter::.ctor(valuetype [mscorlib]System.Guid organizationId)
0x3f37  stloc.3
0x3f38  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x3f3d  stloc.s  4
0x3f3f  ldloc.1
0x3f40  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxCounter>::get_Values()
0x3f45  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxCounter>::GetEnumerator()
0x3f4a  stloc.s  0x15
0x3f4c  br       loc_40DD
0x3f51  ldloca.s 0x15
0x3f53  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxCounter>::get_Current()
0x3f58  stloc.s  0x16
0x3f5a  ldloc.s  0x16
0x3f5c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxCounter::_organizationId
0x3f61  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3f66  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3f6b  brtrue   loc_40DD
0x3f70  ldloc.s  0x16
0x3f72  callvirt instance bool Microsoft.Crm.Sandbox.SandboxCounter::Expired()
0x3f77  brfalse.s loc_3F8C
0x3f79  ldloc.s  4
0x3f7b  ldloc.s  0x16
0x3f7d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxCounter::_organizationId
0x3f82  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x3f87  br       loc_40DD
0x3f8c  ldloc.s  0x16
0x3f8e  ldfld    bool Microsoft.Crm.Sandbox.SandboxCounter::_inAssemblyCache
0x3f93  brfalse.s loc_3F99
0x3f95  ldloc.2
0x3f96  ldc.i4.1
0x3f97  add
0x3f98  stloc.2
0x3f99  ldloc.0
0x3f9a  brfalse  loc_40C1
0x3f9f  ldloc.3
0x3fa0  dup
0x3fa1  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheHits
0x3fa6  ldloc.s  0x16
0x3fa8  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheHits
0x3fad  add
0x3fae  stfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheHits
0x3fb3  ldloc.3
0x3fb4  dup
0x3fb5  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheMisses
0x3fba  ldloc.s  0x16
0x3fbc  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheMisses
0x3fc1  add
0x3fc2  stfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheMisses
0x3fc7  ldloc.3
0x3fc8  dup
0x3fc9  ldfld    float64 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheDiskSpace
0x3fce  ldloc.s  0x16
0x3fd0  ldfld    float64 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheDiskSpace
0x3fd5  add
0x3fd6  stfld    float64 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheDiskSpace
0x3fdb  ldloc.3
0x3fdc  dup
0x3fdd  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheCount
0x3fe2  ldloc.s  0x16
0x3fe4  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheCount
0x3fe9  add
0x3fea  stfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheCount
0x3fef  ldloc.3
0x3ff0  dup
0x3ff1  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_workerProcessSerialCount
0x3ff6  ldloc.s  0x16
0x3ff8  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_workerProcessSerialCount
0x3ffd  add
0x3ffe  stfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_workerProcessSerialCount
0x4003  ldloc.3
0x4004  dup
0x4005  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_workerProcessCrashed
0x400a  ldloc.s  0x16
0x400c  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_workerProcessCrashed
0x4011  add
0x4012  stfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_workerProcessCrashed
0x4017  ldloc.3
0x4018  dup
0x4019  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_workerProcessTerminated
0x401e  ldloc.s  0x16
0x4020  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_workerProcessTerminated
0x4025  add
0x4026  stfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_workerProcessTerminated
0x402b  ldloc.3
0x402c  dup
0x402d  ldfld    int64 Microsoft.Crm.Sandbox.SandboxCounter::_memoryUsage
0x4032  ldloc.s  0x16
0x4034  ldfld    int64 Microsoft.Crm.Sandbox.SandboxCounter::_memoryUsage
0x4039  add
0x403a  stfld    int64 Microsoft.Crm.Sandbox.SandboxCounter::_memoryUsage
0x403f  ldloc.3
0x4040  dup
0x4041  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_processorUsagePercent
0x4046  ldloc.s  0x16
0x4048  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_processorUsagePercent
0x404d  add
0x404e  stfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_processorUsagePercent
0x4053  ldloc.3
0x4054  dup
0x4055  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_handleCount
0x405a  ldloc.s  0x16
0x405c  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_handleCount
0x4061  add
0x4062  stfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_handleCount
0x4067  ldloc.3
0x4068  ldfld    class Microsoft.Crm.Sandbox.SandboxIdTable Microsoft.Crm.Sandbox.SandboxCounter::_activePlugins
0x406d  dup
0x406e  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxIdTable::get_Count()
0x4073  ldloc.s  0x16
0x4075  ldfld    class Microsoft.Crm.Sandbox.SandboxIdTable Microsoft.Crm.Sandbox.SandboxCounter::_activePlugins
0x407a  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxIdTable::get_Count()
0x407f  add
0x4080  callvirt instance void Microsoft.Crm.Sandbox.SandboxIdTable::set_Count(int32 value)
0x4085  ldloc.3
0x4086  ldfld    class Microsoft.Crm.Sandbox.SandboxIdTable Microsoft.Crm.Sandbox.SandboxCounter::_activeCustomActivities
0x408b  dup
0x408c  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxIdTable::get_Count()
0x4091  ldloc.s  0x16
0x4093  ldfld    class Microsoft.Crm.Sandbox.SandboxIdTable Microsoft.Crm.Sandbox.SandboxCounter::_activeCustomActivities
0x4098  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxIdTable::get_Count()
0x409d  add
0x409e  callvirt instance void Microsoft.Crm.Sandbox.SandboxIdTable::set_Count(int32 value)
0x40a3  ldloc.3
0x40a4  ldfld    class Microsoft.Crm.Sandbox.SandboxIdTable Microsoft.Crm.Sandbox.SandboxCounter::_activeAssemblies
0x40a9  dup
0x40aa  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxIdTable::get_Count()
0x40af  ldloc.s  0x16
0x40b1  ldfld    class Microsoft.Crm.Sandbox.SandboxIdTable Microsoft.Crm.Sandbox.SandboxCounter::_activeAssemblies
0x40b6  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxIdTable::get_Count()
0x40bb  add
0x40bc  callvirt instance void Microsoft.Crm.Sandbox.SandboxIdTable::set_Count(int32 value)
0x40c1  ldloc.3
0x40c2  ldloc.s  0x16
0x40c4  callvirt instance void Microsoft.Crm.Sandbox.SandboxRequestCounter::AddCounts(class Microsoft.Crm.Sandbox.SandboxRequestCounter counter)
0x40c9  ldloc.3
0x40ca  ldloc.s  0x16
0x40cc  ldfld    class Microsoft.Crm.Sandbox.SandboxRequestCounter Microsoft.Crm.Sandbox.SandboxCounter::_sdkRequestCounter
0x40d1  callvirt instance void Microsoft.Crm.Sandbox.SandboxCounter::AddSdkCounts(class Microsoft.Crm.Sandbox.SandboxRequestCounter requestCounter)
0x40d6  ldloc.s  0x16
0x40d8  callvirt instance void Microsoft.Crm.Sandbox.SandboxRequestCounter::Reset()
0x40dd  ldloca.s 0x15
0x40df  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxCounter>::MoveNext()
0x40e4  brtrue   loc_3F51
0x40e9  leave.s  loc_40F9
0x40eb  ldloca.s 0x15
0x40ed  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxCounter>
0x40f3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40f8  endfinally
0x40f9  ldsfld   class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Sandbox.SandboxCounter::_watch
0x40fe  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x4103  ldsfld   class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Sandbox.SandboxCounter::_watch
0x4108  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x410d  stloc.s  0x17
0x410f  ldloca.s 0x17
0x4111  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x4116  ldc.r8   0.0
0x411f  cgt
0x4121  ldstr    aWatchElapsedTo// "_watch.Elapsed.TotalSeconds <= 0"
0x4126  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x412b  ldc.r8   0.0
0x4134  stloc.s  5
0x4136  ldc.r8   0.0
0x413f  stloc.s  6
0x4141  ldc.r8   0.0
0x414a  stloc.s  7
0x414c  ldc.r8   0.0
0x4155  stloc.s  8
0x4157  ldloc.0
0x4158  brfalse  loc_420C
0x415d  ldloc.3
0x415e  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheHits
0x4163  ldloc.3
0x4164  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheMisses
0x4169  add
0x416a  ldc.i4.0
0x416b  ble.s    loc_418F
0x416d  ldloc.3
0x416e  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheHits
0x4173  conv.r8
0x4174  ldloc.3
0x4175  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheHits
0x417a  ldloc.3
0x417b  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheMisses
0x4180  add
0x4181  conv.r8
0x4182  div
0x4183  ldc.r8   100.0
0x418c  mul
0x418d  stloc.s  5
0x418f  ldarg.0
0x4190  ldstr    aHostconfigurat// "hostConfiguration"
0x4195  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x419a  ldarg.0
0x419b  ldc.i4.2
0x419c  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype Microsoft.Crm.Sandbox.SandboxHostProperty key)
0x41a1  conv.r8
0x41a2  ldc.r8   1024.0
0x41ab  mul
0x41ac  ldc.r8   1024.0
0x41b5  mul
0x41b6  stloc.s  0x18
0x41b8  ldloc.3
0x41b9  ldfld    float64 Microsoft.Crm.Sandbox.SandboxCounter::_assemblyCacheDiskSpace
0x41be  ldloc.s  0x18
0x41c0  div
0x41c1  ldc.r8   100.0
0x41ca  mul
0x41cb  stloc.s  8
0x41cd  ldloc.3
0x41ce  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_workerProcessSerialCount
0x41d3  ldc.i4.0
0x41d4  ble.s    loc_420C
0x41d6  ldloc.3
0x41d7  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_workerProcessCrashed
0x41dc  conv.r8
0x41dd  ldloc.3
0x41de  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_workerProcessSerialCount
0x41e3  conv.r8
0x41e4  div
0x41e5  ldc.r8   100.0
0x41ee  mul
0x41ef  stloc.s  6
0x41f1  ldloc.3
0x41f2  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_workerProcessTerminated
0x41f7  conv.r8
0x41f8  ldloc.3
0x41f9  ldfld    int32 Microsoft.Crm.Sandbox.SandboxCounter::_workerProcessSerialCount
0x41fe  conv.r8
0x41ff  div
0x4200  ldc.r8   100.0
0x4209  mul
0x420a  stloc.s  7
0x420c  ldloc.3
0x420d  callvirt instance int64 Microsoft.Crm.Sandbox.SandboxRequestCounter::get_NumberOfRequests()
0x4212  conv.r8
0x4213  ldsfld   class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Sandbox.SandboxCounter::_watch
0x4218  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x421d  stloc.s  0x17
0x421f  ldloca.s 0x17
0x4221  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x4226  div
0x4227  stloc.s  9
0x4229  ldloc.3
0x422a  callvirt instance int64 Microsoft.Crm.Sandbox.SandboxRequestCounter::get_NumberOfRequests()
0x422f  ldloc.3
0x4230  callvirt instance int64 Microsoft.Crm.Sandbox.SandboxRequestCounter::get_NumberOfBadRequests()
0x4235  sub
0x4236  stloc.s  0xA
0x4238  ldc.i4.0
0x4239  conv.i8
0x423a  stloc.s  0xB
0x423c  ldloc.s  0xA
0x423e  ldc.i4.0
0x423f  conv.i8
0x4240  ble.s    loc_424D
0x4242  ldloc.3
0x4243  callvirt instance int64 Microsoft.Crm.Sandbox.SandboxRequestCounter::get_TotalRequestTimeInMSec()
0x4248  ldloc.s  0xA
0x424a  div
0x424b  stloc.s  0xB
0x424d  ldc.r8   0.0
0x4256  stloc.s  0xC
0x4258  ldloc.3
0x4259  callvirt instance int64 Microsoft.Crm.Sandbox.SandboxRequestCounter::get_NumberOfRequests()
0x425e  ldc.i4.0
0x425f  conv.i8
0x4260  ble.s    loc_427D
0x4262  ldloc.3
0x4263  callvirt instance int64 Microsoft.Crm.Sandbox.SandboxRequestCounter::get_NumberOfBadRequests()
0x4268  conv.r8
0x4269  ldloc.3
0x426a  callvirt instance int64 Microsoft.Crm.Sandbox.SandboxRequestCounter::get_NumberOfRequests()
0x426f  conv.r8
0x4270  div
0x4271  ldc.r8   100.0
0x427a  mul
0x427b  stloc.s  0xC
0x427d  ldloc.3
0x427e  ldfld    class Microsoft.Crm.Sandbox.SandboxRequestCounter Microsoft.Crm.Sandbox.SandboxCounter::_sdkRequestCounter
0x4283  callvirt instance int64 Microsoft.Crm.Sandbox.SandboxRequestCounter::get_NumberOfRequests()
  ... truncated ...
```
