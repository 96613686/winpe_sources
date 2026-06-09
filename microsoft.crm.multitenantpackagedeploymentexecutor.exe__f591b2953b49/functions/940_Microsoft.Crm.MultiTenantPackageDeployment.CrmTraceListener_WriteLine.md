# Microsoft.Crm.MultiTenantPackageDeployment.CrmTraceListener::WriteLine

- ea: `0x940`
- end: `0x94a`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.CrmTraceListener::WriteLine`
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
0x940  ldarg.0
0x941  ldc.i4.s 0x10
0x943  ldarg.1
0x944  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.CrmTraceListener::WriteToCrmTrace(valuetype [System]System.Diagnostics.TraceEventType eventType, string message)
0x949  ret
```
