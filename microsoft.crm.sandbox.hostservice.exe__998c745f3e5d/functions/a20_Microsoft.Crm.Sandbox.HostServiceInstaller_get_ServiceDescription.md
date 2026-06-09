# Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceDescription

- ea: `0xa20`
- end: `0xa58`
- name: `Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceDescription`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7b0`

## callees

- `0xa20`

## pseudocode

```c

```

## disassembly

```asm
0xa20  ldarg.0
0xa21  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0xa26  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0xa2b  ldstr    aDescription// "description"
0xa30  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0xa35  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa3a  brfalse.s loc_A42
0xa3c  ldstr    aHandlesTheProc// "Handles the processing of isolated plug"...
0xa41  ret
0xa42  ldarg.0
0xa43  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0xa48  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0xa4d  ldstr    aDescription// "description"
0xa52  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0xa57  ret
```
