# Microsoft.Crm.Sandbox.SandboxAssemblyManager::MonitorAssemblyCache

- ea: `0x3660`
- end: `0x369d`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyManager::MonitorAssemblyCache`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x3660`
- `0x36a0`

## string_xrefs

- `0x3660`: `SandboxAssemblyManager.MonitorAssemblyCache`
- `0x367c`: `SandboxAssemblyManager.MonitorAssemblyCache: EXCEPTION {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3660  ldstr    aSandboxassembl_50// "SandboxAssemblyManager.MonitorAssemblyC"...
0x3665  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(string)
0x366a  stloc.0
0x366b  ldarg.0
0x366c  call     void Microsoft.Crm.Sandbox.SandboxAssemblyManager::MonitorAssemblyCacheInternal(object notUsed)
0x3671  leave.s  loc_369C
0x3673  stloc.1
0x3674  ldloc.1
0x3675  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x367a  ldc.i4.s 0x26
0x367c  ldstr    aSandboxassembl_51// "SandboxAssemblyManager.MonitorAssemblyC"...
0x3681  ldc.i4.1
0x3682  newarr   [mscorlib]System.Object
0x3687  dup
0x3688  ldc.i4.0
0x3689  ldloc.1
0x368a  stelem.ref
0x368b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3690  rethrow
0x3692  ldloc.0
0x3693  brfalse.s loc_369B
0x3695  ldloc.0
0x3696  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x369b  endfinally
0x369c  ret
```
