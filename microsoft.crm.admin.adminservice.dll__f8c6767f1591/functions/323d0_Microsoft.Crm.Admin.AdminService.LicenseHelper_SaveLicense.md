# Microsoft.Crm.Admin.AdminService.LicenseHelper::SaveLicense

- ea: `0x323d0`
- end: `0x32530`
- name: `Microsoft.Crm.Admin.AdminService.LicenseHelper::SaveLicense`
- size: `352`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x30c90`
- `0x30ca0`

## callees

- `0x1bd80`
- `0x2dc90`
- `0x2dfa0`
- `0x2e2e0`
- `0x2e2f0`
- `0x31c60`
- `0x31c70`
- `0x31cf0`
- `0x31d30`
- `0x32200`
- `0x323d0`
- `0x32530`
- `0x32620`
- `0x33890`

## string_xrefs

- `0x324a5`: `ConfigSettings`
- `0x324fc`: `InstallOn`
- `0x32512`: `ConfigurationDataMatrix`

## pseudocode

```c

```

## disassembly

```asm
0x323d0  ldarg.0
0x323d1  ldstr    aLicense// "license"
0x323d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x323db  ldnull
0x323dc  stloc.0
0x323dd  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::.ctor()
0x323e2  stloc.1
0x323e3  ldnull
0x323e4  stloc.2
0x323e5  ldarg.1
0x323e6  call     class Microsoft.Crm.Admin.AdminService.StoredLicenseData Microsoft.Crm.Admin.AdminService.LicenseHelper::ReadLicense(class [mscorlib]System.Version buildVersion)
0x323eb  stloc.2
0x323ec  leave.s  loc_32402
0x323ee  stloc.s  6
0x323f0  ldc.i4   0x8004D241
0x323f5  ldloc.s  6
0x323f7  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x323fc  beq.s    loc_32400
0x323fe  rethrow
0x32400  leave.s  loc_32402
0x32402  ldc.i4.1
0x32403  stloc.3
0x32404  ldloc.2
0x32405  brfalse.s loc_32464
0x32407  ldloc.2
0x32408  callvirt instance string Microsoft.Crm.Admin.AdminService.LicenseData::get_Key()
0x3240d  ldarg.0
0x3240e  callvirt instance string Microsoft.Crm.Admin.AdminService.LicenseData::get_Key()
0x32413  call     bool [mscorlib]System.String::op_Equality(string, string)
0x32418  brfalse.s loc_3241E
0x3241a  ldc.i4.0
0x3241b  stloc.3
0x3241c  br.s     loc_32471
0x3241e  ldarg.1
0x3241f  ldnull
0x32420  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x32425  brfalse.s loc_3244A
0x32427  ldarg.1
0x32428  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x3242d  ldc.i4.8
0x3242e  bne.un.s loc_3244A
0x32430  ldloc.2
0x32431  ldarg.0
0x32432  call     bool Microsoft.Crm.Admin.AdminService.V8LicenseHelper::AllowLicenseUpgrade(class Microsoft.Crm.Admin.AdminService.LicenseData licenseFrom, class Microsoft.Crm.Admin.AdminService.LicenseData licenseTo)
0x32437  brtrue.s loc_32471
0x32439  ldc.i4   0x8004D247
0x3243e  ldc.i4.0
0x3243f  newarr   [mscorlib]System.Object
0x32444  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x32449  throw
0x3244a  ldloc.2
0x3244b  ldarg.0
0x3244c  call     bool Microsoft.Crm.Admin.AdminService.LicenseHelper::AllowLicenseUpgrade(class Microsoft.Crm.Admin.AdminService.LicenseData licenseFrom, class Microsoft.Crm.Admin.AdminService.LicenseData licenseTo)
0x32451  brtrue.s loc_32471
0x32453  ldc.i4   0x8004D247
0x32458  ldc.i4.0
0x32459  newarr   [mscorlib]System.Object
0x3245e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x32463  throw
0x32464  ldarg.0
0x32465  callvirt instance bool Microsoft.Crm.Admin.AdminService.LicenseData::get_IsTrial()
0x3246a  brfalse.s loc_32471
0x3246c  call     void Microsoft.Crm.Admin.AdminService.LicenseHelper::CheckDeletedTrialLicense()
0x32471  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x32476  stloc.s  4
0x32478  ldnull
0x32479  stloc.s  5
0x3247b  ldloc.2
0x3247c  brtrue.s loc_32487
0x3247e  ldloc.s  4
0x32480  call     unsigned int8[] Microsoft.Crm.Admin.AdminService.LicenseHash::ComputeHash(valuetype [mscorlib]System.DateTime installedOn)
0x32485  stloc.s  5
0x32487  ldloc.3
0x32488  brfalse  loc_3252E
0x3248d  call     string Microsoft.Crm.Admin.AdminService.ConfigSettingsConstants::get_LicenseKeyCurrentRelease()
0x32492  stloc.s  7
0x32494  call     string Microsoft.Crm.Admin.AdminService.ConfigSettingsConstants::get_ProductIdCurrentRelease()
0x32499  stloc.s  8
0x3249b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DBMetadataCache [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::get_Cache()
0x324a0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.TableCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DBMetadataCache::get_Tables()
0x324a5  ldstr    aConfigsettings// "ConfigSettings"
0x324aa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.Table>::get_Item(void)
0x324af  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ColumnCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.Table::get_Columns()
0x324b4  call     string Microsoft.Crm.Admin.AdminService.ConfigSettingsConstants::get_LicenseKeyCurrentRelease()
0x324b9  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.Column>::ContainsKey(var<u1>)
0x324be  brtrue.s loc_324CE
0x324c0  ldstr    aLicensekeyv8rt// "LicenseKeyV8RTM"
0x324c5  stloc.s  7
0x324c7  ldstr    aProductidv8rtm// "ProductIdV8RTM"
0x324cc  stloc.s  8
0x324ce  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x324d3  stloc.0
0x324d4  ldloc.0
0x324d5  ldloc.s  7
0x324d7  ldarg.0
0x324d8  callvirt instance string Microsoft.Crm.Admin.AdminService.LicenseData::get_Key()
0x324dd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x324e2  ldloc.0
0x324e3  ldloc.s  8
0x324e5  ldarg.0
0x324e6  callvirt instance string Microsoft.Crm.Admin.AdminService.LicenseData::get_Pid()
0x324eb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x324f0  ldarg.0
0x324f1  callvirt instance bool Microsoft.Crm.Admin.AdminService.LicenseData::get_IsTrial()
0x324f6  brfalse.s loc_324FB
0x324f8  ldloc.2
0x324f9  brtrue.s loc_3251E
0x324fb  ldloc.0
0x324fc  ldstr    aInstallon// "InstallOn"
0x32501  ldloc.s  4
0x32503  box      [mscorlib]System.DateTime
0x32508  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3250d  ldloc.s  5
0x3250f  brfalse.s loc_3251E
0x32511  ldloc.0
0x32512  ldstr    aConfigurationd// "ConfigurationDataMatrix"
0x32517  ldloc.s  5
0x32519  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3251e  ldloc.1
0x3251f  ldloc.0
0x32520  callvirt instance void Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::Update(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x32525  ldarg.0
0x32526  ldloc.s  4
0x32528  newobj   instance void Microsoft.Crm.Admin.AdminService.StoredLicenseData::.ctor(class Microsoft.Crm.Admin.AdminService.LicenseData license, valuetype [mscorlib]System.DateTime installedOn)
0x3252d  stloc.2
0x3252e  ldloc.2
0x3252f  ret
```
