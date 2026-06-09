# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceAccountName

- ea: `0x1c60`
- end: `0x1c76`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceAccountName`
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
0x1c60  ldarg.0
0x1c61  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x1c66  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x1c6b  ldstr    aUser// "user"
0x1c70  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x1c75  ret
```
