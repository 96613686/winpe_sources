# Microsoft.Crm.PackageDeployment.CrmTraceListener::LogTrace

- ea: `0x1a0`
- end: `0x1b1`
- name: `Microsoft.Crm.PackageDeployment.CrmTraceListener::LogTrace`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xc0`

## callees

- `0x1c0`

## pseudocode

```c

```

## disassembly

```asm
0x1a0  ldarg.0
0x1a1  ldarg.1
0x1a2  ldarg.2
0x1a3  ldarg.3
0x1a4  ldarg.s  4
0x1a6  ldc.i4.1
0x1a7  ldarg.s  5
0x1a9  ldarg.s  6
0x1ab  call     instance void Microsoft.Crm.PackageDeployment.CrmTraceListener::LogTrace(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, int32 skipFrames, string format, object[] args)
0x1b0  ret
```
