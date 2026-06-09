# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_SqlServerName

- ea: `0x1d80`
- end: `0x1d96`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_SqlServerName`
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
0x1d80  ldarg.0
0x1d81  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x1d86  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x1d8b  ldstr    aSqlserver// "sqlserver"
0x1d90  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x1d95  ret
```
