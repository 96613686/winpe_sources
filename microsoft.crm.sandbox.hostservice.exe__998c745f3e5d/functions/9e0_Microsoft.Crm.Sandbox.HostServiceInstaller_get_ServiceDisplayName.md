# Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceDisplayName

- ea: `0x9e0`
- end: `0xa18`
- name: `Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceDisplayName`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7b0`

## callees

- `0x9e0`

## pseudocode

```c

```

## disassembly

```asm
0x9e0  ldarg.0
0x9e1  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x9e6  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x9eb  ldstr    aDisplayname// "displayname"
0x9f0  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x9f5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9fa  brfalse.s loc_A02
0x9fc  ldstr    aMicrosoftCrmSa_0// "Microsoft CRM Sandbox"
0xa01  ret
0xa02  ldarg.0
0xa03  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0xa08  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0xa0d  ldstr    aDisplayname// "displayname"
0xa12  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0xa17  ret
```
