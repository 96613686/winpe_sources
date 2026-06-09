# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceAccount

- ea: `0x1c20`
- end: `0x1c5a`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceAccount`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1a80`

## callees

- `0x1c20`

## pseudocode

```c

```

## disassembly

```asm
0x1c20  ldarg.0
0x1c21  call     instance class [System.Configuration.Install]System.Configuration.Install.InstallContext [System.Configuration.Install]System.Configuration.Install.Installer::get_Context()
0x1c26  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System.Configuration.Install]System.Configuration.Install.InstallContext::get_Parameters()
0x1c2b  ldstr    aAccount// "account"
0x1c30  callvirt instance string [System]System.Collections.Specialized.StringDictionary::get_Item(string)
0x1c35  stloc.0
0x1c36  ldloc.0
0x1c37  brfalse.s loc_1C58
0x1c39  ldloc.0
0x1c3a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1c3f  ldc.i4.0
0x1c40  ble.s    loc_1C58
0x1c42  ldtoken  [System.ServiceProcess]System.ServiceProcess.ServiceAccount
0x1c47  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c4c  ldloc.0
0x1c4d  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x1c52  unbox.any [System.ServiceProcess]System.ServiceProcess.ServiceAccount
0x1c57  ret
0x1c58  ldc.i4.1
0x1c59  ret
```
