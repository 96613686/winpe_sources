# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent::get_FieldNames

- ea: `0x4bb0`
- end: `0x4bd7`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.CrmTraceEvent::get_FieldNames`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x4bb8`: `TaskName`

## pseudocode

```c

```

## disassembly

```asm
0x4bb0  ldc.i4.4
0x4bb1  newarr   [mscorlib]System.String
0x4bb6  dup
0x4bb7  ldc.i4.0
0x4bb8  ldstr    aTaskname// "TaskName"
0x4bbd  stelem.ref
0x4bbe  dup
0x4bbf  ldc.i4.1
0x4bc0  ldstr    aTracecategory// "traceCategory"
0x4bc5  stelem.ref
0x4bc6  dup
0x4bc7  ldc.i4.2
0x4bc8  ldstr    aTracemessage// "traceMessage"
0x4bcd  stelem.ref
0x4bce  dup
0x4bcf  ldc.i4.3
0x4bd0  ldstr    aStacktrace// "stackTrace"
0x4bd5  stelem.ref
0x4bd6  ret
```
