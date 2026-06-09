# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceShortName

- ea: `0x1e20`
- end: `0x1e58`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceShortName`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1ce0`

## callees

- `0x1e20`

## string_xrefs

- `0x1e2b`: `servicename`
- `0x1e4d`: `servicename`
- `0x1e3c`: `MSCRMAsyncService`

## pseudocode

```c

```

## disassembly

```asm
0x1e20  ldarg.0
0x1e21  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x1e26  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x1e2b  ldstr    aServicename// "servicename"
0x1e30  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x1e35  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1e3a  brfalse.s loc_1E42
0x1e3c  ldstr    aMscrmasyncserv// "MSCRMAsyncService"
0x1e41  ret
0x1e42  ldarg.0
0x1e43  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x1e48  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x1e4d  ldstr    aServicename// "servicename"
0x1e52  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x1e57  ret
```
