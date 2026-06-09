# Microsoft.Crm.Sandbox.HostService::.ctor

- ea: `0x10`
- end: `0x24`
- name: `Microsoft.Crm.Sandbox.HostService::.ctor`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xaa0`

## callees

- `0x6f0`

## pseudocode

```c

```

## disassembly

```asm
0x10  ldarg.0
0x11  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::.ctor()
0x16  ldarg.0
0x17  call     instance void Microsoft.Crm.Sandbox.HostService::InitializeComponent()
0x1c  ldarg.0
0x1d  ldc.i4.0
0x1e  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::set_AutoLog(bool)
0x23  ret
```
