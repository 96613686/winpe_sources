# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::.ctor

- ea: `0x50d0`
- end: `0x5118`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::.ctor`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4350`

## callees

- `0x4ae0`

## pseudocode

```c

```

## disassembly

```asm
0x50d0  ldarg.0
0x50d1  call     instance void [mscorlib]System.Object::.ctor()
0x50d6  ldarg.0
0x50d7  ldarg.1
0x50d8  ldstr    aSandboxworkert_0// "SandboxWorkerTraceError"
0x50dd  ldc.i4.1
0x50de  newobj   instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent::.ctor(string containerId, string eventName, valuetype [System]System.Diagnostics.TraceLevel level)
0x50e3  stfld    class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::_errorTracer
0x50e8  ldarg.0
0x50e9  ldarg.1
0x50ea  ldstr    aSandboxworkert_1// "SandboxWorkerTraceWarning"
0x50ef  ldc.i4.2
0x50f0  newobj   instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent::.ctor(string containerId, string eventName, valuetype [System]System.Diagnostics.TraceLevel level)
0x50f5  stfld    class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::_warningTracer
0x50fa  ldarg.0
0x50fb  ldarg.1
0x50fc  ldstr    aSandboxworkert_2// "SandboxWorkerTraceInfo"
0x5101  ldc.i4.3
0x5102  newobj   instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent::.ctor(string containerId, string eventName, valuetype [System]System.Diagnostics.TraceLevel level)
0x5107  stfld    class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::_infoTracer
0x510c  ldarg.0
0x510d  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x5112  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxMdsTableTraceWriter::lastUpdatedTime
0x5117  ret
```
