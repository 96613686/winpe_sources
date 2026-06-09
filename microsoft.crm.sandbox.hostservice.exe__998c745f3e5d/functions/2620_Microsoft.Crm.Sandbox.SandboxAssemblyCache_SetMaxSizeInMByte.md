# Microsoft.Crm.Sandbox.SandboxAssemblyCache::SetMaxSizeInMByte

- ea: `0x2620`
- end: `0x2670`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyCache::SetMaxSizeInMByte`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x34b0`
- `0x36a0`

## callees

- `0x2620`

## string_xrefs

- `0x262c`: `SandboxAssemblyCache.SetMaxSizeInMByte: maxSize is invalid`

## pseudocode

```c

```

## disassembly

```asm
0x2620  ldarg.1
0x2621  ldc.r8   0.0
0x262a  cgt
0x262c  ldstr    aSandboxassembl_1// "SandboxAssemblyCache.SetMaxSizeInMByte:"...
0x2631  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2636  ldarg.0
0x2637  ldfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_maxCacheSize
0x263c  pop
0x263d  ldarg.0
0x263e  ldarg.1
0x263f  ldc.r8   1048576.0
0x2648  mul
0x2649  stfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_maxCacheSize
0x264e  ldarg.0
0x264f  ldfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_maxCacheSize
0x2654  ldarg.0
0x2655  ldfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSize
0x265a  bge.un.s loc_266F
0x265c  ldnull
0x265d  ldftn    void Microsoft.Crm.Sandbox.SandboxAssemblyCache::StartRecoverDiskSpace(object info)
0x2663  newobj   instance void [mscorlib]System.Threading.WaitCallback::.ctor(object, native int)
0x2668  ldarg.0
0x2669  call     bool [mscorlib]System.Threading.ThreadPool::QueueUserWorkItem(class [mscorlib]System.Threading.WaitCallback, object)
0x266e  pop
0x266f  ret
```
