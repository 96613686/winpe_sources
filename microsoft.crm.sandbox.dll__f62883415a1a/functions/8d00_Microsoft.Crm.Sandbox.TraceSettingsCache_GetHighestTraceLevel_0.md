# Microsoft.Crm.Sandbox.TraceSettingsCache::GetHighestTraceLevel_0

- ea: `0x8d00`
- end: `0x8d56`
- name: `Microsoft.Crm.Sandbox.TraceSettingsCache::GetHighestTraceLevel_0`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8c50`

## callees

- `0x8d00`
- `0x8d60`
- `0xb150`

## pseudocode

```c

```

## disassembly

```asm
0x8d00  newobj   instance void <>c__DisplayClass14_0::.ctor()
0x8d05  stloc.0
0x8d06  ldarg.2
0x8d07  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8d0c  brfalse.s loc_8D10
0x8d0e  ldc.i4.0
0x8d0f  ret
0x8d10  ldarg.0
0x8d11  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel> Microsoft.Crm.Sandbox.TraceSettingsCache::_traceLevels
0x8d16  ldarg.1
0x8d17  ldloca.s 1
0x8d19  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel>::TryGetValue(var<u1>, !!T0)
0x8d1e  brfalse.s loc_8D22
0x8d20  ldloc.1
0x8d21  ret
0x8d22  ldloc.0
0x8d23  ldarg.0
0x8d24  ldarg.1
0x8d25  ldarg.2
0x8d26  call     instance valuetype [System]System.Diagnostics.TraceLevel Microsoft.Crm.Sandbox.TraceSettingsCache::GetHighestTraceLevelInternal(string specificCategory, string traceCategories)
0x8d2b  stfld    valuetype [System]System.Diagnostics.TraceLevel <>c__DisplayClass14_0::highestTraceLevel
0x8d30  ldarg.0
0x8d31  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel> Microsoft.Crm.Sandbox.TraceSettingsCache::_traceLevels
0x8d36  ldarg.1
0x8d37  ldloc.0
0x8d38  ldfld    valuetype [System]System.Diagnostics.TraceLevel <>c__DisplayClass14_0::highestTraceLevel
0x8d3d  ldloc.0
0x8d3e  ldftn    instance valuetype [System]System.Diagnostics.TraceLevel <>c__DisplayClass14_0::<GetHighestTraceLevel>b__0(string s, valuetype [System]System.Diagnostics.TraceLevel t1)
0x8d44  newobj   instance void class [mscorlib]System.Func`3<string, valuetype [System]System.Diagnostics.TraceLevel, valuetype [System]System.Diagnostics.TraceLevel>::.ctor(object, native int)
0x8d49  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel>::AddOrUpdate(void, var<u1>, !!T0)
0x8d4e  pop
0x8d4f  ldloc.0
0x8d50  ldfld    valuetype [System]System.Diagnostics.TraceLevel <>c__DisplayClass14_0::highestTraceLevel
0x8d55  ret
```
