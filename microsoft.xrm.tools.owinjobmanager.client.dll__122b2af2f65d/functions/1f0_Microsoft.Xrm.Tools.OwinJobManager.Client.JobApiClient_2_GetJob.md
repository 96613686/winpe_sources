# Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::GetJob

- ea: `0x1f0`
- end: `0x231`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::GetJob`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1f0`

## pseudocode

```c

```

## disassembly

```asm
0x1f0  ldarg.1
0x1f1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1fb  brfalse.s loc_208
0x1fd  ldstr    aId// "id"
0x202  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x207  throw
0x208  ldarg.0
0x209  ldfld    class [System.Net.Http]System.Net.Http.HttpClient class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::client
0x20e  ldstr    a01_0// "{0}/{1}"
0x213  ldarg.0
0x214  ldfld    string class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::baseUri
0x219  ldarg.1
0x21a  box      [mscorlib]System.Guid
0x21f  call     string [mscorlib]System.String::Format(string, object, object)
0x224  ldc.i4.s 0xA
0x226  ldc.i4   0xBB8
0x22b  call     T0x2B000005
0x230  ret
```
