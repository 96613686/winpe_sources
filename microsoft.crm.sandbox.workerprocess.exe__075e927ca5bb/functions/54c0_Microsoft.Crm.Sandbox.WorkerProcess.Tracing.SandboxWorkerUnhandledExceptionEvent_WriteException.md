# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxWorkerUnhandledExceptionEvent::WriteException

- ea: `0x54c0`
- end: `0x54e3`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.SandboxWorkerUnhandledExceptionEvent::WriteException`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x46b0`

## callees

- `0x4d90`

## pseudocode

```c

```

## disassembly

```asm
0x54c0  ldarg.0
0x54c1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x54c6  ldc.i4.2
0x54c7  newarr   [mscorlib]System.Object
0x54cc  dup
0x54cd  ldc.i4.0
0x54ce  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0x54d3  stelem.ref
0x54d4  dup
0x54d5  ldc.i4.1
0x54d6  ldarg.1
0x54d7  callvirt instance string [mscorlib]System.Object::ToString()
0x54dc  stelem.ref
0x54dd  call     instance void Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::Write(valuetype [mscorlib]System.Guid organizationId, object[] data)
0x54e2  ret
```
