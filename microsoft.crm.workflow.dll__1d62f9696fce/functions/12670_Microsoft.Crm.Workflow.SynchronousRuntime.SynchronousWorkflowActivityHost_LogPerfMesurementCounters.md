# Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::LogPerfMesurementCounters

- ea: `0x12670`
- end: `0x12724`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::LogPerfMesurementCounters`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x11ec0`

## string_xrefs

- `0x126ef`: `Time taken to run the synchronous workflow (Milli Seconds) : ActivityRead {0}, RuntimeInit {1}, Runtime {2}, Total Time {3}.`

## pseudocode

```c

```

## disassembly

```asm
0x12670  ldarg.0
0x12671  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::_perfXamlActivityReadTime
0x12676  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x1267b  ldarg.0
0x1267c  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::_perfBeginTime
0x12681  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x12686  sub
0x12687  ldc.i4   0x2710
0x1268c  conv.i8
0x1268d  div
0x1268e  stloc.0
0x1268f  ldarg.0
0x12690  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::_perfRuntimeInitTime
0x12695  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x1269a  ldarg.0
0x1269b  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::_perfXamlActivityReadTime
0x126a0  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x126a5  sub
0x126a6  ldc.i4   0x2710
0x126ab  conv.i8
0x126ac  div
0x126ad  stloc.1
0x126ae  ldarg.0
0x126af  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::_perfRuntimeTime
0x126b4  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x126b9  ldarg.0
0x126ba  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::_perfRuntimeInitTime
0x126bf  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x126c4  sub
0x126c5  ldc.i4   0x2710
0x126ca  conv.i8
0x126cb  div
0x126cc  stloc.2
0x126cd  ldarg.0
0x126ce  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::_perfEndTime
0x126d3  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x126d8  ldarg.0
0x126d9  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowActivityHost::_perfBeginTime
0x126de  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x126e3  sub
0x126e4  ldc.i4   0x2710
0x126e9  conv.i8
0x126ea  div
0x126eb  stloc.3
0x126ec  ldarg.1
0x126ed  ldc.i4.s 0x1E
0x126ef  ldstr    aTimeTakenToRun_0// "Time taken to run the synchronous workf"...
0x126f4  ldc.i4.4
0x126f5  newarr   [mscorlib]System.Object
0x126fa  dup
0x126fb  ldc.i4.0
0x126fc  ldloc.0
0x126fd  box      [mscorlib]System.Int64
0x12702  stelem.ref
0x12703  dup
0x12704  ldc.i4.1
0x12705  ldloc.1
0x12706  box      [mscorlib]System.Int64
0x1270b  stelem.ref
0x1270c  dup
0x1270d  ldc.i4.2
0x1270e  ldloc.2
0x1270f  box      [mscorlib]System.Int64
0x12714  stelem.ref
0x12715  dup
0x12716  ldc.i4.3
0x12717  ldloc.3
0x12718  box      [mscorlib]System.Int64
0x1271d  stelem.ref
0x1271e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x12723  ret
```
