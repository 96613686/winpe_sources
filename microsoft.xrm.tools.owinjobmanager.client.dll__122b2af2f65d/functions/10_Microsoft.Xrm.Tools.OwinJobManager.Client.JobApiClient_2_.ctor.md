# Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::.ctor

- ea: `0x10`
- end: `0x98`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::.ctor`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x10`

## string_xrefs

- `0x1e`: `baseUri`

## pseudocode

```c

```

## disassembly

```asm
0x10  ldarg.0
0x11  call     instance void [mscorlib]System.Object::.ctor()
0x16  ldarg.1
0x17  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1c  brfalse.s loc_29
0x1e  ldstr    aBaseuri// "baseUri"
0x23  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x28  throw
0x29  ldarg.0
0x2a  ldarg.1
0x2b  stfld    string class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::baseUri
0x30  ldarg.0
0x31  newobj   instance void [System.Net.Http]System.Net.Http.HttpClient::.ctor()
0x36  stfld    class [System.Net.Http]System.Net.Http.HttpClient class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::client
0x3b  ldarga.s 2
0x3d  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.TimeSpan>::get_HasValue()
0x42  brfalse.s loc_7D
0x44  ldarga.s 2
0x46  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.TimeSpan>::get_Value()
0x4b  ldc.r8   3.0
0x54  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x59  call     bool [mscorlib]System.TimeSpan::op_LessThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x5e  brfalse.s loc_6B
0x60  ldstr    aCannotUseATime// "Cannot use a time out less than 3 secon"...
0x65  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x6a  throw
0x6b  ldarg.0
0x6c  ldfld    class [System.Net.Http]System.Net.Http.HttpClient class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::client
0x71  ldarga.s 2
0x73  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.TimeSpan>::get_Value()
0x78  callvirt instance void [System.Net.Http]System.Net.Http.HttpClient::set_Timeout(valuetype [mscorlib]System.TimeSpan)
0x7d  ldarg.0
0x7e  ldarg.0
0x7f  ldfld    class [System.Net.Http]System.Net.Http.HttpClient class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::client
0x84  callvirt instance valuetype [mscorlib]System.TimeSpan [System.Net.Http]System.Net.Http.HttpClient::get_Timeout()
0x89  stloc.0
0x8a  ldloca.s 0
0x8c  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x91  conv.i4
0x92  stfld    int32 class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::httpClientTimeoutInMilliseconds
0x97  ret
```
