# Microsoft.Crm.Sandbox.SandboxAssemblyCache::RecoverDiskSpace

- ea: `0x2820`
- end: `0x2bfb`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyCache::RecoverDiskSpace`
- size: `987`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x2710`
- `0x27e0`
- `0x3820`

## callees

- `0x2570`
- `0x2820`
- `0x2c00`
- `0x48e0`

## string_xrefs

- `0x2828`: `SandboxAssemblyCache.RecoverDiskSpace: ENTER`
- `0x2853`: `SandboxAssemblyCache.RecoverDiskSpace: Before: _cacheSize: {0}`
- `0x2890`: `SandboxAssemblyCache.RecoverDiskSpace: Cache size OK`
- `0x28c0`: `SandboxAssemblyCache.RecoverDiskSpace: Before: numberOfFiles: {0}`
- `0x28f3`: `SandboxAssemblyCache.RecoverDiskSpace: cacheSizeLimit: {0}`
- `0x2928`: `SandboxAssemblyCache.RecoverDiskSpace: AssemblyCacheExpireTimeInMin invalid, using default: {0}`
- `0x2951`: `SandboxAssemblyCache.RecoverDiskSpace: assemblyCacheExpireTimeInMin: {0}`
- `0x2988`: `SandboxAssemblyCache.RecoverDiskSpace: cutoffTime: {0}`
- `0x29c4`: `assemblyCacheInfo`
- `0x29ea`: `SandboxAssemblyCache.RecoverDiskSpace: {0}: {1}`
- `0x2a3c`: `SandboxAssemblyCache.RecoverDiskSpace: Space OK and time OK`
- `0x2a61`: `SandboxAssemblyCache.RecoverDiskSpace: Space OK`
- `0x2a7e`: `SandboxAssemblyCache.RecoverDiskSpace: Delete file: {0}`
- `0x2abe`: `SandboxAssemblyCache.RecoverDiskSpace: File accessed: {0}`
- `0x2aee`: `SandboxAssemblyCache.RecoverDiskSpace: File.Delete: {0}`
- `0x2b71`: `SandboxAssemblyCache.RecoverDiskSpace: After: _cacheSize: {0}`
- `0x2b97`: `SandboxAssemblyCache.RecoverDiskSpace: After: numberOfFiles: {0}`
- `0x2bb8`: `SandboxAssemblyCache.RecoverDiskSpace: EXIT`

## pseudocode

```c

```

## disassembly

