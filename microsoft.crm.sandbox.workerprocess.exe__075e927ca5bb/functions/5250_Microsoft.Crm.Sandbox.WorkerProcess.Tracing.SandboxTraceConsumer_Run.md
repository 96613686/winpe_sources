# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer::Run

- ea: `0x5250`
- end: `0x534f`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer::Run`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x5250`

## callees

- `0x5120`
- `0x5250`
- `0x5350`
- `0x5540`
- `0x5560`
- `0x5580`
- `0x55a0`
- `0x55c0`
- `0x55e0`

## string_xrefs

- `0x52bd`: `Unable to trace or read from blocking collection. Item {0}, Exception: {1}`
- `0x5326`: `Shutting down trace consumer thread. Remaining elements on queue: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5250  ldnull
0x5251  stloc.0
0x5252  ldarg.0
0x5253  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer::_tokenSource
0x5258  callvirt instance bool [mscorlib]System.Threading.CancellationTokenSource::get_IsCancellationRequested()
0x525d  brfalse.s loc_5264
0x525f  leave    loc_5316
0x5264  ldarg.0
0x5265  ldfld    class [System]System.Collections.Concurrent.BlockingCollection`1<class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData> Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer::_traceQueue
0x526a  ldarg.0
0x526b  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer::_tokenSource
0x5270  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x5275  callvirt instance var<u1> class [System]System.Collections.Concurrent.BlockingCollection`1<class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData>::Take(!!T0)
0x527a  stloc.0
0x527b  ldloc.0
0x527c  brfalse.s loc_52A8
0x527e  ldarg.0
0x527f  ldloc.0
0x5280  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData::get_orgId()
0x5285  ldloc.0
0x5286  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData::get_traceCategory()
0x528b  ldloc.0
0x528c  callvirt instance valuetype [System]System.Diagnostics.TraceLevel Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData::get_traceLevel()
0x5291  ldloc.0
0x5292  callvirt instance int32 Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData::get_skipFrames()
0x5297  ldloc.0
0x5298  callvirt instance string Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData::get_format()
0x529d  ldloc.0
0x529e  callvirt instance object[] Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData::get_args()
0x52a3  call     instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer::Write(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, int32 skipFrames, string format, object[] args)
0x52a8  leave.s  Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer__Run
0x52aa  pop
0x52ab  leave.s  Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer__Run
0x52ad  stloc.1
0x52ae  ldarg.0
0x52af  ldfld    class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer::_tableWriter
0x52b4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x52b9  ldc.i4.s 0x21
0x52bb  ldc.i4.1
0x52bc  ldc.i4.0
0x52bd  ldstr    aUnableToTraceO// "Unable to trace or read from blocking c"...
0x52c2  ldc.i4.2
0x52c3  newarr   [mscorlib]System.Object
0x52c8  dup
0x52c9  ldc.i4.0
0x52ca  ldloc.0
0x52cb  brfalse.s loc_52D5
0x52cd  ldloc.0
0x52ce  callvirt instance string [mscorlib]System.Object::ToString()
0x52d3  br.s     loc_52DA
0x52d5  ldstr    aEmpty// "empty"
0x52da  stelem.ref
0x52db  dup
0x52dc  ldc.i4.1
0x52dd  ldloc.1
0x52de  callvirt instance string [mscorlib]System.Object::ToString()
0x52e3  stelem.ref
0x52e4  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::Write(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, int32 skipFrames, string format, object[] args)
0x52e9  leave.s  loc_5311
0x52eb  stloc.2
0x52ec  ldarg.0
0x52ed  ldfld    class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer::_tableWriter
0x52f2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x52f7  ldc.i4.s 0x21
0x52f9  ldc.i4.1
0x52fa  ldc.i4.0
0x52fb  ldstr    aUnhandledExcep_0// "Unhandled exception on Unhandled except"...
0x5300  ldc.i4.1
0x5301  newarr   [mscorlib]System.Object
0x5306  dup
0x5307  ldc.i4.0
0x5308  ldloc.2
0x5309  stelem.ref
0x530a  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::Write(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, int32 skipFrames, string format, object[] args)
0x530f  leave.s  loc_5311
0x5311  leave    Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer__Run
0x5316  nop
0x5317  ldarg.0
0x5318  ldfld    class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer::_tableWriter
0x531d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5322  ldc.i4.s 0x21
0x5324  ldc.i4.2
0x5325  ldc.i4.0
0x5326  ldstr    aShuttingDownTr// "Shutting down trace consumer thread. Re"...
0x532b  ldc.i4.1
0x532c  newarr   [mscorlib]System.Object
0x5331  dup
0x5332  ldc.i4.0
0x5333  ldarg.0
0x5334  ldfld    class [System]System.Collections.Concurrent.BlockingCollection`1<class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData> Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceConsumer::_traceQueue
0x5339  callvirt instance int32 class [System]System.Collections.Concurrent.BlockingCollection`1<class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData>::get_Count()
0x533e  box      [mscorlib]System.Int32
0x5343  stelem.ref
0x5344  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::Write(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, int32 skipFrames, string format, object[] args)
0x5349  leave.s  loc_534E
0x534b  pop
0x534c  leave.s  loc_534E
0x534e  ret
```
