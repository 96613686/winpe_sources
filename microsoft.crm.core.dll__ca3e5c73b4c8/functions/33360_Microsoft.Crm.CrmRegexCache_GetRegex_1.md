# Microsoft.Crm.CrmRegexCache::GetRegex_1

- ea: `0x33360`
- end: `0x33430`
- name: `Microsoft.Crm.CrmRegexCache::GetRegex_1`
- size: `208`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x33340`
- `0x33350`
- `0x33450`
- `0x334c0`
- `0x334f0`
- `0x33540`

## callees

- `0x1ee00`
- `0x1f4b0`
- `0x33360`

## string_xrefs

- `0x333ce`: `[CrmRegexCache-Statistics] cache '{0}' size '{1}', capacity '{2}'.`
- `0x3340a`: `[CrmRegexCache-Sample] random sample: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x33360  ldloca.s 0
0x33362  initobj  RegexCreationSettings
0x33368  ldloca.s 0
0x3336a  ldarg.0
0x3336b  stfld    string RegexCreationSettings::Pattern
0x33370  ldloca.s 0
0x33372  ldarg.1
0x33373  stfld    valuetype [System]System.Text.RegularExpressions.RegexOptions RegexCreationSettings::Options
0x33378  ldloca.s 0
0x3337a  ldarg.2
0x3337b  stfld    valuetype [mscorlib]System.TimeSpan RegexCreationSettings::Timeout
0x33380  ldloca.s 0
0x33382  ldarg.0
0x33383  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x33388  conv.i8
0x33389  ldarg.1
0x3338a  conv.i8
0x3338b  xor
0x3338c  ldarga.s 2
0x3338e  call     instance int64 [mscorlib]System.TimeSpan::get_Ticks()
0x33393  xor
0x33394  conv.i4
0x33395  stfld    int32 RegexCreationSettings::HashCode
0x3339a  ldsfld   class LimitedCapacityCache`2<valuetype RegexCreationSettings, class [System]System.Text.RegularExpressions.Regex>[] Microsoft.Crm.CrmRegexCache::CacheInstances
0x3339f  stloc.1
0x333a0  ldloc.1
0x333a1  ldloc.0
0x333a2  ldfld    int32 RegexCreationSettings::HashCode
0x333a7  ldloc.1
0x333a8  ldlen
0x333a9  conv.i4
0x333aa  rem.un
0x333ab  ldelem.ref
0x333ac  stloc.2
0x333ad  ldsflda  int64 Microsoft.Crm.CrmRegexCache::CrmRegexCacheStatisticsTraceCounter
0x333b2  call     int64 [mscorlib]System.Threading.Interlocked::Increment(int64&)
0x333b7  ldc.i4   0xFFF
0x333bc  conv.i8
0x333bd  and
0x333be  brtrue.s loc_33422
0x333c0  call     bool Microsoft.Crm.CrmTrace::get_TraceDisabled()
0x333c5  brtrue.s loc_33422
0x333c7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x333cc  ldc.i4.s 0x14
0x333ce  ldstr    aCrmregexcacheS// "[CrmRegexCache-Statistics] cache '{0}' "...
0x333d3  ldc.i4.3
0x333d4  newarr   [mscorlib]System.Object
0x333d9  dup
0x333da  ldc.i4.0
0x333db  ldloc.2
0x333dc  callvirt instance string class LimitedCapacityCache`2<valuetype RegexCreationSettings, class [System]System.Text.RegularExpressions.Regex>::get_Name()
0x333e1  stelem.ref
0x333e2  dup
0x333e3  ldc.i4.1
0x333e4  ldloc.2
0x333e5  callvirt instance int32 class LimitedCapacityCache`2<valuetype RegexCreationSettings, class [System]System.Text.RegularExpressions.Regex>::get_Count()
0x333ea  box      [mscorlib]System.Int32
0x333ef  stelem.ref
0x333f0  dup
0x333f1  ldc.i4.2
0x333f2  ldloc.2
0x333f3  callvirt instance int32 class LimitedCapacityCache`2<valuetype RegexCreationSettings, class [System]System.Text.RegularExpressions.Regex>::get_Capacity()
0x333f8  box      [mscorlib]System.Int32
0x333fd  stelem.ref
0x333fe  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x33403  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x33408  ldc.i4.s 0x14
0x3340a  ldstr    aCrmregexcacheS_0// "[CrmRegexCache-Sample] random sample: {"...
0x3340f  ldc.i4.1
0x33410  newarr   [mscorlib]System.Object
0x33415  dup
0x33416  ldc.i4.0
0x33417  call     string [mscorlib]System.Environment::get_StackTrace()
0x3341c  stelem.ref
0x3341d  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x33422  ldloc.2
0x33423  ldloc.0
0x33424  ldarg.1
0x33425  ldc.i4.8
0x33426  and
0x33427  ldc.i4.0
0x33428  cgt
0x3342a  callvirt instance var<u1> class LimitedCapacityCache`2<valuetype RegexCreationSettings, class [System]System.Text.RegularExpressions.Regex>::GetOrCreateValue(void, var<u1>)
0x3342f  ret
```
