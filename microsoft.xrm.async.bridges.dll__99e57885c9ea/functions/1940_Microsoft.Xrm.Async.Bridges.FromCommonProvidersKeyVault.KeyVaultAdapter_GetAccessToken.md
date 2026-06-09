# Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::GetAccessToken

- ea: `0x1940`
- end: `0x1989`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::GetAccessToken`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1940  ldloca.s 0
0x1942  ldarg.0
0x1943  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter <GetAccessToken>d__9::<>4__this
0x1948  ldloca.s 0
0x194a  ldarg.1
0x194b  stfld    string <GetAccessToken>d__9::authority
0x1950  ldloca.s 0
0x1952  ldarg.2
0x1953  stfld    string <GetAccessToken>d__9::resource
0x1958  ldloca.s 0
0x195a  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::Create()
0x195f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetAccessToken>d__9::<>t__builder
0x1964  ldloca.s 0
0x1966  ldc.i4.m1
0x1967  stfld    int32 <GetAccessToken>d__9::<>1__state
0x196c  ldloc.0
0x196d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetAccessToken>d__9::<>t__builder
0x1972  stloc.1
0x1973  ldloca.s 1
0x1975  ldloca.s 0
0x1977  call     T0x2B00002B
0x197c  ldloca.s 0
0x197e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetAccessToken>d__9::<>t__builder
0x1983  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::get_Task()
0x1988  ret
```
