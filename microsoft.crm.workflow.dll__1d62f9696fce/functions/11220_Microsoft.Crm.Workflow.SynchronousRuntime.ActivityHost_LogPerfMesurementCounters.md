# Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::LogPerfMesurementCounters

- ea: `0x11220`
- end: `0x112d4`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::LogPerfMesurementCounters`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x10ad0`

## string_xrefs

- `0x1129f`: `Time taken to Run Intearctive Workflow and get a Page(Milli Seconds) : ActivityRead {0}, RuntimeInit {1}, Runtime {2}, Total Time {3}.`

## pseudocode

```c

```

## disassembly

```asm
0x11220  ldarg.0
0x11221  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::_perfXamlActivityReadTime
0x11226  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x1122b  ldarg.0
0x1122c  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::_perfBeginTime
0x11231  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x11236  sub
0x11237  ldc.i4   0x2710
0x1123c  conv.i8
0x1123d  div
0x1123e  stloc.0
0x1123f  ldarg.0
0x11240  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::_perfRuntimeInitTime
0x11245  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x1124a  ldarg.0
0x1124b  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::_perfXamlActivityReadTime
0x11250  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x11255  sub
0x11256  ldc.i4   0x2710
0x1125b  conv.i8
0x1125c  div
0x1125d  stloc.1
0x1125e  ldarg.0
0x1125f  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::_perfRuntimeTime
0x11264  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x11269  ldarg.0
0x1126a  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::_perfRuntimeInitTime
0x1126f  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x11274  sub
0x11275  ldc.i4   0x2710
0x1127a  conv.i8
0x1127b  div
0x1127c  stloc.2
0x1127d  ldarg.0
0x1127e  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::_perfEndTime
0x11283  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x11288  ldarg.0
0x11289  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.ActivityHost::_perfBeginTime
0x1128e  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x11293  sub
0x11294  ldc.i4   0x2710
0x11299  conv.i8
0x1129a  div
0x1129b  stloc.3
0x1129c  ldarg.1
0x1129d  ldc.i4.s 0x1E
0x1129f  ldstr    aTimeTakenToRun// "Time taken to Run Intearctive Workflow "...
0x112a4  ldc.i4.4
0x112a5  newarr   [mscorlib]System.Object
0x112aa  dup
0x112ab  ldc.i4.0
0x112ac  ldloc.0
0x112ad  box      [mscorlib]System.Int64
0x112b2  stelem.ref
0x112b3  dup
0x112b4  ldc.i4.1
0x112b5  ldloc.1
0x112b6  box      [mscorlib]System.Int64
0x112bb  stelem.ref
0x112bc  dup
0x112bd  ldc.i4.2
0x112be  ldloc.2
0x112bf  box      [mscorlib]System.Int64
0x112c4  stelem.ref
0x112c5  dup
0x112c6  ldc.i4.3
0x112c7  ldloc.3
0x112c8  box      [mscorlib]System.Int64
0x112cd  stelem.ref
0x112ce  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x112d3  ret
```
