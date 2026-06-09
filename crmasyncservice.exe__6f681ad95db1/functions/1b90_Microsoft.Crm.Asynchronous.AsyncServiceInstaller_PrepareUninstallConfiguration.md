# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::PrepareUninstallConfiguration

- ea: `0x1b90`
- end: `0x1ba2`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::PrepareUninstallConfiguration`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1a60`

## callees

- `0x1ce0`

## pseudocode

```c

```

## disassembly

```asm
0x1b90  ldarg.0
0x1b91  ldfld    class [Microsoft.Crm.ServiceControl]Microsoft.Crm.ExtendedServiceInstaller Microsoft.Crm.Asynchronous.AsyncServiceInstaller::_serviceInstaller
0x1b96  ldarg.0
0x1b97  call     instance string Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceName()
0x1b9c  callvirt instance void [System.ServiceProcess]System.ServiceProcess.ServiceInstaller::set_ServiceName(string)
0x1ba1  ret
```
