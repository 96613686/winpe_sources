# Microsoft.Crm.Sandbox.HostServiceInstaller::Uninstall

- ea: `0x7a0`
- end: `0x7ae`
- name: `Microsoft.Crm.Sandbox.HostServiceInstaller::Uninstall`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x8f0`

## pseudocode

```c

```

## disassembly

```asm
0x7a0  ldarg.0
0x7a1  call     instance void Microsoft.Crm.Sandbox.HostServiceInstaller::PrepareUninstallConfiguration()
0x7a6  ldarg.0
0x7a7  ldarg.1
0x7a8  call     instance void [System.Configuration.Install]System.Configuration.Install.Installer::Uninstall(class [mscorlib]System.Collections.IDictionary)
0x7ad  ret
```
