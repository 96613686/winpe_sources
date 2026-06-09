# Microsoft.Crm.Sandbox.SandboxCallManager::GetCallManagerInfo

- ea: `0x350`
- end: `0x439`
- name: `Microsoft.Crm.Sandbox.SandboxCallManager::GetCallManagerInfo`
- size: `233`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x230`
- `0x290`
- `0x2f0`

## callees

- `0x350`

## string_xrefs

- `0x388`: `SandboxCallManager.GetCallManagerInfo: inside lock`

## pseudocode

```c

```

## disassembly

```asm
0x350  ldarg.1
0x351  ldstr    aSandboxcallinf// "sandboxCallInfo"
0x356  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x35b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x360  ldc.i4.s 0x27
0x362  ldstr    aSandboxcallman_8// "SandboxCallManager.GetCallManagerInfo: "...
0x367  ldc.i4.0
0x368  newarr   [mscorlib]System.Object
0x36d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x372  ldnull
0x373  stloc.0
0x374  ldarg.0
0x375  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxCallManager::_dictionaryLock
0x37a  ldc.i4.0
0x37b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x380  stloc.1
0x381  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x386  ldc.i4.s 0x27
0x388  ldstr    aSandboxcallman_9// "SandboxCallManager.GetCallManagerInfo: "...
0x38d  ldc.i4.0
0x38e  newarr   [mscorlib]System.Object
0x393  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x398  ldarg.0
0x399  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.CallManagerInfo> Microsoft.Crm.Sandbox.SandboxCallManager::_currentCallManagerList
0x39e  ldarg.1
0x39f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x3a4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.CallManagerInfo>::ContainsKey(var<u1>)
0x3a9  brfalse.s loc_3EF
0x3ab  ldarg.0
0x3ac  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.CallManagerInfo> Microsoft.Crm.Sandbox.SandboxCallManager::_currentCallManagerList
0x3b1  ldarg.1
0x3b2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x3b7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.CallManagerInfo>::get_Item(void)
0x3bc  stloc.0
0x3bd  ldloc.0
0x3be  ldstr    aReturninfo// "returnInfo"
0x3c3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3c8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3cd  ldc.i4.s 0x21
0x3cf  ldstr    aSandboxcallman_10// "SandboxCallManager.GetCallManagerInfo: "...
0x3d4  ldc.i4.1
0x3d5  newarr   [mscorlib]System.Object
0x3da  dup
0x3db  ldc.i4.0
0x3dc  ldarg.1
0x3dd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x3e2  box      [mscorlib]System.Guid
0x3e7  stelem.ref
0x3e8  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3ed  leave.s  loc_420
0x3ef  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3f4  ldc.i4.s 0x21
0x3f6  ldstr    aSandboxcallman_11// "SandboxCallManager.GetCallManagerInfo: "...
0x3fb  ldc.i4.1
0x3fc  newarr   [mscorlib]System.Object
0x401  dup
0x402  ldc.i4.0
0x403  ldarg.1
0x404  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x409  box      [mscorlib]System.Guid
0x40e  stelem.ref
0x40f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x414  leave.s  loc_420
0x416  ldloc.1
0x417  brfalse.s loc_41F
0x419  ldloc.1
0x41a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41f  endfinally
0x420  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x425  ldc.i4.s 0x27
0x427  ldstr    aSandboxcallman_12// "SandboxCallManager.GetCallManagerInfo: "...
0x42c  ldc.i4.0
0x42d  newarr   [mscorlib]System.Object
0x432  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x437  ldloc.0
0x438  ret
```
