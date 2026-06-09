# <>c::<Get>b__4_0

- ea: `0x19b0`
- end: `0x1a00`
- name: `<>c::<Get>b__4_0`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0x19b0  ldarga.s 1
0x19b2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>::get_Key()
0x19b7  ldarga.s 1
0x19b9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>::get_Value()
0x19be  callvirt instance valuetype Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobStatus class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Status()
0x19c3  stloc.0
0x19c4  ldloca.s 0
0x19c6  constrained. Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobStatus
0x19cc  callvirt instance string [mscorlib]System.Object::ToString()
0x19d1  ldarga.s 1
0x19d3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>::get_Value()
0x19d8  callvirt instance valuetype [mscorlib]System.TimeSpan class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Duration()
0x19dd  ldarga.s 1
0x19df  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>::get_Value()
0x19e4  callvirt instance var<u1> class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Input()
0x19e9  ldarga.s 1
0x19eb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>::get_Value()
0x19f0  callvirt instance class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>> class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Output()
0x19f5  callvirt instance int32 class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>>::get_Count()
0x19fa  newobj   instance void class <>f__AnonymousType2`5<valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.TimeSpan, var<u1>, !!T0>::.ctor(var<u1>, !!T0, var<u1>, void, var<u1>)
0x19ff  ret
```
