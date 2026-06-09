# Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::VerifySettings_0

- ea: `0x2e4c0`
- end: `0x2e580`
- name: `Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::VerifySettings_0`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x2e4b0`

## callees

- `0x2e4c0`
- `0x2e580`
- `0x2e880`
- `0x2eb90`
- `0x2ebd0`
- `0x2ec40`
- `0x2ecc0`
- `0x2ece0`
- `0x2ed00`
- `0x2ed20`
- `0x2ed40`
- `0x2edd0`

## string_xrefs

- `0x2e4c1`: `settingsId`
- `0x2e51f`: `referenceXml`

## pseudocode

```c

```

## disassembly

```asm
0x2e4c0  ldarg.1
0x2e4c1  ldstr    aSettingsid// "settingsId"
0x2e4c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2e4cb  ldarg.3
0x2e4cc  ldstr    aEnvironmentnam// "environmentName"
0x2e4d1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2e4d6  ldarg.2
0x2e4d7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e4dc  brfalse.s loc_2E4EA
0x2e4de  call     string Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::GetStandardReferenceFileName()
0x2e4e3  call     string [mscorlib]System.IO.File::ReadAllText(string)
0x2e4e8  starg.s  2
0x2e4ea  ldarg.s  4
0x2e4ec  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e4f1  brfalse.s loc_2E505
0x2e4f3  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x2e4f8  ldstr    aGeoname// "GeoName"
0x2e4fd  ldc.i4.0
0x2e4fe  callvirt T0x2B000001
0x2e503  starg.s  4
0x2e505  ldarg.s  4
0x2e507  call     string Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::GetStandardGeoName(string geoName)
0x2e50c  starg.s  4
0x2e50e  ldarg.s  5
0x2e510  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2e515  brfalse.s loc_2E51E
0x2e517  call     string Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::GetCurrentDatacenterName()
0x2e51c  starg.s  5
0x2e51e  ldarg.2
0x2e51f  ldstr    aReferencexml// "referenceXml"
0x2e524  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2e529  ldarg.s  4
0x2e52b  ldstr    aGeoname_0// "geoName"
0x2e530  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2e535  ldarg.s  5
0x2e537  ldstr    aDatacentername// "datacenterName"
0x2e53c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2e541  ldarg.2
0x2e542  ldarg.3
0x2e543  ldarg.s  4
0x2e545  ldarg.s  5
0x2e547  call     class Microsoft.Crm.Admin.AdminService.SettingsReferenceDescriptor Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::ReadReferenceData(string referenceXml, string environmentName, string geoName, string datacenterName)
0x2e54c  stloc.0
0x2e54d  ldarg.1
0x2e54e  ldloc.0
0x2e54f  call     class Microsoft.Crm.Admin.AdminService.SettingsDiscrepancies Microsoft.Crm.Admin.AdminService.ConfigSettingsManager::VerifySettings(valuetype [mscorlib]System.Guid settingsId, class Microsoft.Crm.Admin.AdminService.SettingsReferenceDescriptor descriptor)
0x2e554  dup
0x2e555  ldarg.3
0x2e556  callvirt instance void Microsoft.Crm.Admin.AdminService.SettingsDiscrepancies::set_EnvironmentName(string value)
0x2e55b  dup
0x2e55c  ldarg.s  4
0x2e55e  callvirt instance void Microsoft.Crm.Admin.AdminService.SettingsDiscrepancies::set_GeoName(string value)
0x2e563  dup
0x2e564  ldarg.s  5
0x2e566  callvirt instance void Microsoft.Crm.Admin.AdminService.SettingsDiscrepancies::set_DatacenterName(string value)
0x2e56b  dup
0x2e56c  ldarg.s  6
0x2e56e  callvirt instance void Microsoft.Crm.Admin.AdminService.SettingsDiscrepancies::set_ScaleGroupName(string value)
0x2e573  dup
0x2e574  ldloc.0
0x2e575  callvirt instance string Microsoft.Crm.Admin.AdminService.SettingsReferenceDescriptor::get_ReferenceVersion()
0x2e57a  callvirt instance void Microsoft.Crm.Admin.AdminService.SettingsDiscrepancies::set_ReferenceVersion(string value)
0x2e57f  ret
```
