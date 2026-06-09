# Microsoft.Crm.Sandbox.SandboxAssemblyCache::.ctor

- ea: `0x2580`
- end: `0x2613`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyCache::.ctor`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x3030`
- `0x34b0`

## string_xrefs

- `0x25d8`: `SandboxAssemblyCache: _cachePath: {0}`
- `0x25f4`: `SandboxAssemblyCache: _maxCacheSize: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2580  ldarg.0
0x2581  newobj   instance void [mscorlib]System.Object::.ctor()
0x2586  stfld    object Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSizeLock
0x258b  ldarg.0
0x258c  newobj   instance void [mscorlib]System.Object::.ctor()
0x2591  stfld    object Microsoft.Crm.Sandbox.SandboxAssemblyCache::_recoverDiskSpaceLock
0x2596  ldarg.0
0x2597  call     instance void [mscorlib]System.Object::.ctor()
0x259c  ldarg.0
0x259d  ldarg.1
0x259e  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x25a3  ldarg.0
0x25a4  ldnull
0x25a5  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::AssemblyCachePath(string)
0x25aa  ldarg.0
0x25ab  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x25b0  ldstr    aB// "B"
0x25b5  call     instance string [mscorlib]System.Guid::ToString(string)
0x25ba  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x25bf  stfld    string Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cachePath
0x25c4  ldarg.0
0x25c5  ldarg.2
0x25c6  ldc.r8   1048576.0
0x25cf  mul
0x25d0  stfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_maxCacheSize
0x25d5  ldarg.1
0x25d6  ldc.i4.s 0x22
0x25d8  ldstr    aSandboxassembl// "SandboxAssemblyCache: _cachePath: {0}"
0x25dd  ldc.i4.1
0x25de  newarr   [mscorlib]System.Object
0x25e3  dup
0x25e4  ldc.i4.0
0x25e5  ldarg.0
0x25e6  ldfld    string Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cachePath
0x25eb  stelem.ref
0x25ec  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25f1  ldarg.1
0x25f2  ldc.i4.s 0x22
0x25f4  ldstr    aSandboxassembl_0// "SandboxAssemblyCache: _maxCacheSize: {0"...
0x25f9  ldc.i4.1
0x25fa  newarr   [mscorlib]System.Object
0x25ff  dup
0x2600  ldc.i4.0
0x2601  ldarg.0
0x2602  ldfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_maxCacheSize
0x2607  box      [mscorlib]System.Double
0x260c  stelem.ref
0x260d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2612  ret
```
