# Microsoft.Crm.Sandbox.SandboxTraceListener::WriteLine

- ea: `0x93c0`
- end: `0x93cf`
- name: `Microsoft.Crm.Sandbox.SandboxTraceListener::WriteLine`
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
0x93c0  ldarg.0
0x93c1  ldarg.1
0x93c2  ldc.i4.3
0x93c3  ldc.i4.0
0x93c4  newarr   [mscorlib]System.Object
0x93c9  call     instance void Microsoft.Crm.Sandbox.SandboxTraceListener::Write(string message, valuetype [System]System.Diagnostics.TraceLevel traceLevel, object[] args)
0x93ce  ret
```
