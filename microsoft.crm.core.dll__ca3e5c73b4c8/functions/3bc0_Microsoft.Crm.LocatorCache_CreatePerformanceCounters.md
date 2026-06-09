# Microsoft.Crm.LocatorCache::CreatePerformanceCounters

- ea: `0x3bc0`
- end: `0x3c5b`
- name: `Microsoft.Crm.LocatorCache::CreatePerformanceCounters`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x31e0`

## callees

- `0x3bc0`
- `0x1eaa0`
- `0x1f510`
- `0x2f1a0`
- `0x2f3c0`
- `0x2f520`
- `0x2fc60`

## string_xrefs

- `0x3bc9`: `CRM LocatorService`
- `0x3bdb`: `LocatorService`
- `0x3be6`: `LocatorServiceFailedCacheFlushRequests`
- `0x3bf6`: `LocatorServiceTotalCacheFlushRequests`
- `0x3c44`: `UnauthorizedAccessException occured while creating Performance Counters : {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3bc0  call     bool Microsoft.Crm.CrmPerformanceCounterFactory::get_Disabled()
0x3bc5  brfalse.s loc_3BC8
0x3bc7  ret
0x3bc8  nop
0x3bc9  ldstr    aCrmLocatorserv// "CRM LocatorService"
0x3bce  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x3bd3  brtrue.s loc_3BDA
0x3bd5  leave    loc_3C5A
0x3bda  ldc.i4.1
0x3bdb  ldstr    aLocatorservice// "LocatorService"
0x3be0  call     void Microsoft.Crm.CrmPerformanceCounterFactory::LoadCounters(valuetype Microsoft.Crm.PerformanceCounterLoadSetting settings, string component)
0x3be5  ldarg.0
0x3be6  ldstr    aLocatorservice_0// "LocatorServiceFailedCacheFlushRequests"
0x3beb  call     class Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.CrmPerformanceCounterFactory::GetCounter(string counterName)
0x3bf0  stfld    class Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.LocatorCache::_totalCacheFlushFailuresCounter
0x3bf5  ldarg.0
0x3bf6  ldstr    aLocatorservice_1// "LocatorServiceTotalCacheFlushRequests"
0x3bfb  call     class Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.CrmPerformanceCounterFactory::GetCounter(string counterName)
0x3c00  stfld    class Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.LocatorCache::_totalCacheFlushAttemptsCounter
0x3c05  ldarg.0
0x3c06  ldfld    class Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.LocatorCache::_totalCacheFlushFailuresCounter
0x3c0b  brfalse.s loc_3C39
0x3c0d  ldarg.0
0x3c0e  ldfld    class Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.LocatorCache::_totalCacheFlushAttemptsCounter
0x3c13  brfalse.s loc_3C39
0x3c15  ldarg.0
0x3c16  ldfld    class Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.LocatorCache::_totalCacheFlushFailuresCounter
0x3c1b  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.CrmPerformanceCounter::get_PC()
0x3c20  ldc.i4.0
0x3c21  conv.i8
0x3c22  callvirt instance void [System]System.Diagnostics.PerformanceCounter::set_RawValue(int64)
0x3c27  ldarg.0
0x3c28  ldfld    class Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.LocatorCache::_totalCacheFlushAttemptsCounter
0x3c2d  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.CrmPerformanceCounter::get_PC()
0x3c32  ldc.i4.0
0x3c33  conv.i8
0x3c34  callvirt instance void [System]System.Diagnostics.PerformanceCounter::set_RawValue(int64)
0x3c39  leave.s  loc_3C5A
0x3c3b  stloc.0
0x3c3c  ldloc.0
0x3c3d  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3c42  ldc.i4.s 0x14
0x3c44  ldstr    aUnauthorizedac// "UnauthorizedAccessException occured whi"...
0x3c49  ldc.i4.1
0x3c4a  newarr   [mscorlib]System.Object
0x3c4f  dup
0x3c50  ldc.i4.0
0x3c51  ldloc.0
0x3c52  stelem.ref
0x3c53  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x3c58  leave.s  loc_3C5A
0x3c5a  ret
```
