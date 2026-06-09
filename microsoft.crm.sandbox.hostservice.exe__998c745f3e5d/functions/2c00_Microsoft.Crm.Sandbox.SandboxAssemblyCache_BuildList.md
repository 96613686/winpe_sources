# Microsoft.Crm.Sandbox.SandboxAssemblyCache::BuildList

- ea: `0x2c00`
- end: `0x2d73`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyCache::BuildList`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2820`

## callees

- `0x2c00`
- `0xba00`

## string_xrefs

- `0x2c08`: `SandboxAssemblyCache.BuildList: ENTER`
- `0x2c92`: `SandboxAssemblyCache.BuildList: {0}: {1}`
- `0x2d3b`: `SandboxAssemblyCache.BuildList: _cacheSize: {0}`
- `0x2d61`: `SandboxAssemblyCache.BuildList: EXIT`

## pseudocode

```c

```

## disassembly

```asm
0x2c00  ldarg.0
0x2c01  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x2c06  ldc.i4.s 0x22
0x2c08  ldstr    aSandboxassembl_25// "SandboxAssemblyCache.BuildList: ENTER"
0x2c0d  ldc.i4.0
0x2c0e  newarr   [mscorlib]System.Object
0x2c13  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2c18  newobj   instance void class [System]System.Collections.Generic.SortedList`2<valuetype [mscorlib]System.DateTime, class AssemblyCacheInfo>::.ctor()
0x2c1d  stloc.0
0x2c1e  ldarg.0
0x2c1f  ldfld    object Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSizeLock
0x2c24  stloc.2
0x2c25  ldc.i4.0
0x2c26  stloc.3
0x2c27  ldloc.2
0x2c28  ldloca.s 3
0x2c2a  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x2c2f  ldarg.0
0x2c30  ldc.r8   0.0
0x2c39  stfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSize
0x2c3e  leave.s  loc_2C4A
0x2c40  ldloc.3
0x2c41  brfalse.s loc_2C49
0x2c43  ldloc.2
0x2c44  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x2c49  endfinally
0x2c4a  ldc.r8   0.0
0x2c53  stloc.1
0x2c54  ldarg.0
0x2c55  ldfld    string Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cachePath
0x2c5a  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x2c5f  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles()
0x2c64  stloc.s  4
0x2c66  ldc.i4.0
0x2c67  stloc.s  5
0x2c69  br       loc_2CFD
0x2c6e  ldloc.s  4
0x2c70  ldloc.s  5
0x2c72  ldelem.ref
0x2c73  stloc.s  6
0x2c75  ldloc.s  6
0x2c77  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x2c7c  ldloc.s  6
0x2c7e  callvirt instance int64 [mscorlib]System.IO.FileInfo::get_Length()
0x2c83  newobj   instance void AssemblyCacheInfo::.ctor(string assemblyFileName, int64 assemblySize)
0x2c88  stloc.s  7
0x2c8a  ldarg.0
0x2c8b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x2c90  ldc.i4.s 0x22
0x2c92  ldstr    aSandboxassembl_26// "SandboxAssemblyCache.BuildList: {0}: {1"...
0x2c97  ldc.i4.2
0x2c98  newarr   [mscorlib]System.Object
0x2c9d  dup
0x2c9e  ldc.i4.0
0x2c9f  ldloc.s  6
0x2ca1  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.IO.FileSystemInfo::get_LastAccessTimeUtc()
0x2ca6  box      [mscorlib]System.DateTime
0x2cab  stelem.ref
0x2cac  dup
0x2cad  ldc.i4.1
0x2cae  ldloc.s  7
0x2cb0  ldfld    string AssemblyCacheInfo::_assemblyFileName
0x2cb5  stelem.ref
0x2cb6  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2cbb  ldloc.s  6
0x2cbd  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.IO.FileSystemInfo::get_LastAccessTimeUtc()
0x2cc2  stloc.s  8
0x2cc4  br.s     loc_2CD8
0x2cc6  ldloca.s 8
0x2cc8  ldc.r8   1.0
0x2cd1  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMilliseconds(float64)
0x2cd6  stloc.s  8
0x2cd8  ldloc.0
0x2cd9  ldloc.s  8
0x2cdb  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<valuetype [mscorlib]System.DateTime, class AssemblyCacheInfo>::ContainsKey(var<u1>)
0x2ce0  brtrue.s loc_2CC6
0x2ce2  ldloc.0
0x2ce3  ldloc.s  8
0x2ce5  ldloc.s  7
0x2ce7  callvirt instance void class [System]System.Collections.Generic.SortedList`2<valuetype [mscorlib]System.DateTime, class AssemblyCacheInfo>::Add(var<u1>, !!T0)
0x2cec  ldloc.1
0x2ced  ldloc.s  6
0x2cef  callvirt instance int64 [mscorlib]System.IO.FileInfo::get_Length()
0x2cf4  conv.r8
0x2cf5  add
0x2cf6  stloc.1
0x2cf7  ldloc.s  5
0x2cf9  ldc.i4.1
0x2cfa  add
0x2cfb  stloc.s  5
0x2cfd  ldloc.s  5
0x2cff  ldloc.s  4
0x2d01  ldlen
0x2d02  conv.i4
0x2d03  blt      loc_2C6E
0x2d08  ldarg.0
0x2d09  ldfld    object Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSizeLock
0x2d0e  stloc.2
0x2d0f  ldc.i4.0
0x2d10  stloc.3
0x2d11  ldloc.2
0x2d12  ldloca.s 3
0x2d14  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x2d19  ldarg.0
0x2d1a  ldarg.0
0x2d1b  ldfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSize
0x2d20  ldloc.1
0x2d21  add
0x2d22  stfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSize
0x2d27  leave.s  loc_2D33
0x2d29  ldloc.3
0x2d2a  brfalse.s loc_2D32
0x2d2c  ldloc.2
0x2d2d  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x2d32  endfinally
0x2d33  ldarg.0
0x2d34  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x2d39  ldc.i4.s 0x22
0x2d3b  ldstr    aSandboxassembl_27// "SandboxAssemblyCache.BuildList: _cacheS"...
0x2d40  ldc.i4.1
0x2d41  newarr   [mscorlib]System.Object
0x2d46  dup
0x2d47  ldc.i4.0
0x2d48  ldarg.0
0x2d49  ldfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSize
0x2d4e  box      [mscorlib]System.Double
0x2d53  stelem.ref
0x2d54  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2d59  ldarg.0
0x2d5a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x2d5f  ldc.i4.s 0x22
0x2d61  ldstr    aSandboxassembl_28// "SandboxAssemblyCache.BuildList: EXIT"
0x2d66  ldc.i4.0
0x2d67  newarr   [mscorlib]System.Object
0x2d6c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2d71  ldloc.0
0x2d72  ret
```
