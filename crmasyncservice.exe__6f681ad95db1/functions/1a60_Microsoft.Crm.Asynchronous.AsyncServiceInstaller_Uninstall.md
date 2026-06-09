# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::Uninstall

- ea: `0x1a60`
- end: `0x1a78`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::Uninstall`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1b90`

## pseudocode

```c

```

## disassembly

```asm
0x1a60  ldarg.0
0x1a61  call     instance void Microsoft.Crm.Asynchronous.AsyncServiceInstaller::PrepareUninstallConfiguration()
0x1a66  call     void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.PerformanceCounters::Uninstall()
0x1a6b  call     void [Microsoft.Crm.ServiceBus]Microsoft.Crm.ServiceBus.PerformanceCounters::Uninstall()
0x1a70  ldarg.0
0x1a71  ldarg.1
0x1a72  call     instance void [System.Configuration.Install]System.Configuration.Install.Installer::Uninstall(class [mscorlib]System.Collections.IDictionary)
0x1a77  ret
```
