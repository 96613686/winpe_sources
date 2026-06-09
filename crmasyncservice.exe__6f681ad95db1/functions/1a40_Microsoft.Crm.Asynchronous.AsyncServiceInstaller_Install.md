# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::Install

- ea: `0x1a40`
- end: `0x1a5e`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::Install`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1a80`
- `0x1bb0`

## pseudocode

```c

```

## disassembly

```asm
0x1a40  ldarg.0
0x1a41  call     instance void Microsoft.Crm.Asynchronous.AsyncServiceInstaller::PrepareInstallConfiguration()
0x1a46  call     void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.PerformanceCounters::Install()
0x1a4b  call     void [Microsoft.Crm.ServiceBus]Microsoft.Crm.ServiceBus.PerformanceCounters::Install()
0x1a50  ldarg.0
0x1a51  ldarg.1
0x1a52  call     instance void [System.Configuration.Install]System.Configuration.Install.Installer::Install(class [mscorlib]System.Collections.IDictionary)
0x1a57  ldarg.0
0x1a58  call     instance void Microsoft.Crm.Asynchronous.AsyncServiceInstaller::SetServiceExecutableParameters()
0x1a5d  ret
```
