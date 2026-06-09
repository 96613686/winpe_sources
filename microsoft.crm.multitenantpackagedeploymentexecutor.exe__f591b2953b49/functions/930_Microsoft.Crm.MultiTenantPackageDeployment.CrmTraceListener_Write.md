# Microsoft.Crm.MultiTenantPackageDeployment.CrmTraceListener::Write

- ea: `0x930`
- end: `0x93a`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.CrmTraceListener::Write`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x950`

## pseudocode

```c

```

## disassembly

```asm
0x930  ldarg.0
0x931  ldc.i4.s 0x10
0x933  ldarg.1
0x934  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.CrmTraceListener::WriteToCrmTrace(valuetype [System]System.Diagnostics.TraceEventType eventType, string message)
0x939  ret
```
