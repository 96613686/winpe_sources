# Microsoft.Crm.Sandbox.HostService::Dispose

- ea: `0x500`
- end: `0x51e`
- name: `Microsoft.Crm.Sandbox.HostService::Dispose`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x500`

## pseudocode

```c

```

## disassembly

```asm
0x500  ldarg.1
0x501  brfalse.s loc_516
0x503  ldarg.0
0x504  ldfld    class [System]System.ComponentModel.IContainer Microsoft.Crm.Sandbox.HostService::components
0x509  brfalse.s loc_516
0x50b  ldarg.0
0x50c  ldfld    class [System]System.ComponentModel.IContainer Microsoft.Crm.Sandbox.HostService::components
0x511  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x516  ldarg.0
0x517  ldarg.1
0x518  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::Dispose(bool)
0x51d  ret
```
