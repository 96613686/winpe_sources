# Microsoft.Crm.Admin.AdminService.LicenseHelper::ExtendTrialLicense

- ea: `0x325a0`
- end: `0x32614`
- name: `Microsoft.Crm.Admin.AdminService.LicenseHelper::ExtendTrialLicense`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x2dc90`
- `0x2dfa0`
- `0x31cf0`
- `0x321f0`
- `0x325a0`
- `0x33890`

## string_xrefs

- `0x325ea`: `InstallOn`
- `0x32600`: `ConfigurationDataMatrix`

## pseudocode

```c

```

## disassembly

```asm
0x325a0  ldnull
0x325a1  stloc.0
0x325a2  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::.ctor()
0x325a7  stloc.1
0x325a8  ldnull
0x325a9  stloc.2
0x325aa  ldarg.0
0x325ab  call     instance class Microsoft.Crm.Admin.AdminService.StoredLicenseData Microsoft.Crm.Admin.AdminService.LicenseHelper::ReadLicense()
0x325b0  stloc.2
0x325b1  leave.s  loc_325C5
0x325b3  stloc.3
0x325b4  ldc.i4   0x8004D241
0x325b9  ldloc.3
0x325ba  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x325bf  beq.s    loc_325C3
0x325c1  rethrow
0x325c3  leave.s  loc_325C5
0x325c5  ldloc.2
0x325c6  brfalse.s loc_32613
0x325c8  ldloc.2
0x325c9  callvirt instance bool Microsoft.Crm.Admin.AdminService.LicenseData::get_IsTrial()
0x325ce  brfalse.s loc_32613
0x325d0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x325d5  stloc.s  4
0x325d7  ldnull
0x325d8  stloc.s  5
0x325da  ldloc.s  4
0x325dc  call     unsigned int8[] Microsoft.Crm.Admin.AdminService.LicenseHash::ComputeHash(valuetype [mscorlib]System.DateTime installedOn)
0x325e1  stloc.s  5
0x325e3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x325e8  stloc.0
0x325e9  ldloc.0
0x325ea  ldstr    aInstallon// "InstallOn"
0x325ef  ldloc.s  4
0x325f1  box      [mscorlib]System.DateTime
0x325f6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x325fb  ldloc.s  5
0x325fd  brfalse.s loc_3260C
0x325ff  ldloc.0
0x32600  ldstr    aConfigurationd// "ConfigurationDataMatrix"
0x32605  ldloc.s  5
0x32607  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3260c  ldloc.1
0x3260d  ldloc.0
0x3260e  callvirt instance void Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::Update(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x32613  ret
```
