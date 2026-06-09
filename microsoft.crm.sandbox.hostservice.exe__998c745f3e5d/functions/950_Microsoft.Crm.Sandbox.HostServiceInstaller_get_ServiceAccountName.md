# Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceAccountName

- ea: `0x950`
- end: `0x966`
- name: `Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceAccountName`
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
0x950  ldarg.0
0x951  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x956  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x95b  ldstr    aUser// "user"
0x960  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x965  ret
```
