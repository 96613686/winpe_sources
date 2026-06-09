# Microsoft.Crm.Sandbox.SandboxSdkClientCache`1::DiscardClient

- ea: `0x9c20`
- end: `0x9cd8`
- name: `Microsoft.Crm.Sandbox.SandboxSdkClientCache`1::DiscardClient`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14d0`
- `0x9c20`

## string_xrefs

- `0x9c27`: `SandboxClientCache.DiscardClient`
- `0x9c9b`: `SandboxClientCache.DiscardClient: remove client: {0}; count: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x9c20  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9c25  ldc.i4.s 0x21
0x9c27  ldstr    aSandboxclientc_1// "SandboxClientCache.DiscardClient"
0x9c2c  ldc.i4.0
0x9c2d  newarr   [mscorlib]System.Object
0x9c32  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x9c37  ldarg.1
0x9c38  box      var<u1>
0x9c3d  brtrue.s loc_9C40
0x9c3f  ret
0x9c40  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_clientLock
0x9c45  ldc.i4.2
0x9c46  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x9c4b  stloc.0
0x9c4c  ldarg.1
0x9c4d  box      var<u1>
0x9c52  callvirt instance void class Microsoft.Crm.Sandbox.SandboxClientBase`1<class Microsoft.Crm.Sandbox.ISandboxSdkListener>::Stop()
0x9c57  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>> class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_clientDictionary
0x9c5c  ldarg.1
0x9c5d  box      var<u1>
0x9c62  callvirt instance string class Microsoft.Crm.Sandbox.SandboxClientBase`1<class Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_UriText()
0x9c67  ldloca.s 1
0x9c69  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>>::TryGetValue(var<u1>, !!T0)
0x9c6e  brfalse.s loc_9CCB
0x9c70  ldarg.1
0x9c71  box      var<u1>
0x9c76  ldloc.1
0x9c77  box      var<u1>
0x9c7c  bne.un.s loc_9CCB
0x9c7e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>> class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_clientDictionary
0x9c83  ldarg.1
0x9c84  box      var<u1>
0x9c89  callvirt instance string class Microsoft.Crm.Sandbox.SandboxClientBase`1<class Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_UriText()
0x9c8e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>>::Remove(var<u1>)
0x9c93  pop
0x9c94  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9c99  ldc.i4.s 0x21
0x9c9b  ldstr    aSandboxclientc_2// "SandboxClientCache.DiscardClient: remov"...
0x9ca0  ldc.i4.2
0x9ca1  newarr   [mscorlib]System.Object
0x9ca6  dup
0x9ca7  ldc.i4.0
0x9ca8  ldarg.1
0x9ca9  box      var<u1>
0x9cae  callvirt instance string class Microsoft.Crm.Sandbox.SandboxClientBase`1<class Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_UriText()
0x9cb3  stelem.ref
0x9cb4  dup
0x9cb5  ldc.i4.1
0x9cb6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>> class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_clientDictionary
0x9cbb  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>>::get_Count()
0x9cc0  box      [mscorlib]System.Int32
0x9cc5  stelem.ref
0x9cc6  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x9ccb  leave.s  loc_9CD7
0x9ccd  ldloc.0
0x9cce  brfalse.s loc_9CD6
0x9cd0  ldloc.0
0x9cd1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9cd6  endfinally
0x9cd7  ret
```
