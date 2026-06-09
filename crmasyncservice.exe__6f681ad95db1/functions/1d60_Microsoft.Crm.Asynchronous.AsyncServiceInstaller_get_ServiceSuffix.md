# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceSuffix

- ea: `0x1d60`
- end: `0x1d76`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceSuffix`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1ce0`
- `0x1d20`

## pseudocode

```c

```

## disassembly

```asm
0x1d60  ldarg.0
0x1d61  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x1d66  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x1d6b  ldstr    aInstance// "instance"
0x1d70  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x1d75  ret
```
