# Microsoft.Crm.Sandbox.SandboxCallManager::RemoveCallTracker

- ea: `0x190`
- end: `0x226`
- name: `Microsoft.Crm.Sandbox.SandboxCallManager::RemoveCallTracker`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4b0`

## callees

- `0x190`

## string_xrefs

- `0x1d4`: `SandboxCallManager.RemoveCallTracker: removed: {0}`
- `0x1fb`: `SandboxCallManager.RemoveCallTracker: not found: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x190  ldarg.1
0x191  ldstr    aSandboxcallinf// "sandboxCallInfo"
0x196  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x19b  ldarg.0
0x19c  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxCallManager::_dictionaryLock
0x1a1  ldc.i4.2
0x1a2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x1a7  stloc.0
0x1a8  ldarg.0
0x1a9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.CallManagerInfo> Microsoft.Crm.Sandbox.SandboxCallManager::_currentCallManagerList
0x1ae  ldarg.1
0x1af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x1b4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.CallManagerInfo>::ContainsKey(var<u1>)
0x1b9  brfalse.s loc_1F4
0x1bb  ldarg.0
0x1bc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.CallManagerInfo> Microsoft.Crm.Sandbox.SandboxCallManager::_currentCallManagerList
0x1c1  ldarg.1
0x1c2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x1c7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.CallManagerInfo>::Remove(var<u1>)
0x1cc  pop
0x1cd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1d2  ldc.i4.s 0x21
0x1d4  ldstr    aSandboxcallman_0// "SandboxCallManager.RemoveCallTracker: r"...
0x1d9  ldc.i4.1
0x1da  newarr   [mscorlib]System.Object
0x1df  dup
0x1e0  ldc.i4.0
0x1e1  ldarg.1
0x1e2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x1e7  box      [mscorlib]System.Guid
0x1ec  stelem.ref
0x1ed  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1f2  leave.s  loc_225
0x1f4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f9  ldc.i4.s 0x21
0x1fb  ldstr    aSandboxcallman_1// "SandboxCallManager.RemoveCallTracker: n"...
0x200  ldc.i4.1
0x201  newarr   [mscorlib]System.Object
0x206  dup
0x207  ldc.i4.0
0x208  ldarg.1
0x209  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x20e  box      [mscorlib]System.Guid
0x213  stelem.ref
0x214  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x219  leave.s  loc_225
0x21b  ldloc.0
0x21c  brfalse.s loc_224
0x21e  ldloc.0
0x21f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x224  endfinally
0x225  ret
```
