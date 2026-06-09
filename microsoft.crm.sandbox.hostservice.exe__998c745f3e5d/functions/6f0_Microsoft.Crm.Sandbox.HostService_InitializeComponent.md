# Microsoft.Crm.Sandbox.HostService::InitializeComponent

- ea: `0x6f0`
- end: `0x707`
- name: `Microsoft.Crm.Sandbox.HostService::InitializeComponent`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x10`

## string_xrefs

- `0x6fc`: `MSCRMSandboxService`

## pseudocode

```c

```

## disassembly

```asm
0x6f0  ldarg.0
0x6f1  newobj   instance void [System]System.ComponentModel.Container::.ctor()
0x6f6  stfld    class [System]System.ComponentModel.IContainer Microsoft.Crm.Sandbox.HostService::components
0x6fb  ldarg.0
0x6fc  ldstr    aMscrmsandboxse// "MSCRMSandboxService"
0x701  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::set_ServiceName(string)
0x706  ret
```
