# Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::CancelJob

- ea: `0x1a0`
- end: `0x1e3`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::CancelJob`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1a0`

## pseudocode

```c

```

## disassembly

```asm
0x1a0  ldarg.1
0x1a1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1ab  brfalse.s loc_1B8
0x1ad  ldstr    aId// "id"
0x1b2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1b7  throw
0x1b8  ldarg.0
0x1b9  ldfld    class [System.Net.Http]System.Net.Http.HttpClient class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::client
0x1be  ldstr    a01Cancel// "{0}/{1}/cancel"
0x1c3  ldarg.0
0x1c4  ldfld    string class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::baseUri
0x1c9  ldarg.1
0x1ca  box      [mscorlib]System.Guid
0x1cf  call     string [mscorlib]System.String::Format(string, object, object)
0x1d4  ldnull
0x1d5  ldc.i4.s 0xA
0x1d7  ldc.i4   0xBB8
0x1dc  call     T0x2B000004
0x1e1  pop
0x1e2  ret
```
