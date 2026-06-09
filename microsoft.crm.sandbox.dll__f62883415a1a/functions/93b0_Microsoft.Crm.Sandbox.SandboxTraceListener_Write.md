# Microsoft.Crm.Sandbox.SandboxTraceListener::Write

- ea: `0x93b0`
- end: `0x93bf`
- name: `Microsoft.Crm.Sandbox.SandboxTraceListener::Write`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x93d0`

## pseudocode

```c

```

## disassembly

```asm
0x93b0  ldarg.0
0x93b1  ldarg.1
0x93b2  ldc.i4.3
0x93b3  ldc.i4.0
0x93b4  newarr   [mscorlib]System.Object
0x93b9  call     instance void Microsoft.Crm.Sandbox.SandboxTraceListener::Write(string message, valuetype [System]System.Diagnostics.TraceLevel traceLevel, object[] args)
0x93be  ret
```
