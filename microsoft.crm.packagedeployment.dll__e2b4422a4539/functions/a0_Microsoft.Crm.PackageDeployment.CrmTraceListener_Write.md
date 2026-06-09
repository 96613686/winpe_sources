# Microsoft.Crm.PackageDeployment.CrmTraceListener::Write

- ea: `0xa0`
- end: `0xaa`
- name: `Microsoft.Crm.PackageDeployment.CrmTraceListener::Write`
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
0xa0  ldarg.0
0xa1  ldc.i4.s 0x10
0xa3  ldarg.1
0xa4  call     instance void Microsoft.Crm.PackageDeployment.CrmTraceListener::WriteToCrmTrace(valuetype [System]System.Diagnostics.TraceEventType eventType, string message)
0xa9  ret
```
