# Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::RemoveJob

- ea: `0x300`
- end: `0x343`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::RemoveJob`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x300`

## string_xrefs

- `0x31e`: `{0}/{1}/remove`

## pseudocode

```c

```

## disassembly

```asm
0x300  ldarg.1
0x301  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x306  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x30b  brfalse.s loc_318
0x30d  ldstr    aId// "id"
0x312  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x317  throw
0x318  ldarg.0
0x319  ldfld    class [System.Net.Http]System.Net.Http.HttpClient class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::client
0x31e  ldstr    a01Remove// "{0}/{1}/remove"
0x323  ldarg.0
0x324  ldfld    string class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::baseUri
0x329  ldarg.1
0x32a  box      [mscorlib]System.Guid
0x32f  call     string [mscorlib]System.String::Format(string, object, object)
0x334  ldnull
0x335  ldc.i4.s 0xA
0x337  ldc.i4   0xBB8
0x33c  call     T0x2B000004
0x341  pop
0x342  ret
```
