# <FindAsync>d__6::MoveNext

- ea: `0x3bc0`
- end: `0x3e4e`
- name: `<FindAsync>d__6::MoveNext`
- size: `654`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1080`
- `0x1560`
- `0x1570`
- `0x1580`
- `0x1590`
- `0x17f0`
- `0x1ab0`
- `0x3bc0`

## string_xrefs

- `0x3c96`: `Cannot lookup this secret URI.`

## pseudocode

```c

```

## disassembly

```asm
0x3bc0  ldarg.0
0x3bc1  ldfld    int32 <FindAsync>d__6::<>1__state
0x3bc6  stloc.0
0x3bc7  ldloc.0
0x3bc8  brfalse.s loc_3BF5
0x3bca  ldloc.0
0x3bcb  ldc.i4.1
0x3bcc  beq.s    loc_3BF5
0x3bce  ldarg.0
0x3bcf  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup <FindAsync>d__6::<>4__this
0x3bd4  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup::events
0x3bd9  ldarg.0
0x3bda  ldfld    class [System]System.Uri <FindAsync>d__6::secretUri
0x3bdf  dup
0x3be0  brtrue.s loc_3BE6
0x3be2  pop
0x3be3  ldnull
0x3be4  br.s     loc_3BEB
0x3be6  callvirt instance string [mscorlib]System.Object::ToString()
0x3beb  ldstr    aKeyvaultsecret// "KeyVaultSecretLookup"
0x3bf0  callvirt instance void Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents::OnBeginFind(string key, string callerType)
0x3bf5  nop
0x3bf6  ldloc.0
0x3bf7  brfalse.s loc_3C4C
0x3bf9  ldloc.0
0x3bfa  ldc.i4.1
0x3bfb  beq      loc_3D01
0x3c00  ldarg.0
0x3c01  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup <FindAsync>d__6::<>4__this
0x3c06  ldarg.0
0x3c07  ldfld    class [System]System.Uri <FindAsync>d__6::secretUri
0x3c0c  ldloca.s 3
0x3c0e  initobj  Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions
0x3c14  ldloc.3
0x3c15  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup::CanFindAsync(class [System]System.Uri secretUri, [opt] valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions options)
0x3c1a  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x3c1f  stloc.2
0x3c20  ldloca.s 2
0x3c22  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x3c27  brtrue.s loc_3C68
0x3c29  ldarg.0
0x3c2a  ldc.i4.0
0x3c2b  dup
0x3c2c  stloc.0
0x3c2d  stfld    int32 <FindAsync>d__6::<>1__state
0x3c32  ldarg.0
0x3c33  ldloc.2
0x3c34  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <FindAsync>d__6::<>u__1
0x3c39  ldarg.0
0x3c3a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <FindAsync>d__6::<>t__builder
0x3c3f  ldloca.s 2
0x3c41  ldarg.0
0x3c42  call     T0x2B000082
0x3c47  leave    loc_3E4D
0x3c4c  ldarg.0
0x3c4d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <FindAsync>d__6::<>u__1
0x3c52  stloc.2
0x3c53  ldarg.0
0x3c54  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <FindAsync>d__6::<>u__1
0x3c59  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x3c5f  ldarg.0
0x3c60  ldc.i4.m1
0x3c61  dup
0x3c62  stloc.0
0x3c63  stfld    int32 <FindAsync>d__6::<>1__state
0x3c68  ldloca.s 2
0x3c6a  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x3c6f  ldloca.s 2
0x3c71  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x3c77  brtrue.s loc_3CAD
0x3c79  ldarg.0
0x3c7a  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup <FindAsync>d__6::<>4__this
0x3c7f  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup::events
0x3c84  ldarg.0
0x3c85  ldfld    class [System]System.Uri <FindAsync>d__6::secretUri
0x3c8a  dup
0x3c8b  brtrue.s loc_3C91
0x3c8d  pop
0x3c8e  ldnull
0x3c8f  br.s     loc_3C96
0x3c91  callvirt instance string [mscorlib]System.Object::ToString()
0x3c96  ldstr    aCannotLookupTh// "Cannot lookup this secret URI."
0x3c9b  ldstr    aKeyvaultsecret// "KeyVaultSecretLookup"
0x3ca0  callvirt instance bool Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents::OnFailedFind(string key, string error, string callerType)
0x3ca5  pop
0x3ca6  ldnull
0x3ca7  stloc.1
0x3ca8  leave    loc_3E39
0x3cad  ldarg.0
0x3cae  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup <FindAsync>d__6::<>4__this
0x3cb3  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.IKeyVaultClient Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup::client
0x3cb8  ldarg.0
0x3cb9  ldfld    class [System]System.Uri <FindAsync>d__6::secretUri
0x3cbe  ldloca.s 5
0x3cc0  initobj  [mscorlib]System.Threading.CancellationToken
0x3cc6  ldloc.s  5
0x3cc8  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.IKeyVaultClient::GetSecretAsync(class [System]System.Uri secretUri, [opt] valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x3ccd  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x3cd2  stloc.s  4
0x3cd4  ldloca.s 4
0x3cd6  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x3cdb  brtrue.s loc_3D1E
0x3cdd  ldarg.0
0x3cde  ldc.i4.1
0x3cdf  dup
0x3ce0  stloc.0
0x3ce1  stfld    int32 <FindAsync>d__6::<>1__state
0x3ce6  ldarg.0
0x3ce7  ldloc.s  4
0x3ce9  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <FindAsync>d__6::<>u__2
0x3cee  ldarg.0
0x3cef  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <FindAsync>d__6::<>t__builder
0x3cf4  ldloca.s 4
0x3cf6  ldarg.0
0x3cf7  call     T0x2B000083
0x3cfc  leave    loc_3E4D
0x3d01  ldarg.0
0x3d02  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <FindAsync>d__6::<>u__2
0x3d07  stloc.s  4
0x3d09  ldarg.0
0x3d0a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <FindAsync>d__6::<>u__2
0x3d0f  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x3d15  ldarg.0
0x3d16  ldc.i4.m1
0x3d17  dup
0x3d18  stloc.0
0x3d19  stfld    int32 <FindAsync>d__6::<>1__state
0x3d1e  ldloca.s 4
0x3d20  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x3d25  ldloca.s 4
0x3d27  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x3d2d  ldarg.0
0x3d2e  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup <FindAsync>d__6::<>4__this
0x3d33  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup::events
0x3d38  ldarg.0
0x3d39  ldfld    class [System]System.Uri <FindAsync>d__6::secretUri
0x3d3e  dup
0x3d3f  brtrue.s loc_3D45
0x3d41  pop
0x3d42  ldnull
0x3d43  br.s     loc_3D4A
0x3d45  callvirt instance string [mscorlib]System.Object::ToString()
0x3d4a  ldstr    aKeyvaultsecret// "KeyVaultSecretLookup"
0x3d4f  callvirt instance void Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents::OnCompleteFind(string key, string callerType)
0x3d54  stloc.1
0x3d55  leave    loc_3E39
0x3d5a  isinst   [mscorlib]System.Exception
0x3d5f  dup
0x3d60  brtrue.s loc_3D66
0x3d62  pop
0x3d63  ldc.i4.0
0x3d64  br.s     loc_3D7C
0x3d66  stloc.s  6
0x3d68  ldloc.s  6
0x3d6a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3d6f  ldstr    aSecretNotFound// "Secret not found"
0x3d74  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x3d79  ldc.i4.0
0x3d7a  cgt.un
0x3d7c  endfilter
0x3d7e  pop
0x3d7f  ldarg.0
0x3d80  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup <FindAsync>d__6::<>4__this
0x3d85  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup::events
0x3d8a  ldarg.0
0x3d8b  ldfld    class [System]System.Uri <FindAsync>d__6::secretUri
0x3d90  dup
0x3d91  brtrue.s loc_3D97
0x3d93  pop
0x3d94  ldnull
0x3d95  br.s     loc_3D9C
0x3d97  callvirt instance string [mscorlib]System.Object::ToString()
0x3d9c  ldloc.s  6
0x3d9e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3da3  ldstr    aKeyvaultsecret// "KeyVaultSecretLookup"
0x3da8  callvirt instance bool Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents::OnFailedFind(string key, string error, string callerType)
0x3dad  pop
0x3dae  ldnull
0x3daf  stloc.1
0x3db0  leave    loc_3E39
0x3db5  isinst   [mscorlib]System.Exception
0x3dba  dup
0x3dbb  brtrue.s loc_3DC1
0x3dbd  pop
0x3dbe  ldc.i4.0
0x3dbf  br.s     loc_3DF6
0x3dc1  stloc.s  7
0x3dc3  ldarg.0
0x3dc4  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup <FindAsync>d__6::<>4__this
0x3dc9  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup::events
0x3dce  ldarg.0
0x3dcf  ldfld    class [System]System.Uri <FindAsync>d__6::secretUri
0x3dd4  dup
0x3dd5  brtrue.s loc_3DDB
0x3dd7  pop
0x3dd8  ldnull
0x3dd9  br.s     loc_3DE0
0x3ddb  callvirt instance string [mscorlib]System.Object::ToString()
0x3de0  ldloc.s  7
0x3de2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3de7  ldstr    aKeyvaultsecret// "KeyVaultSecretLookup"
0x3dec  ldloc.s  7
0x3dee  callvirt instance bool Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents::OnFailedFind(string key, string error, string callerType, class [mscorlib]System.Exception exception)
0x3df3  ldc.i4.0
0x3df4  cgt.un
0x3df6  endfilter
0x3df8  pop
0x3df9  ldarg.0
0x3dfa  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup <FindAsync>d__6::<>4__this
0x3dff  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup::events
0x3e04  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3e09  callvirt instance string [mscorlib]System.Type::get_FullName()
0x3e0e  ldstr    aOnfailedfind// ".OnFailedFind"
0x3e13  call     string [mscorlib]System.String::Concat(string, string)
0x3e18  ldloc.s  7
0x3e1a  newobj   instance void Microsoft.Xrm.Async.Bridges.FromCommon.ExceptionFilterContractViolationException::.ctor(string filterMemberFullName, class [mscorlib]System.Exception innerException)
0x3e1f  throw
0x3e20  stloc.s  8
0x3e22  ldarg.0
0x3e23  ldc.i4.s 0xFE
0x3e25  stfld    int32 <FindAsync>d__6::<>1__state
0x3e2a  ldarg.0
0x3e2b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <FindAsync>d__6::<>t__builder
0x3e30  ldloc.s  8
0x3e32  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetException(class [mscorlib]System.Exception)
0x3e37  leave.s  loc_3E4D
0x3e39  ldarg.0
0x3e3a  ldc.i4.s 0xFE
0x3e3c  stfld    int32 <FindAsync>d__6::<>1__state
0x3e41  ldarg.0
0x3e42  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <FindAsync>d__6::<>t__builder
0x3e47  ldloc.1
0x3e48  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetResult(var<u1>)
0x3e4d  ret
```
