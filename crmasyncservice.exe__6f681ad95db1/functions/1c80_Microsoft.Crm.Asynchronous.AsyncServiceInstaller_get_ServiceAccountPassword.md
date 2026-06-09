# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceAccountPassword

- ea: `0x1c80`
- end: `0x1c96`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceAccountPassword`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1a80`

## pseudocode

```c

```

## disassembly

```asm
0x1c80  ldarg.0
0x1c81  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x1c86  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x1c8b  ldstr    aPassword// "password"
0x1c90  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x1c95  ret
```
