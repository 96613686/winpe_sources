# Microsoft.Crm.CrmLive.Provisioning.OverwriteBaseCurrencyActionHelper::TryUpdateLocaleIdForOrganizationAndInitialUsers_0

- ea: `0x6390`
- end: `0x6457`
- name: `Microsoft.Crm.CrmLive.Provisioning.OverwriteBaseCurrencyActionHelper::TryUpdateLocaleIdForOrganizationAndInitialUsers_0`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6380`

## callees

- `0x6390`
- `0x6460`
- `0x9130`
- `0x91b0`
- `0x94c0`
- `0x1c110`

## string_xrefs

- `0x63a9`: `OverwriteBaseCurrencyAction: a preferred LocaleId was not specified - using defaults.`
- `0x63d7`: `OverwriteBaseCurrencyAction: Failed to update unsupported LocaleId to `
- `0x642c`: `OverwriteBaseCurrencyAction: Update LocaleId to `

## pseudocode

```c

```

## disassembly

```asm
0x6390  ldarg.0
0x6391  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_PreferredCulture()
0x6396  brtrue.s loc_63B4
0x6398  ldarg.0
0x6399  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x639e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x63a3  ldarg.0
0x63a4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_QueueItemId()
0x63a9  ldstr    aOverwritebasec// "OverwriteBaseCurrencyAction: a preferre"...
0x63ae  call     void Microsoft.Crm.CrmLive.Provisioning.OverwriteBaseCurrencyActionHelper::Log(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid queueItemId, string log)
0x63b3  ret
0x63b4  call     class [System]System.Collections.Generic.SortedList`2<int32, string> [Microsoft.Crm.Core.Extensions]Microsoft.Crm.LocaleValues::get_AllLocales()
0x63b9  ldarg.0
0x63ba  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_PreferredCulture()
0x63bf  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<int32, string>::ContainsKey(var<u1>)
0x63c4  brtrue.s loc_63F5
0x63c6  ldarg.0
0x63c7  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x63cc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x63d1  ldarg.0
0x63d2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_QueueItemId()
0x63d7  ldstr    aOverwritebasec_0// "OverwriteBaseCurrencyAction: Failed to "...
0x63dc  ldarg.0
0x63dd  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_PreferredCulture()
0x63e2  stloc.1
0x63e3  ldloca.s 1
0x63e5  call     instance string [mscorlib]System.Int32::ToString()
0x63ea  call     string [mscorlib]System.String::Concat(string, string)
0x63ef  call     void Microsoft.Crm.CrmLive.Provisioning.OverwriteBaseCurrencyActionHelper::Log(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid queueItemId, string log)
0x63f4  ret
0x63f5  ldarg.0
0x63f6  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_PreferredCulture()
0x63fb  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x6400  stloc.0
0x6401  ldarg.1
0x6402  ldarg.0
0x6403  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x6408  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x640d  ldloc.0
0x640e  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x6413  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::UpdateOrganizationRegionSettings(valuetype [mscorlib]System.Guid organizationId, int32 lcid)
0x6418  leave.s  loc_6456
0x641a  stloc.2
0x641b  ldarg.0
0x641c  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x6421  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x6426  ldarg.0
0x6427  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_QueueItemId()
0x642c  ldstr    aOverwritebasec_1// "OverwriteBaseCurrencyAction: Update Loc"...
0x6431  ldarg.0
0x6432  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_PreferredCulture()
0x6437  stloc.1
0x6438  ldloca.s 1
0x643a  call     instance string [mscorlib]System.Int32::ToString()
0x643f  ldstr    aFailedWithExce// " failed with exception "
0x6444  ldloc.2
0x6445  callvirt instance string [mscorlib]System.Object::ToString()
0x644a  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x644f  call     void Microsoft.Crm.CrmLive.Provisioning.OverwriteBaseCurrencyActionHelper::Log(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid queueItemId, string log)
0x6454  leave.s  loc_6456
0x6456  ret
```