```asm
0x2820  ldarg.0
0x2821  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x2826  ldc.i4.s 0x22
0x2828  ldstr    aSandboxassembl_8// "SandboxAssemblyCache.RecoverDiskSpace: "...
0x282d  ldc.i4.0
0x282e  newarr   [mscorlib]System.Object
0x2833  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2838  ldc.i4.0
0x2839  stloc.0
0x283a  ldarg.0
0x283b  ldfld    object Microsoft.Crm.Sandbox.SandboxAssemblyCache::_recoverDiskSpaceLock
0x2840  stloc.1
0x2841  ldc.i4.0
0x2842  stloc.2
0x2843  ldloc.1
0x2844  ldloca.s 2
0x2846  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x284b  ldarg.0
0x284c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x2851  ldc.i4.s 0x22
0x2853  ldstr    aSandboxassembl_9// "SandboxAssemblyCache.RecoverDiskSpace: "...
0x2858  ldc.i4.1
0x2859  newarr   [mscorlib]System.Object
0x285e  dup
0x285f  ldc.i4.0
0x2860  ldarg.0
0x2861  ldfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSize
0x2866  box      [mscorlib]System.Double
0x286b  stelem.ref
0x286c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2871  ldarg.0
0x2872  ldfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSize
0x2877  ldarg.0
0x2878  ldfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_maxCacheSize
0x287d  clt
0x287f  stloc.3
0x2880  ldarg.1
0x2881  ldc.i4.0
0x2882  ceq
0x2884  ldloc.3
0x2885  and
0x2886  brfalse.s loc_28A8
0x2888  ldarg.0
0x2889  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x288e  ldc.i4.s 0x22
0x2890  ldstr    aSandboxassembl_10// "SandboxAssemblyCache.RecoverDiskSpace: "...
0x2895  ldc.i4.0
0x2896  newarr   [mscorlib]System.Object
0x289b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x28a0  ldloc.0
0x28a1  stloc.s  8
0x28a3  leave    loc_2BF8
0x28a8  ldarg.0
0x28a9  call     instance class [System]System.Collections.Generic.SortedList`2<valuetype [mscorlib]System.DateTime, class AssemblyCacheInfo> Microsoft.Crm.Sandbox.SandboxAssemblyCache::BuildList()
0x28ae  stloc.s  4
0x28b0  ldloc.s  4
0x28b2  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<valuetype [mscorlib]System.DateTime, class AssemblyCacheInfo>::get_Count()
0x28b7  stloc.0
0x28b8  ldarg.0
0x28b9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x28be  ldc.i4.s 0x22
0x28c0  ldstr    aSandboxassembl_11// "SandboxAssemblyCache.RecoverDiskSpace: "...
0x28c5  ldc.i4.1
0x28c6  newarr   [mscorlib]System.Object
0x28cb  dup
0x28cc  ldc.i4.0
0x28cd  ldloc.0
0x28ce  box      [mscorlib]System.Int32
0x28d3  stelem.ref
0x28d4  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x28d9  ldarg.0
0x28da  ldfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_maxCacheSize
0x28df  ldc.r8   0.8
0x28e8  mul
0x28e9  stloc.s  5
0x28eb  ldarg.0
0x28ec  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x28f1  ldc.i4.s 0x22
0x28f3  ldstr    aSandboxassembl_12// "SandboxAssemblyCache.RecoverDiskSpace: "...
0x28f8  ldc.i4.1
0x28f9  newarr   [mscorlib]System.Object
0x28fe  dup
0x28ff  ldc.i4.0
0x2900  ldloc.s  5
0x2902  box      [mscorlib]System.Double
0x2907  stelem.ref
0x2908  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x290d  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0x2912  ldc.i4.8
0x2913  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0x2918  stloc.s  6
0x291a  ldloc.s  6
0x291c  ldc.i4.0
0x291d  bgt.s    loc_2949
0x291f  ldnull
0x2920  ldarg.0
0x2921  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x2926  ldc.i4.s 0x22
0x2928  ldstr    aSandboxassembl_13// "SandboxAssemblyCache.RecoverDiskSpace: "...
0x292d  ldc.i4.1
0x292e  newarr   [mscorlib]System.Object
0x2933  dup
0x2934  ldc.i4.0
0x2935  ldloc.s  6
0x2937  box      [mscorlib]System.Int32
0x293c  stelem.ref
0x293d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2942  ldc.i4   0x1C20
0x2947  stloc.s  6
0x2949  ldarg.0
0x294a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x294f  ldc.i4.s 0x22
0x2951  ldstr    aSandboxassembl_14// "SandboxAssemblyCache.RecoverDiskSpace: "...
0x2956  ldc.i4.1
0x2957  newarr   [mscorlib]System.Object
0x295c  dup
0x295d  ldc.i4.0
0x295e  ldloc.s  6
0x2960  box      [mscorlib]System.Int32
0x2965  stelem.ref
0x2966  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x296b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2970  stloc.s  9
0x2972  ldloca.s 9
0x2974  ldc.i4.m1
0x2975  ldloc.s  6
0x2977  mul
0x2978  conv.r8
0x2979  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x297e  stloc.s  7
0x2980  ldarg.0
0x2981  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x2986  ldc.i4.s 0x22
0x2988  ldstr    aSandboxassembl_15// "SandboxAssemblyCache.RecoverDiskSpace: "...
0x298d  ldc.i4.1
0x298e  newarr   [mscorlib]System.Object
0x2993  dup
0x2994  ldc.i4.0
0x2995  ldloc.s  7
0x2997  box      [mscorlib]System.DateTime
0x299c  stelem.ref
0x299d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x29a2  ldloc.s  4
0x29a4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [System]System.Collections.Generic.SortedList`2<valuetype [mscorlib]System.DateTime, class AssemblyCacheInfo>::GetEnumerator()
0x29a9  stloc.s  0xA
0x29ab  br       loc_2B45
0x29b0  ldloc.s  0xA
0x29b2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.DateTime, class AssemblyCacheInfo>>::get_Current()
0x29b7  stloc.s  0xB
0x29b9  ldloca.s 0xB
0x29bb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.DateTime, class AssemblyCacheInfo>::get_Value()
0x29c0  stloc.s  0xC
0x29c2  ldloc.s  0xC
0x29c4  ldstr    aAssemblycachei// "assemblyCacheInfo"
0x29c9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x29ce  ldarg.0
0x29cf  ldfld    string Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cachePath
0x29d4  ldloc.s  0xC
0x29d6  ldfld    string AssemblyCacheInfo::_assemblyFileName
0x29db  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x29e0  stloc.s  0xD
0x29e2  ldarg.0
0x29e3  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x29e8  ldc.i4.s 0x22
0x29ea  ldstr    aSandboxassembl_16// "SandboxAssemblyCache.RecoverDiskSpace: "...
0x29ef  ldc.i4.2
0x29f0  newarr   [mscorlib]System.Object
0x29f5  dup
0x29f6  ldc.i4.0
0x29f7  ldloca.s 0xB
0x29f9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.DateTime, class AssemblyCacheInfo>::get_Key()
0x29fe  box      [mscorlib]System.DateTime
0x2a03  stelem.ref
0x2a04  dup
0x2a05  ldc.i4.1
0x2a06  ldloc.s  0xC
0x2a08  ldfld    string AssemblyCacheInfo::_assemblyFileName
0x2a0d  stelem.ref
0x2a0e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2a13  ldloca.s 0xB
0x2a15  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.DateTime, class AssemblyCacheInfo>::get_Key()
0x2a1a  ldloc.s  7
0x2a1c  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x2a21  stloc.s  0xE
0x2a23  ldarg.0
0x2a24  ldfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSize
0x2a29  ldloc.s  5
0x2a2b  clt
0x2a2d  stloc.3
0x2a2e  ldloc.3
0x2a2f  ldloc.s  0xE
0x2a31  and
0x2a32  brfalse.s loc_2A51
0x2a34  ldarg.0
0x2a35  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x2a3a  ldc.i4.s 0x22
0x2a3c  ldstr    aSandboxassembl_17// "SandboxAssemblyCache.RecoverDiskSpace: "...
0x2a41  ldc.i4.0
0x2a42  newarr   [mscorlib]System.Object
0x2a47  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2a4c  leave    loc_2B69
0x2a51  ldarg.1
0x2a52  ldc.i4.0
0x2a53  ceq
0x2a55  ldloc.3
0x2a56  and
0x2a57  brfalse.s loc_2A76
0x2a59  ldarg.0
0x2a5a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x2a5f  ldc.i4.s 0x22
0x2a61  ldstr    aSandboxassembl_18// "SandboxAssemblyCache.RecoverDiskSpace: "...
0x2a66  ldc.i4.0
0x2a67  newarr   [mscorlib]System.Object
0x2a6c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2a71  leave    loc_2B69
0x2a76  ldarg.0
0x2a77  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x2a7c  ldc.i4.s 0x22
0x2a7e  ldstr    aSandboxassembl_19// "SandboxAssemblyCache.RecoverDiskSpace: "...
0x2a83  ldc.i4.1
0x2a84  newarr   [mscorlib]System.Object
0x2a89  dup
0x2a8a  ldc.i4.0
0x2a8b  ldloc.s  0xC
0x2a8d  ldfld    string AssemblyCacheInfo::_assemblyFileName
0x2a92  stelem.ref
0x2a93  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2a98  ldloc.s  0xD
0x2a9a  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x2a9f  stloc.s  0xF
0x2aa1  ldloca.s 0xB
0x2aa3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.DateTime, class AssemblyCacheInfo>::get_Key()
0x2aa8  ldloc.s  0xF
0x2aaa  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.IO.FileSystemInfo::get_LastAccessTimeUtc()
0x2aaf  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x2ab4  brfalse.s loc_2ADA
0x2ab6  ldarg.0
0x2ab7  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x2abc  ldc.i4.s 0x22
0x2abe  ldstr    aSandboxassembl_20// "SandboxAssemblyCache.RecoverDiskSpace: "...
0x2ac3  ldc.i4.1
0x2ac4  newarr   [mscorlib]System.Object
0x2ac9  dup
0x2aca  ldc.i4.0
0x2acb  ldloc.s  0xC
0x2acd  ldfld    string AssemblyCacheInfo::_assemblyFileName
0x2ad2  stelem.ref
0x2ad3  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2ad8  br.s     loc_2B45
0x2ada  nop
0x2adb  ldloc.s  0xD
0x2add  call     void [mscorlib]System.IO.File::Delete(string)
0x2ae2  leave.s  loc_2B0A
0x2ae4  stloc.s  0x10
0x2ae6  ldarg.0
0x2ae7  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x2aec  ldc.i4.s 0x22
0x2aee  ldstr    aSandboxassembl_21// "SandboxAssemblyCache.RecoverDiskSpace: "...
0x2af3  ldc.i4.1
0x2af4  newarr   [mscorlib]System.Object
0x2af9  dup
0x2afa  ldc.i4.0
0x2afb  ldloc.s  0x10
0x2afd  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2b02  stelem.ref
0x2b03  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2b08  leave.s  loc_2B45
0x2b0a  ldloc.0
0x2b0b  ldc.i4.1
0x2b0c  sub
0x2b0d  stloc.0
0x2b0e  ldarg.0
0x2b0f  ldfld    object Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSizeLock
0x2b14  stloc.s  0x11
0x2b16  ldc.i4.0
0x2b17  stloc.s  0x12
0x2b19  ldloc.s  0x11
0x2b1b  ldloca.s 0x12
0x2b1d  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x2b22  ldarg.0
0x2b23  ldarg.0
0x2b24  ldfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSize
0x2b29  ldloc.s  0xC
0x2b2b  ldfld    int64 AssemblyCacheInfo::_assemblySize
0x2b30  conv.r8
0x2b31  sub
0x2b32  stfld    float64 Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cacheSize
0x2b37  leave.s  loc_2B45
0x2b39  ldloc.s  0x12
0x2b3b  brfalse.s loc_2B44
0x2b3d  ldloc.s  0x11
0x2b3f  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x2b44  endfinally
0x2b45  ldloc.s  0xA
0x2b47  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2b4c  brtrue   loc_29B0
0x2b51  leave.s  loc_2B69
0x2b53  ldloc.s  0xA
0x2b55  brfalse.s loc_2B5E
0x2b57  ldloc.s  0xA
  ... truncated ...
```
