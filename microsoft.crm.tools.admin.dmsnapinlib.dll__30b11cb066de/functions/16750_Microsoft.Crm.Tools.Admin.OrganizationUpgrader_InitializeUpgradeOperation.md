# Microsoft.Crm.Tools.Admin.OrganizationUpgrader::InitializeUpgradeOperation

- ea: `0x16750`
- end: `0x1679d`
- name: `Microsoft.Crm.Tools.Admin.OrganizationUpgrader::InitializeUpgradeOperation`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x16700`
- `0x16710`
- `0x16720`
- `0x16730`

## callees

- `0x8610`
- `0x8a10`
- `0x8a90`
- `0x9870`
- `0x16750`
- `0x169a0`

## string_xrefs

- `0x1675b`: `ServerInstallInfo.UpgradeType`

## pseudocode

```c

```

## disassembly

```asm
0x16750  ldarg.0
0x16751  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0x16756  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x1675b  ldstr    aServerinstalli// "ServerInstallInfo.UpgradeType"
0x16760  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x16765  brtrue.s loc_16772
0x16767  ldarg.0
0x16768  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0x1676d  call     void Microsoft.Crm.Tools.Admin.OrganizationUpgrader::SetUpgradeType(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo)
0x16772  ldarg.0
0x16773  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0x16778  ldc.i4.0
0x16779  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_CreateDatabase(bool value)
0x1677e  ldarg.0
0x1677f  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0x16784  ldc.i4.1
0x16785  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_UpgradeDatabase(bool value)
0x1678a  ldarg.0
0x1678b  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0x16790  ldc.i4.0
0x16791  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_IsXrmOrg(bool value)
0x16796  ldarg.0
0x16797  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::InitializeActionList()
0x1679c  ret
```
