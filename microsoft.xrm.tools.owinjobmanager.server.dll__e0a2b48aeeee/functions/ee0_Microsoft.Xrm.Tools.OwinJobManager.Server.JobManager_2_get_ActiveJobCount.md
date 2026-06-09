# Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::get_ActiveJobCount

- ea: `0xee0`
- end: `0xf0b`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::get_ActiveJobCount`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xee0`

## pseudocode

```c

```

## disassembly

```asm
0xee0  ldarg.0
0xee1  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::jobs
0xee6  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>, var<u1>> class <>c<var<u1>, !!T0>::<>9__16_0
0xeeb  dup
0xeec  brtrue.s loc_F05
0xeee  pop
0xeef  ldsfld   class <>c<var<u1>, !!T0> class <>c<var<u1>, !!T0>::<>9
0xef4  ldftn    instance bool class <>c<var<u1>, !!T0>::<get_ActiveJobCount>b__16_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>)
0xefa  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>, var<u1>>::.ctor(object, native int)
0xeff  dup
0xf00  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>, var<u1>> class <>c<var<u1>, !!T0>::<>9__16_0
0xf05  call     T0x2B000002
0xf0a  ret
```
