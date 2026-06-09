# Microsoft.Crm.PackageDeployment.CrmTraceListener::WriteLine

- ea: `0xb0`
- end: `0xba`
- name: `Microsoft.Crm.PackageDeployment.CrmTraceListener::WriteLine`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xc0`

## pseudocode

```c

```

## disassembly

```asm
0xb0  ldarg.0
0xb1  ldc.i4.s 0x10
0xb3  ldarg.1
0xb4  call     instance void Microsoft.Crm.PackageDeployment.CrmTraceListener::WriteToCrmTrace(valuetype [System]System.Diagnostics.TraceEventType eventType, string message)
0xb9  ret
```
