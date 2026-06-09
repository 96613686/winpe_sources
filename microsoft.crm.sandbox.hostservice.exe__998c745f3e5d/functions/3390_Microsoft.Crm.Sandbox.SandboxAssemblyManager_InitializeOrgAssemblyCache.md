# Microsoft.Crm.Sandbox.SandboxAssemblyManager::InitializeOrgAssemblyCache

- ea: `0x3390`
- end: `0x343f`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyManager::InitializeOrgAssemblyCache`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3320`

## callees

- `0x3390`
- `0x3440`
- `0x34b0`

## string_xrefs

- `0x3393`: `SandboxAssemblyManager.InitializeOrgAssemblyCache: New assembly - assembly cache miss`
- `0x33f0`: `SandboxAssemblyManager.InitializeOrgAssemblyCache: Assembly cache - new organization`

## pseudocode

```c

```

## disassembly

```asm
0x3390  ldarg.1
0x3391  ldc.i4.s 0x22
0x3393  ldstr    aSandboxassembl_42// "SandboxAssemblyManager.InitializeOrgAss"...
0x3398  ldc.i4.0
0x3399  newarr   [mscorlib]System.Object
0x339e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x33a3  ldarg.0
0x33a4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x33a9  brfalse.s loc_33C6
0x33ab  ldarg.1
0x33ac  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0x33b1  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::AssemblyCacheMiss()
0x33b6  ldstr    aAssemblyShould// "Assembly should be provided"
0x33bb  ldc.i4   0x80044191
0x33c0  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmAssemblyMissingInCacheException::.ctor(string, int32)
0x33c5  throw
0x33c6  ldc.i4.0
0x33c7  stloc.0
0x33c8  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, object> Microsoft.Crm.Sandbox.SandboxAssemblyManager::_orgLock
0x33cd  ldarg.1
0x33ce  newobj   instance void [mscorlib]System.Object::.ctor()
0x33d3  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, object>::GetOrAdd(void, var<u1>)
0x33d8  stloc.1
0x33d9  ldloc.1
0x33da  stloc.2
0x33db  ldc.i4.0
0x33dc  stloc.3
0x33dd  ldloc.2
0x33de  ldloca.s 3
0x33e0  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x33e5  ldarg.2
0x33e6  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x33eb  brtrue.s loc_3409
0x33ed  ldarg.1
0x33ee  ldc.i4.s 0x22
0x33f0  ldstr    aSandboxassembl_43// "SandboxAssemblyManager.InitializeOrgAss"...
0x33f5  ldc.i4.0
0x33f6  newarr   [mscorlib]System.Object
0x33fb  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3400  ldarg.2
0x3401  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x3406  pop
0x3407  ldc.i4.1
0x3408  stloc.0
0x3409  leave.s  loc_3415
0x340b  ldloc.3
0x340c  brfalse.s loc_3414
0x340e  ldloc.2
0x340f  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x3414  endfinally
0x3415  ldloc.0
0x3416  brfalse.s loc_341E
0x3418  ldarg.1
0x3419  call     void Microsoft.Crm.Sandbox.SandboxAssemblyManager::InitializeOrgCacheObject(valuetype [mscorlib]System.Guid organizationId)
0x341e  ldloc.1
0x341f  stloc.2
0x3420  ldc.i4.0
0x3421  stloc.3
0x3422  ldloc.2
0x3423  ldloca.s 3
0x3425  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x342a  ldarg.0
0x342b  ldarg.1
0x342c  ldarg.3
0x342d  call     void Microsoft.Crm.Sandbox.SandboxAssemblyManager::SaveAssemblyToOrgCache(string pluginAssemblyContents, valuetype [mscorlib]System.Guid organizationId, string assemblyPath)
0x3432  leave.s  loc_343E
0x3434  ldloc.3
0x3435  brfalse.s loc_343D
0x3437  ldloc.2
0x3438  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x343d  endfinally
0x343e  ret
```
