# Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::TryGetJob

- ea: `0x240`
- end: `0x280`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::TryGetJob`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x240`
- `0x9f0`

## pseudocode

```c

```

## disassembly

```asm
0x240  ldarg.1
0x241  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x246  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x24b  brfalse.s loc_258
0x24d  ldstr    aId// "id"
0x252  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x257  throw
0x258  nop
0x259  ldarg.0
0x25a  ldarg.1
0x25b  call     instance class Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<var<u1>> class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::GetJob(void)
0x260  stloc.0
0x261  leave.s  loc_27E
0x263  isinst   [System.Net.Http]System.Net.Http.HttpRequestException
0x268  dup
0x269  brtrue.s loc_26F
0x26b  pop
0x26c  ldc.i4.0
0x26d  br.s     loc_277
0x26f  call     bool Microsoft.Xrm.Tools.OwinJobManager.Client.Helpers.HttpClientExtensions::IsConnectFailure(class [System.Net.Http]System.Net.Http.HttpRequestException ex)
0x274  ldc.i4.0
0x275  cgt.un
0x277  endfilter
0x279  pop
0x27a  ldnull
0x27b  stloc.0
0x27c  leave.s  loc_27E
0x27e  ldloc.0
0x27f  ret
```
