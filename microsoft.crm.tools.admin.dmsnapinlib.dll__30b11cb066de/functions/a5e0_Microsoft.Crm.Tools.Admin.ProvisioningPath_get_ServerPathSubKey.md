# Microsoft.Crm.Tools.Admin.ProvisioningPath::get_ServerPathSubKey

- ea: `0xa5e0`
- end: `0xa63d`
- name: `Microsoft.Crm.Tools.Admin.ProvisioningPath::get_ServerPathSubKey`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xa480`
- `0xa4f0`

## callees

- `0xa5e0`
- `0xa650`

## string_xrefs

- `0xa60d`: `CRM_Server_InstallDir`
- `0xa61f`: `CRM_Live_InstallDir`

## pseudocode

```c

```

## disassembly

```asm
0xa5e0  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0xa5e5  ldstr    aSoftwareMicros// "Software\\Microsoft\\MSCRM"
0xa5ea  ldc.i4.0
0xa5eb  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0xa5f0  stloc.0
0xa5f1  ldloc.0
0xa5f2  ldstr    aCrmServerVersi// "CRM_Server_Version"
0xa5f7  ldsfld   string [mscorlib]System.String::Empty
0xa5fc  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0xa601  castclass [mscorlib]System.String
0xa606  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xa60b  brtrue.s loc_A61F
0xa60d  ldstr    aCrmServerInsta// "CRM_Server_InstallDir"
0xa612  call     void Microsoft.Crm.Tools.Admin.ProvisioningPath::set_InstallRegistryValue(string value)
0xa617  ldstr    aSoftwareMicros// "Software\\Microsoft\\MSCRM"
0xa61c  stloc.1
0xa61d  leave.s  loc_A63B
0xa61f  ldstr    aCrmLiveInstall// "CRM_Live_InstallDir"
0xa624  call     void Microsoft.Crm.Tools.Admin.ProvisioningPath::set_InstallRegistryValue(string value)
0xa629  ldstr    aSoftwareMicros_2// "Software\\Microsoft\\MSCRM Live"
0xa62e  stloc.1
0xa62f  leave.s  loc_A63B
0xa631  ldloc.0
0xa632  brfalse.s loc_A63A
0xa634  ldloc.0
0xa635  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa63a  endfinally
0xa63b  ldloc.1
0xa63c  ret
```
