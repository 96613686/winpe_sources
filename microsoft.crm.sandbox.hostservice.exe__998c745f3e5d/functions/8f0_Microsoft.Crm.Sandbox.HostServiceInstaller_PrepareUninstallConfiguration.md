# Microsoft.Crm.Sandbox.HostServiceInstaller::PrepareUninstallConfiguration

- ea: `0x8f0`
- end: `0x902`
- name: `Microsoft.Crm.Sandbox.HostServiceInstaller::PrepareUninstallConfiguration`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x7a0`

## callees

- `0x9d0`

## pseudocode

```c

```

## disassembly

```asm
0x8f0  ldarg.0
0x8f1  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Sandbox.HostServiceInstaller::_serviceInstaller
0x8f6  ldarg.0
0x8f7  call     instance string Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceName()
0x8fc  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::set_ServiceName(string)
0x901  ret
```
