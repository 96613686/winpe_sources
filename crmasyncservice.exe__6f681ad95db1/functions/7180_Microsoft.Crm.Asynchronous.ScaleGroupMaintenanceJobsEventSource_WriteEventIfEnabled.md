# Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobsEventSource::WriteEventIfEnabled

- ea: `0x7180`
- end: `0x7192`
- name: `Microsoft.Crm.Asynchronous.ScaleGroupMaintenanceJobsEventSource::WriteEventIfEnabled`
- size: `18`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7070`
- `0x70d0`
- `0x7140`

## callees

- `0x7180`

## pseudocode

```c

```

## disassembly

```asm
0x7180  ldarg.0
0x7181  call     instance bool [mscorlib]System.Diagnostics.Tracing.EventSource::IsEnabled()
0x7186  brtrue.s loc_7189
0x7188  ret
0x7189  ldarg.0
0x718a  ldarg.1
0x718b  ldarg.2
0x718c  call     instance void [mscorlib]System.Diagnostics.Tracing.EventSource::WriteEvent(int32, object[])
0x7191  ret
```
