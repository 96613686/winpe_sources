# Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2::Add

- ea: `0xf90`
- end: `0x104b`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2::Add`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xf90`

## pseudocode

```c

```

## disassembly

```asm
0xf90  ldarg.0
0xf91  callvirt instance class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2<var<u1>, !!T0>::get_JobManager()
0xf96  ldarg.1
0xf97  ldarg.2
0xf98  callvirt instance class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::Add(var<u1>, void)
0xf9d  stloc.0
0xf9e  ldloc.0
0xf9f  callvirt instance bool class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_IsCompleted()
0xfa4  brfalse  loc_102E
0xfa9  ldarg.3
0xfaa  brfalse.s loc_FBE
0xfac  ldarg.0
0xfad  callvirt instance class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2<var<u1>, !!T0>::get_JobManager()
0xfb2  ldloc.0
0xfb3  callvirt instance valuetype [mscorlib]System.Guid class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Id()
0xfb8  callvirt instance bool class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::TryRemove(valuetype [mscorlib]System.Guid)
0xfbd  pop
0xfbe  ldarg.0
0xfbf  ldc.i4   0xC8
0xfc4  ldloc.0
0xfc5  callvirt instance valuetype [mscorlib]System.Guid class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Id()
0xfca  ldloc.0
0xfcb  callvirt instance valuetype Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobStatus class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Status()
0xfd0  ldloc.0
0xfd1  callvirt instance valuetype [mscorlib]System.TimeSpan class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Duration()
0xfd6  ldloc.0
0xfd7  callvirt instance class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>> class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Output()
0xfdc  callvirt instance var<u1>[] class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>>::GetAll()
0xfe1  ldloc.0
0xfe2  callvirt instance class [mscorlib]System.Exception class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Exception()
0xfe7  dup
0xfe8  brtrue.s loc_FEE
0xfea  pop
0xfeb  ldnull
0xfec  br.s     loc_FFF
0xfee  call     instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0xff3  dup
0xff4  brtrue.s loc_FFA
0xff6  pop
0xff7  ldnull
0xff8  br.s     loc_FFF
0xffa  callvirt instance string [mscorlib]System.Type::get_FullName()
0xfff  ldloc.0
0x1000  callvirt instance class [mscorlib]System.Exception class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Exception()
0x1005  dup
0x1006  brtrue.s loc_100C
0x1008  pop
0x1009  ldnull
0x100a  br.s     loc_1011
0x100c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1011  ldloc.0
0x1012  callvirt instance class [mscorlib]System.Exception class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Exception()
0x1017  dup
0x1018  brtrue.s loc_101E
0x101a  pop
0x101b  ldnull
0x101c  br.s     loc_1023
0x101e  callvirt instance string [mscorlib]System.Object::ToString()
0x1023  newobj   instance void class <>f__AnonymousType0`7<valuetype [mscorlib]System.Guid, valuetype Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobStatus, valuetype [mscorlib]System.TimeSpan, var<u1>[], void, string, string>::.ctor(var<u1>, !!T0, var<u1>, void, var<u1>, bool, var<u1>)
0x1028  callvirt T0x2B000004
0x102d  ret
0x102e  ldarg.0
0x102f  ldc.i4   0xCA
0x1034  ldloc.0
0x1035  callvirt instance valuetype [mscorlib]System.Guid class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Id()
0x103a  ldloc.0
0x103b  callvirt instance valuetype Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobStatus class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Status()
0x1040  newobj   instance void class <>f__AnonymousType1`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobStatus>::.ctor(var<u1>, !!T0)
0x1045  callvirt T0x2B000005
0x104a  ret
```
