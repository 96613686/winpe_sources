# Microsoft.Crm.Sandbox.SandboxSdkClientCache`1::GetSandboxClient

- ea: `0x9ce0`
- end: `0x9e6b`
- name: `Microsoft.Crm.Sandbox.SandboxSdkClientCache`1::GetSandboxClient`
- size: `395`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1450`
- `0x14d0`
- `0x9ce0`

## string_xrefs

- `0x9ce7`: `SandboxClientCache.GetSandboxClient: {0}`
- `0x9d17`: `SandboxClientCache.GetSandboxClient: listenerUri: {0}`
- `0x9d41`: `SandboxClientCache.GetSandboxClient: read lock/existing client`
- `0x9d62`: `uri mismatch!`
- `0x9dd2`: `uri mismatch!`
- `0x9e08`: `uri mismatch!`
- `0x9db1`: `SandboxClientCache.GetSandboxClient: write lock/existing client`
- `0x9e25`: `SandboxClientCache.GetSandboxClient: new client: {0}; count: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x9ce0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9ce5  ldc.i4.s 0x21
0x9ce7  ldstr    aSandboxclientc_3// "SandboxClientCache.GetSandboxClient: {0"...
0x9cec  ldc.i4.1
0x9ced  newarr   [mscorlib]System.Object
0x9cf2  dup
0x9cf3  ldc.i4.0
0x9cf4  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x9cf9  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0x9cfe  stelem.ref
0x9cff  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x9d04  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_clientLock
0x9d09  ldc.i4.0
0x9d0a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x9d0f  stloc.1
0x9d10  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9d15  ldc.i4.s 0x26
0x9d17  ldstr    aSandboxclientc_4// "SandboxClientCache.GetSandboxClient: li"...
0x9d1c  ldc.i4.1
0x9d1d  newarr   [mscorlib]System.Object
0x9d22  dup
0x9d23  ldc.i4.0
0x9d24  ldarg.1
0x9d25  stelem.ref
0x9d26  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x9d2b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>> class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_clientDictionary
0x9d30  ldarg.1
0x9d31  ldloca.s 0
0x9d33  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>>::TryGetValue(var<u1>, !!T0)
0x9d38  brfalse.s loc_9D83
0x9d3a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9d3f  ldc.i4.s 0x21
0x9d41  ldstr    aSandboxclientc_5// "SandboxClientCache.GetSandboxClient: re"...
0x9d46  ldc.i4.0
0x9d47  newarr   [mscorlib]System.Object
0x9d4c  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x9d51  ldloc.0
0x9d52  box      var<u1>
0x9d57  callvirt instance string class Microsoft.Crm.Sandbox.SandboxClientBase`1<class Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_UriText()
0x9d5c  ldarg.1
0x9d5d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9d62  ldstr    aUriMismatch// "uri mismatch!"
0x9d67  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x9d6c  ldloc.0
0x9d6d  box      var<u1>
0x9d72  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x9d77  callvirt instance void class Microsoft.Crm.Sandbox.SandboxClientBase`1<class Microsoft.Crm.Sandbox.ISandboxSdkListener>::set_LastUsed(valuetype [mscorlib]System.DateTime)
0x9d7c  ldloc.0
0x9d7d  stloc.2
0x9d7e  leave    loc_9E69
0x9d83  leave.s  loc_9D8F
0x9d85  ldloc.1
0x9d86  brfalse.s loc_9D8E
0x9d88  ldloc.1
0x9d89  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9d8e  endfinally
0x9d8f  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_clientLock
0x9d94  ldc.i4.2
0x9d95  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x9d9a  stloc.1
0x9d9b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>> class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_clientDictionary
0x9da0  ldarg.1
0x9da1  ldloca.s 0
0x9da3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>>::TryGetValue(var<u1>, !!T0)
0x9da8  brfalse.s loc_9DF0
0x9daa  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9daf  ldc.i4.s 0x21
0x9db1  ldstr    aSandboxclientc_6// "SandboxClientCache.GetSandboxClient: wr"...
0x9db6  ldc.i4.0
0x9db7  newarr   [mscorlib]System.Object
0x9dbc  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x9dc1  ldloc.0
0x9dc2  box      var<u1>
0x9dc7  callvirt instance string class Microsoft.Crm.Sandbox.SandboxClientBase`1<class Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_UriText()
0x9dcc  ldarg.1
0x9dcd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9dd2  ldstr    aUriMismatch// "uri mismatch!"
0x9dd7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x9ddc  ldloc.0
0x9ddd  box      var<u1>
0x9de2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x9de7  callvirt instance void class Microsoft.Crm.Sandbox.SandboxClientBase`1<class Microsoft.Crm.Sandbox.ISandboxSdkListener>::set_LastUsed(valuetype [mscorlib]System.DateTime)
0x9dec  ldloc.0
0x9ded  stloc.2
0x9dee  leave.s  loc_9E69
0x9df0  ldarg.2
0x9df1  callvirt instance var<u1> class GetDefaultSandboxSdkClientInstance<var<u1>>::Invoke()
0x9df6  stloc.0
0x9df7  ldloc.0
0x9df8  box      var<u1>
0x9dfd  callvirt instance string class Microsoft.Crm.Sandbox.SandboxClientBase`1<class Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_UriText()
0x9e02  ldarg.1
0x9e03  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9e08  ldstr    aUriMismatch// "uri mismatch!"
0x9e0d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x9e12  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>> class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_clientDictionary
0x9e17  ldarg.1
0x9e18  ldloc.0
0x9e19  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>>::set_Item(var<u1>, !!T0)
0x9e1e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9e23  ldc.i4.s 0x21
0x9e25  ldstr    aSandboxclientc_7// "SandboxClientCache.GetSandboxClient: ne"...
0x9e2a  ldc.i4.2
0x9e2b  newarr   [mscorlib]System.Object
0x9e30  dup
0x9e31  ldc.i4.0
0x9e32  ldarg.1
0x9e33  stelem.ref
0x9e34  dup
0x9e35  ldc.i4.1
0x9e36  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>> class Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>>::_clientDictionary
0x9e3b  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, var<u1>>::get_Count()
0x9e40  box      [mscorlib]System.Int32
0x9e45  stelem.ref
0x9e46  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x9e4b  ldloc.0
0x9e4c  box      var<u1>
0x9e51  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x9e56  callvirt instance void class Microsoft.Crm.Sandbox.SandboxClientBase`1<class Microsoft.Crm.Sandbox.ISandboxSdkListener>::set_LastUsed(valuetype [mscorlib]System.DateTime)
0x9e5b  ldloc.0
0x9e5c  stloc.2
0x9e5d  leave.s  loc_9E69
0x9e5f  ldloc.1
0x9e60  brfalse.s loc_9E68
0x9e62  ldloc.1
0x9e63  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9e68  endfinally
0x9e69  ldloc.2
0x9e6a  ret
```
