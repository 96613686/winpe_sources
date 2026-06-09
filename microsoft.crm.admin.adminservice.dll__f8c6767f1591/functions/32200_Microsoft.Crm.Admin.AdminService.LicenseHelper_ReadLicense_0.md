# Microsoft.Crm.Admin.AdminService.LicenseHelper::ReadLicense_0

- ea: `0x32200`
- end: `0x323c4`
- name: `Microsoft.Crm.Admin.AdminService.LicenseHelper::ReadLicense_0`
- size: `452`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x321f0`
- `0x323d0`

## callees

- `0x2dc90`
- `0x2e200`
- `0x2e2e0`
- `0x2e2f0`
- `0x31af0`
- `0x31d30`
- `0x31e30`
- `0x31e50`
- `0x32150`
- `0x32200`
- `0x32930`
- `0x32940`
- `0x331e0`

## string_xrefs

- `0x32237`: `ConfigSettings`
- `0x3229c`: `InstallOn`
- `0x322bb`: `InstallOn`
- `0x32301`: `InstallOn`
- `0x3230e`: `InstallOn`

## pseudocode

```c

```

## disassembly

```asm
0x32200  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::.ctor()
0x32205  stloc.0
0x32206  call     string Microsoft.Crm.Admin.AdminService.ConfigSettingsConstants::get_LicenseKeyCurrentRelease()
0x3220b  stloc.1
0x3220c  call     string Microsoft.Crm.Admin.AdminService.ConfigSettingsConstants::get_ProductIdCurrentRelease()
0x32211  stloc.2
0x32212  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x32217  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetSku()
0x3221c  ldc.i4.2
0x3221d  bne.un.s loc_3222D
0x3221f  ldstr    aLicensekeyv8rt// "LicenseKeyV8RTM"
0x32224  stloc.1
0x32225  ldstr    aProductidv8rtm// "ProductIdV8RTM"
0x3222a  stloc.2
0x3222b  br.s     loc_3228B
0x3222d  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DBMetadataCache [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::get_Cache()
0x32232  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.TableCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DBMetadataCache::get_Tables()
0x32237  ldstr    aConfigsettings// "ConfigSettings"
0x3223c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.Table>::get_Item(void)
0x32241  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ColumnCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.Table::get_Columns()
0x32246  ldloc.1
0x32247  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.Column>::ContainsKey(var<u1>)
0x3224c  brtrue.s loc_3225C
0x3224e  ldstr    aLicensekeyv8rt// "LicenseKeyV8RTM"
0x32253  stloc.1
0x32254  ldstr    aProductidv8rtm// "ProductIdV8RTM"
0x32259  stloc.2
0x3225a  br.s     loc_3228B
0x3225c  ldarg.0
0x3225d  ldnull
0x3225e  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x32263  brfalse.s loc_3228B
0x32265  ldarg.0
0x32266  call     class [mscorlib]System.Version Microsoft.Crm.Admin.AdminService.LicenseDataConstants::get_V8Version()
0x3226b  call     bool [mscorlib]System.Version::op_GreaterThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x32270  brfalse.s loc_3228B
0x32272  ldarg.0
0x32273  call     class [mscorlib]System.Version Microsoft.Crm.Admin.AdminService.LicenseDataConstants::get_V9Version()
0x32278  call     bool [mscorlib]System.Version::op_LessThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x3227d  brfalse.s loc_3228B
0x3227f  ldstr    aLicensekeyv8rt// "LicenseKeyV8RTM"
0x32284  stloc.1
0x32285  ldstr    aProductidv8rtm// "ProductIdV8RTM"
0x3228a  stloc.2
0x3228b  ldloc.0
0x3228c  ldc.i4.3
0x3228d  newarr   [mscorlib]System.String
0x32292  dup
0x32293  ldc.i4.0
0x32294  ldloc.1
0x32295  stelem.ref
0x32296  dup
0x32297  ldc.i4.1
0x32298  ldloc.2
0x32299  stelem.ref
0x3229a  dup
0x3229b  ldc.i4.2
0x3229c  ldstr    aInstallon// "InstallOn"
0x322a1  stelem.ref
0x322a2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::Retrieve(string[] columns)
0x322a7  stloc.3
0x322a8  ldloc.3
0x322a9  ldloc.1
0x322aa  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x322af  stloc.s  4
0x322b1  ldloc.3
0x322b2  ldloc.2
0x322b3  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x322b8  stloc.s  5
0x322ba  ldloc.3
0x322bb  ldstr    aInstallon// "InstallOn"
0x322c0  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x322c5  stloc.s  6
0x322c7  ldloc.s  4
0x322c9  brfalse.s loc_322D2
0x322cb  ldloc.s  5
0x322cd  brtrue   loc_32370
0x322d2  ldloc.1
0x322d3  call     string Microsoft.Crm.Admin.AdminService.ConfigSettingsConstants::get_LicenseKeyCurrentRelease()
0x322d8  ldc.i4.5
0x322d9  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x322de  brfalse.s loc_3235F
0x322e0  ldloc.0
0x322e1  ldc.i4.4
0x322e2  newarr   [mscorlib]System.String
0x322e7  dup
0x322e8  ldc.i4.0
0x322e9  ldstr    aLicensekeyv9be// "LicenseKeyV9Beta"
0x322ee  stelem.ref
0x322ef  dup
0x322f0  ldc.i4.1
0x322f1  ldstr    aLicensekeyv8rt// "LicenseKeyV8RTM"
0x322f6  stelem.ref
0x322f7  dup
0x322f8  ldc.i4.2
0x322f9  ldstr    aProductidv8rtm// "ProductIdV8RTM"
0x322fe  stelem.ref
0x322ff  dup
0x32300  ldc.i4.3
0x32301  ldstr    aInstallon// "InstallOn"
0x32306  stelem.ref
0x32307  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::Retrieve(string[] columns)
0x3230c  stloc.3
0x3230d  ldloc.3
0x3230e  ldstr    aInstallon// "InstallOn"
0x32313  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x32318  stloc.s  6
0x3231a  ldloc.3
0x3231b  ldstr    aLicensekeyv9be// "LicenseKeyV9Beta"
0x32320  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x32325  castclass [mscorlib]System.String
0x3232a  call     class Microsoft.Crm.Admin.AdminService.LicenseData Microsoft.Crm.Admin.AdminService.BackCompatLicenseData::GetLicenseFromPreviousKey(string productKey)
0x3232f  stloc.s  0xB
0x32331  ldloc.s  0xB
0x32333  brtrue.s loc_3234C
0x32335  ldloc.3
0x32336  ldstr    aLicensekeyv8rt// "LicenseKeyV8RTM"
0x3233b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x32340  castclass [mscorlib]System.String
0x32345  call     class Microsoft.Crm.Admin.AdminService.LicenseData Microsoft.Crm.Admin.AdminService.BackCompatLicenseData::GetLicenseFromPreviousKey(string productKey)
0x3234a  stloc.s  0xB
0x3234c  ldloc.s  0xB
0x3234e  brfalse.s loc_3235F
0x32350  ldloc.s  0xB
0x32352  ldloc.s  6
0x32354  unbox.any [mscorlib]System.DateTime
0x32359  newobj   instance void Microsoft.Crm.Admin.AdminService.StoredLicenseData::.ctor(class Microsoft.Crm.Admin.AdminService.LicenseData license, valuetype [mscorlib]System.DateTime installedOn)
0x3235e  ret
0x3235f  ldc.i4   0x8004D241
0x32364  ldc.i4.0
0x32365  newarr   [mscorlib]System.Object
0x3236a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x3236f  throw
0x32370  ldloc.s  4
0x32372  castclass [mscorlib]System.String
0x32377  stloc.s  7
0x32379  ldloc.s  5
0x3237b  castclass [mscorlib]System.String
0x32380  stloc.s  8
0x32382  ldloc.s  6
0x32384  unbox.any [mscorlib]System.DateTime
0x32389  stloc.s  9
0x3238b  ldloc.1
0x3238c  ldstr    aLicensekeyv8rt// "LicenseKeyV8RTM"
0x32391  callvirt instance bool [mscorlib]System.String::Equals(string)
0x32396  brfalse.s loc_323A3
0x32398  ldloc.s  7
0x3239a  call     class Microsoft.Crm.Admin.AdminService.PIDGenResult Microsoft.Crm.Admin.AdminService.PidGenUtility::ValidateProductKeyV8(string sKey)
0x3239f  stloc.s  0xA
0x323a1  br.s     loc_323AC
0x323a3  ldloc.s  7
0x323a5  call     class Microsoft.Crm.Admin.AdminService.PIDGenResult Microsoft.Crm.Admin.AdminService.PidGenUtility::ValidateProductKeyV9(string sKey)
0x323aa  stloc.s  0xA
0x323ac  ldloc.s  7
0x323ae  ldloc.s  8
0x323b0  ldloc.s  0xA
0x323b2  callvirt instance unsigned int64 Microsoft.Crm.Admin.AdminService.PIDGenResult::get_SequenceNumber()
0x323b7  call     class Microsoft.Crm.Admin.AdminService.LicenseData Microsoft.Crm.Admin.AdminService.LicenseHelper::ComputeLicense(string licenseKey, string pid, unsigned int64 sequenceNumber)
0x323bc  ldloc.s  9
0x323be  newobj   instance void Microsoft.Crm.Admin.AdminService.StoredLicenseData::.ctor(class Microsoft.Crm.Admin.AdminService.LicenseData license, valuetype [mscorlib]System.DateTime installedOn)
0x323c3  ret
```
