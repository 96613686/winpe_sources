# Microsoft.Crm.Sandbox.SandboxAssemblyManager::CheckDiskSpace

- ea: `0x35d0`
- end: `0x3651`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyManager::CheckDiskSpace`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2710`
- `0x35d0`

## string_xrefs

- `0x3610`: `cache`

## pseudocode

```c

```

## disassembly

```asm
0x35d0  ldstr    aSandboxassembl_48// "SandboxAssemblyManager.CheckDiskSpace"
0x35d5  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(string)
0x35da  stloc.0
0x35db  ldarg.0
0x35dc  isinst   AssemblyInfo
0x35e1  stloc.1
0x35e2  ldloc.1
0x35e3  ldstr    aAssemblyinfo// "assemblyInfo"
0x35e8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x35ed  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache> Microsoft.Crm.Sandbox.SandboxAssemblyManager::_cacheMap
0x35f2  ldloc.1
0x35f3  ldfld    valuetype [mscorlib]System.Guid AssemblyInfo::_organizationId
0x35f8  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache>::ContainsKey(var<u1>)
0x35fd  brfalse.s loc_3625
0x35ff  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache> Microsoft.Crm.Sandbox.SandboxAssemblyManager::_cacheMap
0x3604  ldloc.1
0x3605  ldfld    valuetype [mscorlib]System.Guid AssemblyInfo::_organizationId
0x360a  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.SandboxAssemblyCache>::get_Item(void)
0x360f  dup
0x3610  ldstr    aCache// "cache"
0x3615  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x361a  ldloc.1
0x361b  ldfld    int32 AssemblyInfo::_assemblySize
0x3620  callvirt instance void Microsoft.Crm.Sandbox.SandboxAssemblyCache::FileAdded(int32 assemblySize)
0x3625  leave.s  loc_3650
0x3627  stloc.2
0x3628  ldloc.2
0x3629  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x362e  ldc.i4.s 0x26
0x3630  ldstr    aSandboxassembl_49// "SandboxAssemblyManager.CheckDiskSpace: "...
0x3635  ldc.i4.1
0x3636  newarr   [mscorlib]System.Object
0x363b  dup
0x363c  ldc.i4.0
0x363d  ldloc.2
0x363e  stelem.ref
0x363f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3644  rethrow
0x3646  ldloc.0
0x3647  brfalse.s loc_364F
0x3649  ldloc.0
0x364a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x364f  endfinally
0x3650  ret
```
