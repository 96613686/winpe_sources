# Microsoft.Crm.Sandbox.SandboxAssemblyManager::Start

- ea: `0x3030`
- end: `0x320b`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyManager::Start`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140`

## callees

- `0x2580`
- `0x3030`
- `0x3210`
- `0x3880`

## string_xrefs

- `0x3037`: `SandboxAssemblyManager ctor: AssemblyCachePath: {0}`
- `0x3064`: `SandboxAssemblyManager ctor: Create root directory for assembly cache`
- `0x31d5`: `Could not add assembly folder to organization assembly cache`

## pseudocode

```c

```

## disassembly

```asm
0x3030  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3035  ldc.i4.s 0x26
0x3037  ldstr    aSandboxassembl_29// "SandboxAssemblyManager ctor: AssemblyCa"...
0x303c  ldc.i4.1
0x303d  newarr   [mscorlib]System.Object
0x3042  dup
0x3043  ldc.i4.0
0x3044  ldnull
0x3045  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::AssemblyCachePath(string)
0x304a  stelem.ref
0x304b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3050  ldnull
0x3051  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::AssemblyCachePath(string)
0x3056  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x305b  brtrue.s loc_3080
0x305d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3062  ldc.i4.s 0x22
0x3064  ldstr    aSandboxassembl_30// "SandboxAssemblyManager ctor: Create roo"...
0x3069  ldc.i4.0
0x306a  newarr   [mscorlib]System.Object
0x306f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3074  ldnull
0x3075  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::AssemblyCachePath(string)
0x307a  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x307f  pop
0x3080  ldnull
0x3081  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::AssemblyCachePath(string)
0x3086  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x308b  ldstr    asc_137F4// "{*-*-*-*-*}"
0x3090  callvirt instance class [mscorlib]System.IO.DirectoryInfo[] [mscorlib]System.IO.DirectoryInfo::GetDirectories(string)
0x3095  stloc.0
0x3096  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x309b  ldc.i4.s 0x26
0x309d  ldstr    aSandboxassembl_31// "SandboxAssemblyManager ctor: dirInfos.L"...
0x30a2  ldc.i4.1
0x30a3  newarr   [mscorlib]System.Object
0x30a8  dup
0x30a9  ldc.i4.0
0x30aa  ldloc.0
0x30ab  ldlen
0x30ac  conv.i4
0x30ad  box      [mscorlib]System.Int32
0x30b2  stelem.ref
0x30b3  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x30b8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x30bd  stloc.1
0x30be  ldloc.0
0x30bf  stloc.3
0x30c0  ldc.i4.0
0x30c1  stloc.s  4
0x30c3  br       loc_3157
0x30c8  ldloc.3
0x30c9  ldloc.s  4
0x30cb  ldelem.ref
0x30cc  stloc.s  5
0x30ce  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x30d3  ldc.i4.s 0x26
0x30d5  ldstr    aSandboxassembl_32// "SandboxAssemblyManager ctor: dirInfo.Na"...
0x30da  ldc.i4.1
0x30db  newarr   [mscorlib]System.Object
0x30e0  dup
0x30e1  ldc.i4.0
0x30e2  ldloc.s  5
0x30e4  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x30e9  stelem.ref
0x30ea  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x30ef  ldloc.s  5
0x30f1  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_Name()
0x30f6  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x30fb  stloc.s  6
0x30fd  leave.s  loc_3149
0x30ff  stloc.s  7
0x3101  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3106  ldc.i4.s 0x22
0x3108  ldstr    aSandboxassembl_33// "SandboxAssemblyManager ctor: FormatExce"...
0x310d  ldc.i4.1
0x310e  newarr   [mscorlib]System.Object
0x3113  dup
0x3114  ldc.i4.0
0x3115  ldloc.s  7
0x3117  callvirt instance string [mscorlib]System.Exception::get_Message()
0x311c  stelem.ref
0x311d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3122  leave.s  loc_3151
0x3124  stloc.s  8
0x3126  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x312b  ldc.i4.s 0x22
0x312d  ldstr    aSandboxassembl_34// "SandboxAssemblyManager ctor: OverflowEx"...
0x3132  ldc.i4.1
0x3133  newarr   [mscorlib]System.Object
0x3138  dup
0x3139  ldc.i4.0
0x313a  ldloc.s  8
0x313c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3141  stelem.ref
0x3142  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3147  leave.s  loc_3151
0x3149  ldloc.1
0x314a  ldloc.s  6
0x314c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x3151  ldloc.s  4
0x3153  ldc.i4.1
0x3154  add
0x3155  stloc.s  4
0x3157  ldloc.s  4
0x3159  ldloc.3
0x315a  ldlen
0x315b  conv.i4
0x315c  blt      loc_30C8
0x3161  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3166  ldc.i4.s 0x26
0x3168  ldstr    aSandboxassembl_35// "SandboxAssemblyManager ctor: # orgs: {0"...
0x316d  ldc.i4.1
0x316e  newarr   [mscorlib]System.Object
0x3173  dup
0x3174  ldc.i4.0
0x3175  ldloc.1
0x3176  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x317b  box      [mscorlib]System.Int32
0x3180  stelem.ref
0x3181  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3186  ldloc.1
0x3187  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x318c  call     float64 Microsoft.Crm.Sandbox.SandboxAssemblyManager::MaxCacheSizePerOrgInMByte(int32 numberOfOrgs)
0x3191  stloc.2
0x3192  ldloc.1
0x3193  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x3198  stloc.s  9
0x319a  br.s     loc_31EC
0x319c  ldloca.s 9
0x319e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x31a3  stloc.s  0xA
0x31a5  ldloc.s  0xA
0x31a7  ldloc.2
0x31a8  newobj   instance void Microsoft.Crm.Sandbox.SandboxAssemblyCache::.ctor(valuetype [mscorlib]System.Guid organizationId, float64 maxCacheSizeInMByte)
0x31ad  stloc.s  0xB
0x31af  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache> Microsoft.Crm.Sandbox.SandboxAssemblyManager::_cacheMap
0x31b4  ldloc.s  0xA
0x31b6  ldloc.s  0xB
0x31b8  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache>::TryAdd(var<u1>, !!T0)
0x31bd  brfalse.s loc_31D5
0x31bf  ldloc.s  0xA
0x31c1  ldc.i4.s 0x26
0x31c3  ldstr    aSandboxassembl_36// "SandboxAssemblyManager ctor: Organizati"...
0x31c8  ldc.i4.0
0x31c9  newarr   [mscorlib]System.Object
0x31ce  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x31d3  br.s     loc_31E0
0x31d5  ldstr    aCouldNotAddAss// "Could not add assembly folder to organi"...
0x31da  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x31df  throw
0x31e0  ldloc.s  0xA
0x31e2  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0x31e7  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::AddedToAssemblyCache()
0x31ec  ldloca.s 9
0x31ee  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x31f3  brtrue.s loc_319C
0x31f5  leave.s  loc_3205
0x31f7  ldloca.s 9
0x31f9  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x31ff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3204  endfinally
0x3205  call     void Microsoft.Crm.Sandbox.SandboxAssemblyManager::UpdateTimer()
0x320a  ret
```
