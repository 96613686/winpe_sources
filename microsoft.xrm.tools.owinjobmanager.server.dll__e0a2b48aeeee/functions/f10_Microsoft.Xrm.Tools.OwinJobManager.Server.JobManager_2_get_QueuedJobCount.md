# Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::get_QueuedJobCount

- ea: `0xf10`
- end: `0xf3b`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::get_QueuedJobCount`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xf10`

## pseudocode

```c

```

## disassembly

```asm
0xf10  ldarg.0
0xf11  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::jobs
0xf16  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>, var<u1>> class <>c<var<u1>, !!T0>::<>9__18_0
0xf1b  dup
0xf1c  brtrue.s loc_F35
0xf1e  pop
0xf1f  ldsfld   class <>c<var<u1>, !!T0> class <>c<var<u1>, !!T0>::<>9
0xf24  ldftn    instance bool class <>c<var<u1>, !!T0>::<get_QueuedJobCount>b__18_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>)
0xf2a  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>, var<u1>>::.ctor(object, native int)
0xf2f  dup
0xf30  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>, var<u1>> class <>c<var<u1>, !!T0>::<>9__18_0
0xf35  call     T0x2B000002
0xf3a  ret
```
