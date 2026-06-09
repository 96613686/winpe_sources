# Microsoft.Crm.Sandbox.SandboxAssemblyCache::FileAdded

- ea: `0x2710`
- end: `0x27d7`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyCache::FileAdded`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x35d0`

## callees

- `0x2570`
- `0x2710`
- `0x2820`

## string_xrefs

- `0x2718`: `SandboxAssemblyCache.FileAdded: ENTER`
- `0x276e`: `SandboxAssemblyCache.FileAdded: Cache size exceeded`
- `0x27c6`: `SandboxAssemblyCache.FileAdded: EXIT`

## pseudocode

```c

```

## disassembly

```asm
0x2710  ldarg.0
0x2711  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x2716  ldc.i4.s 0x22
0x2718  ldstr    aSandboxassembl_4// "SandboxAssemblyCache.FileAdded: ENTER"
0x271d  ldc.i4.0
0x271e  newarr   [mscorlib]System.Object
0x2723  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2728  ldarg.0
0x2729  ldfld    object Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSizeLock
0x272e  stloc.1
0x272f  ldc.i4.0
0x2730  stloc.2
0x2731  ldloc.1
0x2732  ldloca.s 2
0x2734  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x2739  ldarg.0
0x273a  ldarg.0
0x273b  ldfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSize
0x2740  ldarg.1
0x2741  conv.r8
0x2742  add
0x2743  stfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSize
0x2748  ldarg.0
0x2749  ldfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSize
0x274e  ldarg.0
0x274f  ldfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_maxCacheSize
0x2754  cgt
0x2756  stloc.0
0x2757  leave.s  loc_2763
0x2759  ldloc.2
0x275a  brfalse.s loc_2762
0x275c  ldloc.1
0x275d  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x2762  endfinally
0x2763  ldloc.0
0x2764  brfalse.s loc_2786
0x2766  ldarg.0
0x2767  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x276c  ldc.i4.s 0x22
0x276e  ldstr    aSandboxassembl_5// "SandboxAssemblyCache.FileAdded: Cache s"...
0x2773  ldc.i4.0
0x2774  newarr   [mscorlib]System.Object
0x2779  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x277e  ldarg.0
0x277f  ldc.i4.0
0x2780  call     instance int32 Microsoft.Crm.Sandbox.SandboxAssemblyCache::RecoverDiskSpace(bool fullScan)
0x2785  pop
0x2786  ldarg.0
0x2787  ldflda   int32 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_numberOfFiles
0x278c  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x2791  pop
0x2792  ldarg.0
0x2793  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x2798  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0x279d  ldarg.0
0x279e  call     instance float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::get_CacheSize()
0x27a3  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::AssemblyCacheDiskSpace(float64)
0x27a8  ldarg.0
0x27a9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x27ae  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0x27b3  ldarg.0
0x27b4  ldfld    int32 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_numberOfFiles
0x27b9  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::AssemblyCacheCount(int32)
0x27be  ldarg.0
0x27bf  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x27c4  ldc.i4.s 0x22
0x27c6  ldstr    aSandboxassembl_6// "SandboxAssemblyCache.FileAdded: EXIT"
0x27cb  ldc.i4.0
0x27cc  newarr   [mscorlib]System.Object
0x27d1  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x27d6  ret
```
