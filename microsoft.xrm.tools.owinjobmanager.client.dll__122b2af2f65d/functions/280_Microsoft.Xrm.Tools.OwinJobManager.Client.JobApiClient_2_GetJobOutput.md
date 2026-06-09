# Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::GetJobOutput

- ea: `0x280`
- end: `0x2f2`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::GetJobOutput`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x280`

## pseudocode

```c

```

## disassembly

```asm
0x280  ldarg.1
0x281  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x286  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x28b  brfalse.s loc_298
0x28d  ldstr    aId// "id"
0x292  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x297  throw
0x298  ldarg.3
0x299  brtrue.s loc_2AB
0x29b  ldstr    aInvalidCount// "Invalid count"
0x2a0  ldstr    aCount// "count"
0x2a5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x2aa  throw
0x2ab  ldarg.0
0x2ac  ldfld    class [System.Net.Http]System.Net.Http.HttpClient class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::client
0x2b1  ldstr    a01OutputSkip2C// "{0}/{1}/output?skip={2}&count={3}"
0x2b6  ldc.i4.4
0x2b7  newarr   [mscorlib]System.Object
0x2bc  dup
0x2bd  ldc.i4.0
0x2be  ldarg.0
0x2bf  ldfld    string class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::baseUri
0x2c4  stelem.ref
0x2c5  dup
0x2c6  ldc.i4.1
0x2c7  ldarg.1
0x2c8  box      [mscorlib]System.Guid
0x2cd  stelem.ref
0x2ce  dup
0x2cf  ldc.i4.2
0x2d0  ldarg.2
0x2d1  box      [mscorlib]System.Int32
0x2d6  stelem.ref
0x2d7  dup
0x2d8  ldc.i4.3
0x2d9  ldarg.3
0x2da  box      [mscorlib]System.Int32
0x2df  stelem.ref
0x2e0  call     string [mscorlib]System.String::Format(string, object[])
0x2e5  ldc.i4.s 0xA
0x2e7  ldc.i4   0xBB8
0x2ec  call     T0x2B000006
0x2f1  ret
```
