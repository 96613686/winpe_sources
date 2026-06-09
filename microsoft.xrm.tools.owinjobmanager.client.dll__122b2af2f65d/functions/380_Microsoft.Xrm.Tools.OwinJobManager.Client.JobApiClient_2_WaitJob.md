# Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::WaitJob

- ea: `0x380`
- end: `0x407`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2::WaitJob`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x380`

## string_xrefs

- `0x3dc`: `Timed out in {0} when waiting for job {1} to complete`

## pseudocode

```c

```

## disassembly

```asm
0x380  ldarg.1
0x381  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x386  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x38b  brfalse.s loc_398
0x38d  ldstr    aId// "id"
0x392  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x397  throw
0x398  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x39d  stloc.0
0x39e  ldarga.s 4
0x3a0  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x3a5  ldarg.0
0x3a6  ldarg.1
0x3a7  call     instance class Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<var<u1>> class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::TryGetJob(void)
0x3ac  stloc.1
0x3ad  ldloc.1
0x3ae  brtrue.s loc_3B9
0x3b0  ldarga.s 4
0x3b2  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x3b7  ldnull
0x3b8  ret
0x3b9  ldloc.1
0x3ba  callvirt instance bool class Microsoft.Xrm.Tools.OwinJobManager.Client.Model.Job`1<var<u1>>::get_IsCompleted()
0x3bf  brfalse.s loc_3C3
0x3c1  ldloc.1
0x3c2  ret
0x3c3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x3c8  ldloc.0
0x3c9  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3ce  ldarg.2
0x3cf  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Subtraction(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x3d4  ldarg.3
0x3d5  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x3da  brfalse.s loc_3F8
0x3dc  ldstr    aTimedOutIn0Whe// "Timed out in {0} when waiting for job {"...
0x3e1  ldarg.3
0x3e2  box      [mscorlib]System.TimeSpan
0x3e7  ldarg.1
0x3e8  box      [mscorlib]System.Guid
0x3ed  call     string [mscorlib]System.String::Format(string, object, object)
0x3f2  newobj   instance void [mscorlib]System.TimeoutException::.ctor(string)
0x3f7  throw
0x3f8  ldarga.s 2
0x3fa  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x3ff  conv.i4
0x400  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x405  br.s     loc_39E
```
