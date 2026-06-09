# Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2::GetOutput

- ea: `0x10e0`
- end: `0x110f`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2::GetOutput`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x10e0  newobj   instance void class <>c__DisplayClass7_0<var<u1>, !!T0>::.ctor()
0x10e5  stloc.0
0x10e6  ldloc.0
0x10e7  ldarg.0
0x10e8  stfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2<var<u1>, !!T0> class <>c__DisplayClass7_0<var<u1>, !!T0>::<>4__this
0x10ed  ldloc.0
0x10ee  ldarg.2
0x10ef  stfld    int32 class <>c__DisplayClass7_0<var<u1>, !!T0>::skip
0x10f4  ldloc.0
0x10f5  ldarg.3
0x10f6  stfld    int32 class <>c__DisplayClass7_0<var<u1>, !!T0>::count
0x10fb  ldarg.0
0x10fc  ldarg.1
0x10fd  ldloc.0
0x10fe  ldftn    instance class [System.Web.Http]System.Web.Http.IHttpActionResult class <>c__DisplayClass7_0<var<u1>, !!T0>::<GetOutput>b__0(class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>)
0x1104  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>, var<u1>>::.ctor(object, native int)
0x1109  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2<var<u1>, !!T0>::TryFindJobAndProcess(valuetype [mscorlib]System.Guid, class [mscorlib]System.Func`2<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>, var<u1>>)
0x110e  ret
```
