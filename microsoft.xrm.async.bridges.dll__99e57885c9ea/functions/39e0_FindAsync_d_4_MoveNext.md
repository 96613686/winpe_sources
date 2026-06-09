# <FindAsync>d__4::MoveNext

- ea: `0x39e0`
- end: `0x3b95`
- name: `<FindAsync>d__4::MoveNext`
- size: `437`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0xab0`
- `0x1080`
- `0x1560`
- `0x1570`
- `0x1580`
- `0x1590`
- `0x17e0`
- `0x39e0`

## pseudocode

```c

```

## disassembly

```asm
0x39e0  ldarg.0
0x39e1  ldfld    int32 <FindAsync>d__4::<>1__state
0x39e6  stloc.0
0x39e7  ldloc.0
0x39e8  brfalse.s loc_3A1B
0x39ea  ldarg.0
0x39eb  ldfld    string <FindAsync>d__4::key
0x39f0  ldstr    aKey// "key"
0x39f5  call     T0x2B000024
0x39fa  call     class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotNullOrEmpty(class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> arg)
0x39ff  pop
0x3a00  ldarg.0
0x3a01  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup <FindAsync>d__4::<>4__this
0x3a06  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup::events
0x3a0b  ldarg.0
0x3a0c  ldfld    string <FindAsync>d__4::key
0x3a11  ldstr    aKeyvaultsecret// "KeyVaultSecretLookup"
0x3a16  callvirt instance void Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents::OnBeginFind(string key, string callerType)
0x3a1b  nop
0x3a1c  ldloc.0
0x3a1d  brfalse.s loc_3A70
0x3a1f  ldarg.0
0x3a20  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup <FindAsync>d__4::<>4__this
0x3a25  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.IKeyVaultClient Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup::client
0x3a2a  ldarg.0
0x3a2b  ldfld    string <FindAsync>d__4::key
0x3a30  ldloca.s 3
0x3a32  initobj  [mscorlib]System.Threading.CancellationToken
0x3a38  ldloc.3
0x3a39  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.IKeyVaultClient::GetSecretAsync(string secretName, [opt] valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x3a3e  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x3a43  stloc.2
0x3a44  ldloca.s 2
0x3a46  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x3a4b  brtrue.s loc_3A8C
0x3a4d  ldarg.0
0x3a4e  ldc.i4.0
0x3a4f  dup
0x3a50  stloc.0
0x3a51  stfld    int32 <FindAsync>d__4::<>1__state
0x3a56  ldarg.0
0x3a57  ldloc.2
0x3a58  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <FindAsync>d__4::<>u__1
0x3a5d  ldarg.0
0x3a5e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <FindAsync>d__4::<>t__builder
0x3a63  ldloca.s 2
0x3a65  ldarg.0
0x3a66  call     T0x2B000081
0x3a6b  leave    loc_3B94
0x3a70  ldarg.0
0x3a71  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <FindAsync>d__4::<>u__1
0x3a76  stloc.2
0x3a77  ldarg.0
0x3a78  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <FindAsync>d__4::<>u__1
0x3a7d  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x3a83  ldarg.0
0x3a84  ldc.i4.m1
0x3a85  dup
0x3a86  stloc.0
0x3a87  stfld    int32 <FindAsync>d__4::<>1__state
0x3a8c  ldloca.s 2
0x3a8e  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x3a93  ldloca.s 2
0x3a95  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x3a9b  ldarg.0
0x3a9c  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup <FindAsync>d__4::<>4__this
0x3aa1  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup::events
0x3aa6  ldarg.0
0x3aa7  ldfld    string <FindAsync>d__4::key
0x3aac  ldstr    aKeyvaultsecret// "KeyVaultSecretLookup"
0x3ab1  callvirt instance void Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents::OnCompleteFind(string key, string callerType)
0x3ab6  stloc.1
0x3ab7  leave    loc_3B80
0x3abc  isinst   [mscorlib]System.Exception
0x3ac1  dup
0x3ac2  brtrue.s loc_3AC8
0x3ac4  pop
0x3ac5  ldc.i4.0
0x3ac6  br.s     loc_3ADE
0x3ac8  stloc.s  4
0x3aca  ldloc.s  4
0x3acc  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3ad1  ldstr    aSecretNotFound// "Secret not found"
0x3ad6  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x3adb  ldc.i4.0
0x3adc  cgt.un
0x3ade  endfilter
0x3ae0  pop
0x3ae1  ldarg.0
0x3ae2  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup <FindAsync>d__4::<>4__this
0x3ae7  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup::events
0x3aec  ldarg.0
0x3aed  ldfld    string <FindAsync>d__4::key
0x3af2  ldloc.s  4
0x3af4  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3af9  ldstr    aKeyvaultsecret// "KeyVaultSecretLookup"
0x3afe  callvirt instance bool Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents::OnFailedFind(string key, string error, string callerType)
0x3b03  pop
0x3b04  ldnull
0x3b05  stloc.1
0x3b06  leave.s  loc_3B80
0x3b08  isinst   [mscorlib]System.Exception
0x3b0d  dup
0x3b0e  brtrue.s loc_3B14
0x3b10  pop
0x3b11  ldc.i4.0
0x3b12  br.s     loc_3B3D
0x3b14  stloc.s  5
0x3b16  ldarg.0
0x3b17  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup <FindAsync>d__4::<>4__this
0x3b1c  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup::events
0x3b21  ldarg.0
0x3b22  ldfld    string <FindAsync>d__4::key
0x3b27  ldloc.s  5
0x3b29  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3b2e  ldstr    aKeyvaultsecret// "KeyVaultSecretLookup"
0x3b33  ldloc.s  5
0x3b35  callvirt instance bool Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents::OnFailedFind(string key, string error, string callerType, class [mscorlib]System.Exception exception)
0x3b3a  ldc.i4.0
0x3b3b  cgt.un
0x3b3d  endfilter
0x3b3f  pop
0x3b40  ldarg.0
0x3b41  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup <FindAsync>d__4::<>4__this
0x3b46  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultSecretLookup::events
0x3b4b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3b50  callvirt instance string [mscorlib]System.Type::get_FullName()
0x3b55  ldstr    aOnfailedfind// ".OnFailedFind"
0x3b5a  call     string [mscorlib]System.String::Concat(string, string)
0x3b5f  ldloc.s  5
0x3b61  newobj   instance void Microsoft.Xrm.Async.Bridges.FromCommon.ExceptionFilterContractViolationException::.ctor(string filterMemberFullName, class [mscorlib]System.Exception innerException)
0x3b66  throw
0x3b67  stloc.s  6
0x3b69  ldarg.0
0x3b6a  ldc.i4.s 0xFE
0x3b6c  stfld    int32 <FindAsync>d__4::<>1__state
0x3b71  ldarg.0
0x3b72  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <FindAsync>d__4::<>t__builder
0x3b77  ldloc.s  6
0x3b79  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetException(class [mscorlib]System.Exception)
0x3b7e  leave.s  loc_3B94
0x3b80  ldarg.0
0x3b81  ldc.i4.s 0xFE
0x3b83  stfld    int32 <FindAsync>d__4::<>1__state
0x3b88  ldarg.0
0x3b89  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <FindAsync>d__4::<>t__builder
0x3b8e  ldloc.1
0x3b8f  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetResult(var<u1>)
0x3b94  ret
```
