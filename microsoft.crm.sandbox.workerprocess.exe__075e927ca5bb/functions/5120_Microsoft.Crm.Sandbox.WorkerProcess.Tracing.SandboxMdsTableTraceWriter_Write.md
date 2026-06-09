# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::Write

- ea: `0x5120`
- end: `0x5187`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::Write`
- size: `103`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5250`
- `0x5350`
- `0x5370`

## callees

- `0x4af0`
- `0x5120`

## string_xrefs

- `0x5128`: `Cannot access a disposed MdsTableTraceWriter`

## pseudocode

```c

```

## disassembly

```asm
0x5120  ldarg.0
0x5121  ldfld    bool Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::_isDisposed
0x5126  brfalse.s loc_5133
0x5128  ldstr    aCannotAccessAD// "Cannot access a disposed MdsTableTraceW"...
0x512d  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x5132  throw
0x5133  ldarg.3
0x5134  ldc.i4.1
0x5135  sub
0x5136  switch   loc_5148, loc_515D, loc_5172
0x5147  ret
0x5148  ldarg.0
0x5149  ldfld    class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::_errorTracer
0x514e  ldarg.1
0x514f  ldarg.3
0x5150  ldarg.2
0x5151  ldarg.s  4
0x5153  ldarg.s  5
0x5155  ldarg.s  6
0x5157  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent::WriteTrace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, int32 skipFrames, string format, object[] args)
0x515c  ret
0x515d  ldarg.0
0x515e  ldfld    class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::_warningTracer
0x5163  ldarg.1
0x5164  ldarg.3
0x5165  ldarg.2
0x5166  ldarg.s  4
0x5168  ldarg.s  5
0x516a  ldarg.s  6
0x516c  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent::WriteTrace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, int32 skipFrames, string format, object[] args)
0x5171  ret
0x5172  ldarg.0
0x5173  ldfld    class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::_infoTracer
0x5178  ldarg.1
0x5179  ldarg.3
0x517a  ldarg.2
0x517b  ldarg.s  4
0x517d  ldarg.s  5
0x517f  ldarg.s  6
0x5181  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent::WriteTrace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, int32 skipFrames, string format, object[] args)
0x5186  ret
```
