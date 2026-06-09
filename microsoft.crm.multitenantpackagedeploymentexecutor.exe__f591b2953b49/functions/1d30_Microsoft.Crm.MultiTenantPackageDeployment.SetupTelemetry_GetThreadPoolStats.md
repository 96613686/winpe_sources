# Microsoft.Crm.MultiTenantPackageDeployment.SetupTelemetry::GetThreadPoolStats

- ea: `0x1d30`
- end: `0x1d4d`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.SetupTelemetry::GetThreadPoolStats`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c80`

## pseudocode

```c

```

## disassembly

```asm
0x1d30  ldloca.s 0
0x1d32  ldloca.s 1
0x1d34  call     void [mscorlib]System.Threading.ThreadPool::GetAvailableThreads(int32&, int32&)
0x1d39  ldloca.s 2
0x1d3b  ldloca.s 3
0x1d3d  call     void [mscorlib]System.Threading.ThreadPool::GetMaxThreads(int32&, int32&)
0x1d42  ldarg.0
0x1d43  ldloc.2
0x1d44  ldloc.0
0x1d45  sub
0x1d46  stind.i4
0x1d47  ldarg.1
0x1d48  ldloc.3
0x1d49  ldloc.1
0x1d4a  sub
0x1d4b  stind.i4
0x1d4c  ret
```
