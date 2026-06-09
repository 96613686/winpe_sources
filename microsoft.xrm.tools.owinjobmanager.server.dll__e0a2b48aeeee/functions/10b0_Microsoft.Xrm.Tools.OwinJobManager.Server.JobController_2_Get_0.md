# Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2::Get_0

- ea: `0x10b0`
- end: `0x10dd`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2::Get_0`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x10b0  newobj   instance void class <>c__DisplayClass6_0<var<u1>, !!T0>::.ctor()
0x10b5  stloc.0
0x10b6  ldloc.0
0x10b7  ldarg.0
0x10b8  stfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2<var<u1>, !!T0> class <>c__DisplayClass6_0<var<u1>, !!T0>::<>4__this
0x10bd  ldloc.0
0x10be  ldarg.1
0x10bf  stfld    valuetype [mscorlib]System.Guid class <>c__DisplayClass6_0<var<u1>, !!T0>::id
0x10c4  ldarg.0
0x10c5  ldloc.0
0x10c6  ldfld    valuetype [mscorlib]System.Guid class <>c__DisplayClass6_0<var<u1>, !!T0>::id
0x10cb  ldloc.0
0x10cc  ldftn    instance class [System.Web.Http]System.Web.Http.IHttpActionResult class <>c__DisplayClass6_0<var<u1>, !!T0>::<Get>b__0(class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>)
0x10d2  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>, var<u1>>::.ctor(object, native int)
0x10d7  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2<var<u1>, !!T0>::TryFindJobAndProcess(valuetype [mscorlib]System.Guid, class [mscorlib]System.Func`2<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>, var<u1>>)
0x10dc  ret
```
