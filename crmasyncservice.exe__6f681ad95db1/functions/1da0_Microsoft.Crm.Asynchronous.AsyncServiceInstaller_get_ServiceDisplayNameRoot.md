# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceDisplayNameRoot

- ea: `0x1da0`
- end: `0x1dd8`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceDisplayNameRoot`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1d20`

## callees

- `0x1da0`

## string_xrefs

- `0x1dbc`: `Microsoft CRM Asynchronous Processing Service`

## pseudocode

```c

```

## disassembly

```asm
0x1da0  ldarg.0
0x1da1  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x1da6  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x1dab  ldstr    aDisplayname// "displayname"
0x1db0  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x1db5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1dba  brfalse.s loc_1DC2
0x1dbc  ldstr    aMicrosoftCrmAs_1// "Microsoft CRM Asynchronous Processing S"...
0x1dc1  ret
0x1dc2  ldarg.0
0x1dc3  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x1dc8  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x1dcd  ldstr    aDisplayname// "displayname"
0x1dd2  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x1dd7  ret
```
