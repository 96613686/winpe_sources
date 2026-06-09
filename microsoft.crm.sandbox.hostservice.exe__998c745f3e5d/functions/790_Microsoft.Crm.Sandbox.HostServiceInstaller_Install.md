# Microsoft.Crm.Sandbox.HostServiceInstaller::Install

- ea: `0x790`
- end: `0x79e`
- name: `Microsoft.Crm.Sandbox.HostServiceInstaller::Install`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x7b0`

## pseudocode

```c

```

## disassembly

```asm
0x790  ldarg.0
0x791  call     instance void Microsoft.Crm.Sandbox.HostServiceInstaller::PrepareInstallConfiguration()
0x796  ldarg.0
0x797  ldarg.1
0x798  call     instance void [System.Configuration.Install]System.Configuration.Install.Installer::Install(class [mscorlib]System.Collections.IDictionary)
0x79d  ret
```
