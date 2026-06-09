# Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2::Get

- ea: `0x1050`
- end: `0x1092`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2::Get`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1050`

## pseudocode

```c

```

## disassembly

```asm
0x1050  ldarg.0
0x1051  callvirt instance class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2<var<u1>, !!T0>::get_JobManager()
0x1056  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::GetAll()
0x105b  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>, var<u1>> class <>c<var<u1>, !!T0>::<>9__4_0
0x1060  dup
0x1061  brtrue.s loc_107A
0x1063  pop
0x1064  ldsfld   class <>c<var<u1>, !!T0> class <>c<var<u1>, !!T0>::<>9
0x1069  ldftn    instance class <>f__AnonymousType2`5<valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.TimeSpan, var<u1>, !!T0> class <>c<var<u1>, !!T0>::<Get>b__4_0(int32)
0x106f  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>, var<u1>>::.ctor(object, native int)
0x1074  dup
0x1075  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>, var<u1>> class <>c<var<u1>, !!T0>::<>9__4_0
0x107a  call     T0x2B000006
0x107f  call     T0x2B000007
0x1084  stloc.0
0x1085  ldarg.0
0x1086  ldc.i4   0xC8
0x108b  ldloc.0
0x108c  callvirt T0x2B000008
0x1091  ret
```
