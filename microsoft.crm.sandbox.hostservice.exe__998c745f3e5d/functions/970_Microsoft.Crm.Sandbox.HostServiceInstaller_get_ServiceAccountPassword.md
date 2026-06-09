# Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceAccountPassword

- ea: `0x970`
- end: `0x986`
- name: `Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceAccountPassword`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7b0`

## pseudocode

```c

```

## disassembly

```asm
0x970  ldarg.0
0x971  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x976  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x97b  ldstr    aPassword// "password"
0x980  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x985  ret
```
