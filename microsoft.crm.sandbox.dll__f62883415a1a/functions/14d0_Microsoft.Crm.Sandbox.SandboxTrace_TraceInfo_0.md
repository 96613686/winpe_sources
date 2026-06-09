# Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo_0

- ea: `0x14d0`
- end: `0x14db`
- name: `Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo_0`
- size: `11`
- prototype: ``
- caller_count: `26`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3b0`
- `0x550`
- `0x620`
- `0xb60`
- `0x2030`
- `0x2800`
- `0x3080`
- `0x32f0`
- `0x36a0`
- `0x53f0`
- `0x5580`
- `0x5680`
- `0x5a30`
- `0x5bd0`
- `0x6fe0`
- `0x78e0`
- `0x7bf0`
- `0x7d40`
- `0x80d0`
- `0x82a0`
- `0x93d0`
- `0x9ba0`
- `0x9c20`
- `0x9ce0`
- `0x9e70`
- `0xaeb0`

## callees

- `0x14c0`

## pseudocode

```c

```

## disassembly

```asm
0x14d0  ldarg.0
0x14d1  ldarg.1
0x14d2  ldc.i4.0
0x14d3  ldarg.2
0x14d4  ldarg.3
0x14d5  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, int32 skipFrames, string format, object[] args)
0x14da  ret
```
