# Microsoft.Crm.Sandbox.SandboxCallManager::NewCallTrackerInternal

- ea: `0x110`
- end: `0x18b`
- name: `Microsoft.Crm.Sandbox.SandboxCallManager::NewCallTrackerInternal`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0xd0`
- `0x100`

## callees

- `0x50`
- `0x70`
- `0x90`
- `0xa0`
- `0x110`
- `0x480`
- `0x4f0`

## pseudocode

```c

```

## disassembly

```asm
0x110  newobj   instance void Microsoft.Crm.Sandbox.SandboxCallTracker::.ctor()
0x115  stloc.0
0x116  ldarg.0
0x117  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxCallManager::_dictionaryLock
0x11c  ldc.i4.2
0x11d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x122  stloc.1
0x123  ldarg.0
0x124  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.CallManagerInfo> Microsoft.Crm.Sandbox.SandboxCallManager::_currentCallManagerList
0x129  ldloc.0
0x12a  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallTracker::get_CallInfo()
0x12f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x134  newobj   instance void Microsoft.Crm.Sandbox.CallManagerInfo::.ctor()
0x139  dup
0x13a  ldarg.1
0x13b  callvirt instance void Microsoft.Crm.Sandbox.CallManagerInfo::set_Context(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext value)
0x140  dup
0x141  ldarg.2
0x142  callvirt instance void Microsoft.Crm.Sandbox.CallManagerInfo::set_AssemblyData(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IPluginAssemblyData value)
0x147  dup
0x148  ldarg.3
0x149  callvirt instance void Microsoft.Crm.Sandbox.CallManagerInfo::set_AssemblyId(valuetype [mscorlib]System.Guid value)
0x14e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.CallManagerInfo>::Add(var<u1>, !!T0)
0x153  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x158  ldc.i4.s 0x21
0x15a  ldstr    aSandboxcallman// "SandboxCallManager.NewCallTrackerIntern"...
0x15f  ldc.i4.1
0x160  newarr   [mscorlib]System.Object
0x165  dup
0x166  ldc.i4.0
0x167  ldloc.0
0x168  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallTracker::get_CallInfo()
0x16d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x172  box      [mscorlib]System.Guid
0x177  stelem.ref
0x178  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x17d  leave.s  loc_189
0x17f  ldloc.1
0x180  brfalse.s loc_188
0x182  ldloc.1
0x183  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x188  endfinally
0x189  ldloc.0
0x18a  ret
```
