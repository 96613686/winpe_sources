# Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::GetSecretAsync_0

- ea: `0x18f0`
- end: `0x1939`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::GetSecretAsync_0`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18d0`

## pseudocode

```c

```

## disassembly

```asm
0x18f0  ldloca.s 0
0x18f2  ldarg.0
0x18f3  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter <GetSecretAsync>d__8::<>4__this
0x18f8  ldloca.s 0
0x18fa  ldarg.1
0x18fb  stfld    class [System]System.Uri <GetSecretAsync>d__8::secretUri
0x1900  ldloca.s 0
0x1902  ldarg.2
0x1903  stfld    valuetype [mscorlib]System.Threading.CancellationToken <GetSecretAsync>d__8::cancellationToken
0x1908  ldloca.s 0
0x190a  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::Create()
0x190f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetSecretAsync>d__8::<>t__builder
0x1914  ldloca.s 0
0x1916  ldc.i4.m1
0x1917  stfld    int32 <GetSecretAsync>d__8::<>1__state
0x191c  ldloc.0
0x191d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetSecretAsync>d__8::<>t__builder
0x1922  stloc.1
0x1923  ldloca.s 1
0x1925  ldloca.s 0
0x1927  call     T0x2B00002A
0x192c  ldloca.s 0
0x192e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetSecretAsync>d__8::<>t__builder
0x1933  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::get_Task()
0x1938  ret
```
