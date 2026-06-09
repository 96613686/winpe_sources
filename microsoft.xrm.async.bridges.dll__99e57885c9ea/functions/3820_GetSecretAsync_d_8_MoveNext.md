# <GetSecretAsync>d__8::MoveNext

- ea: `0x3820`
- end: `0x38d9`
- name: `<GetSecretAsync>d__8::MoveNext`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x3820`

## pseudocode

```c

```

## disassembly

```asm
0x3820  ldarg.0
0x3821  ldfld    int32 <GetSecretAsync>d__8::<>1__state
0x3826  stloc.0
0x3827  ldloc.0
0x3828  brfalse.s loc_387A
0x382a  ldarg.0
0x382b  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter <GetSecretAsync>d__8::<>4__this
0x3830  ldfld    class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::keyVaultClient
0x3835  ldarg.0
0x3836  ldfld    class [System]System.Uri <GetSecretAsync>d__8::secretUri
0x383b  callvirt instance string [mscorlib]System.Object::ToString()
0x3840  ldarg.0
0x3841  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <GetSecretAsync>d__8::cancellationToken
0x3846  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret> [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.KeyVaultClient::GetSecretAsync(string, valuetype [mscorlib]System.Threading.CancellationToken)
0x384b  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret>::GetAwaiter()
0x3850  stloc.2
0x3851  ldloca.s 2
0x3853  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret>::get_IsCompleted()
0x3858  brtrue.s loc_3896
0x385a  ldarg.0
0x385b  ldc.i4.0
0x385c  dup
0x385d  stloc.0
0x385e  stfld    int32 <GetSecretAsync>d__8::<>1__state
0x3863  ldarg.0
0x3864  ldloc.2
0x3865  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret> <GetSecretAsync>d__8::<>u__1
0x386a  ldarg.0
0x386b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetSecretAsync>d__8::<>t__builder
0x3870  ldloca.s 2
0x3872  ldarg.0
0x3873  call     T0x2B00007F
0x3878  leave.s  loc_38D8
0x387a  ldarg.0
0x387b  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret> <GetSecretAsync>d__8::<>u__1
0x3880  stloc.2
0x3881  ldarg.0
0x3882  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret> <GetSecretAsync>d__8::<>u__1
0x3887  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret>
0x388d  ldarg.0
0x388e  ldc.i4.m1
0x388f  dup
0x3890  stloc.0
0x3891  stfld    int32 <GetSecretAsync>d__8::<>1__state
0x3896  ldloca.s 2
0x3898  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret>::GetResult()
0x389d  ldloca.s 2
0x389f  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret>
0x38a5  callvirt instance string [Microsoft.Azure.KeyVault]Microsoft.Azure.KeyVault.Secret::get_Value()
0x38aa  stloc.1
0x38ab  leave.s  loc_38C4
0x38ad  stloc.3
0x38ae  ldarg.0
0x38af  ldc.i4.s 0xFE
0x38b1  stfld    int32 <GetSecretAsync>d__8::<>1__state
0x38b6  ldarg.0
0x38b7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetSecretAsync>d__8::<>t__builder
0x38bc  ldloc.3
0x38bd  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetException(class [mscorlib]System.Exception)
0x38c2  leave.s  loc_38D8
0x38c4  ldarg.0
0x38c5  ldc.i4.s 0xFE
0x38c7  stfld    int32 <GetSecretAsync>d__8::<>1__state
0x38cc  ldarg.0
0x38cd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetSecretAsync>d__8::<>t__builder
0x38d2  ldloc.1
0x38d3  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetResult(var<u1>)
0x38d8  ret
```
