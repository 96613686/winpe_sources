# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceDescription

- ea: `0x1de0`
- end: `0x1e18`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceDescription`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1a80`

## callees

- `0x1de0`

## pseudocode

```c

```

## disassembly

```asm
0x1de0  ldarg.0
0x1de1  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x1de6  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x1deb  ldstr    aDescription// "description"
0x1df0  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x1df5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1dfa  brfalse.s loc_1E02
0x1dfc  ldstr    aHandlesTheProc// "Handles the processing of queued Asynch"...
0x1e01  ret
0x1e02  ldarg.0
0x1e03  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x1e08  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x1e0d  ldstr    aDescription// "description"
0x1e12  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x1e17  ret
```
