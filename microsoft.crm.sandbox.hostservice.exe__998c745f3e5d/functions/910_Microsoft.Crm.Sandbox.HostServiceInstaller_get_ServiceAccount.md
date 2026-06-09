# Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceAccount

- ea: `0x910`
- end: `0x946`
- name: `Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceAccount`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7b0`

## callees

- `0x910`

## pseudocode

```c

```

## disassembly

```asm
0x910  ldarg.0
0x911  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x916  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x91b  ldstr    aAccount// "account"
0x920  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x925  stloc.0
0x926  ldloc.0
0x927  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x92c  brtrue.s loc_944
0x92e  ldtoken  [System.ServiceProcess]System.ServiceProcess.ServiceAccount
0x933  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x938  ldloc.0
0x939  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x93e  unbox.any [System.ServiceProcess]System.ServiceProcess.ServiceAccount
0x943  ret
0x944  ldc.i4.1
0x945  ret
```
