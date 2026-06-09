# <>c__DisplayClass6_0::<Get>b__0

- ea: `0x1a30`
- end: `0x1ab3`
- name: `<>c__DisplayClass6_0::<Get>b__0`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1a30`

## pseudocode

```c

```

## disassembly

```asm
0x1a30  ldarg.0
0x1a31  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2<var<u1>, !!T0> class <>c__DisplayClass6_0<var<u1>, !!T0>::<>4__this
0x1a36  ldc.i4   0xC8
0x1a3b  ldarg.0
0x1a3c  ldfld    valuetype [mscorlib]System.Guid class <>c__DisplayClass6_0<var<u1>, !!T0>::id
0x1a41  ldarg.1
0x1a42  callvirt instance valuetype Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobStatus class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Status()
0x1a47  stloc.0
0x1a48  ldloca.s 0
0x1a4a  constrained. Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobStatus
0x1a50  callvirt instance string [mscorlib]System.Object::ToString()
0x1a55  ldarg.1
0x1a56  callvirt instance valuetype [mscorlib]System.TimeSpan class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Duration()
0x1a5b  ldarg.1
0x1a5c  callvirt instance class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>> class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Output()
0x1a61  callvirt instance int32 class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>>::get_Count()
0x1a66  ldarg.1
0x1a67  callvirt instance class [mscorlib]System.Exception class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Exception()
0x1a6c  dup
0x1a6d  brtrue.s loc_1A73
0x1a6f  pop
0x1a70  ldnull
0x1a71  br.s     loc_1A84
0x1a73  call     instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x1a78  dup
0x1a79  brtrue.s loc_1A7F
0x1a7b  pop
0x1a7c  ldnull
0x1a7d  br.s     loc_1A84
0x1a7f  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1a84  ldarg.1
0x1a85  callvirt instance class [mscorlib]System.Exception class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Exception()
0x1a8a  dup
0x1a8b  brtrue.s loc_1A91
0x1a8d  pop
0x1a8e  ldnull
0x1a8f  br.s     loc_1A96
0x1a91  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1a96  ldarg.1
0x1a97  callvirt instance class [mscorlib]System.Exception class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Exception()
0x1a9c  dup
0x1a9d  brtrue.s loc_1AA3
0x1a9f  pop
0x1aa0  ldnull
0x1aa1  br.s     loc_1AA8
0x1aa3  callvirt instance string [mscorlib]System.Object::ToString()
0x1aa8  newobj   instance void class <>f__AnonymousType3`7<valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.TimeSpan, int32, string, string, string>::.ctor(var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>)
0x1aad  callvirt T0x2B00000E
0x1ab2  ret
```
