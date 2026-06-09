# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceOverrideProducer::Write

- ea: `0x53e0`
- end: `0x5475`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceOverrideProducer::Write`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x5480`

## callees

- `0x53e0`
- `0x5550`
- `0x5570`
- `0x5590`
- `0x55b0`
- `0x55d0`
- `0x55f0`
- `0x5680`

## pseudocode

```c

```

## disassembly

```asm
0x53e0  ldarg.0
0x53e1  ldfld    bool Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceOverrideProducer::_traceToConsole
0x53e6  brfalse.s loc_5435
0x53e8  ldstr    a0HhMmSs123// "[{0:HH:mm:ss}] [{1}] [{2}] {3}"
0x53ed  ldc.i4.4
0x53ee  newarr   [mscorlib]System.Object
0x53f3  dup
0x53f4  ldc.i4.0
0x53f5  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x53fa  box      [mscorlib]System.DateTime
0x53ff  stelem.ref
0x5400  dup
0x5401  ldc.i4.1
0x5402  ldarg.2
0x5403  box      [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory
0x5408  stelem.ref
0x5409  dup
0x540a  ldc.i4.2
0x540b  ldarg.3
0x540c  box      [System]System.Diagnostics.TraceLevel
0x5411  stelem.ref
0x5412  dup
0x5413  ldc.i4.3
0x5414  ldarg.s  6
0x5416  brfalse.s loc_542D
0x5418  ldarg.s  6
0x541a  ldlen
0x541b  brfalse.s loc_542D
0x541d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5422  ldarg.s  5
0x5424  ldarg.s  6
0x5426  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x542b  br.s     loc_542F
0x542d  ldarg.s  5
0x542f  stelem.ref
0x5430  call     void [mscorlib]System.Console::WriteLine(string, object[])
0x5435  newobj   instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData::.ctor()
0x543a  dup
0x543b  ldarg.1
0x543c  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData::set_orgId(valuetype [mscorlib]System.Guid value)
0x5441  dup
0x5442  ldarg.2
0x5443  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData::set_traceCategory(valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory value)
0x5448  dup
0x5449  ldarg.3
0x544a  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData::set_traceLevel(valuetype [System]System.Diagnostics.TraceLevel value)
0x544f  dup
0x5450  ldarg.s  4
0x5452  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData::set_skipFrames(int32 value)
0x5457  dup
0x5458  ldarg.s  5
0x545a  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData::set_format(string value)
0x545f  dup
0x5460  ldarg.s  6
0x5462  callvirt instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData::set_args(object[] value)
0x5467  stloc.0
0x5468  ldarg.0
0x5469  ldfld    class [System]System.Collections.Concurrent.BlockingCollection`1<class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData> Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceOverrideProducer::_traceQueue
0x546e  ldloc.0
0x546f  callvirt instance void class [System]System.Collections.Concurrent.BlockingCollection`1<class Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxTraceData>::Add(var<u1>)
0x5474  ret
```
