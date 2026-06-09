# Microsoft.Crm.Admin.AdminService.TrialHelper::ReadTrial

- ea: `0x336e0`
- end: `0x33805`
- name: `Microsoft.Crm.Admin.AdminService.TrialHelper::ReadTrial`
- size: `293`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x2dc90`
- `0x2e200`
- `0x31cf0`
- `0x31d80`
- `0x33650`
- `0x336e0`
- `0x33810`
- `0x33830`
- `0x33900`

## string_xrefs

- `0x33773`: `ConfigurationDataMatrix`
- `0x3377e`: `ConfigurationDataMatrix`

## pseudocode

```c

```

## disassembly

```asm
0x336e0  ldarg.1
0x336e1  callvirt instance bool Microsoft.Crm.Admin.AdminService.LicenseData::get_IsTrial()
0x336e6  brtrue.s loc_336F8
0x336e8  ldstr    aNotATrialLicen// "Not a trial license"
0x336ed  ldc.i4   0x80040216
0x336f2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x336f7  throw
0x336f8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x336fd  stloc.s  4
0x336ff  ldloca.s 4
0x33701  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x33706  stloc.0
0x33707  ldarg.2
0x33708  brfalse.s loc_33731
0x3370a  ldarg.1
0x3370b  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Admin.AdminService.StoredLicenseData::get_InstalledOn()
0x33710  stloc.s  4
0x33712  ldloca.s 4
0x33714  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x33719  stloc.s  4
0x3371b  ldloca.s 4
0x3371d  ldc.r8   90.0
0x33726  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x3372b  stloc.0
0x3372c  br       loc_337BA
0x33731  ldarg.1
0x33732  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Admin.AdminService.StoredLicenseData::get_InstalledOn()
0x33737  stloc.s  4
0x33739  ldloca.s 4
0x3373b  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x33740  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x33745  stloc.s  4
0x33747  ldloca.s 4
0x33749  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x3374e  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x33753  brfalse.s loc_33766
0x33755  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x3375a  stloc.s  4
0x3375c  ldloca.s 4
0x3375e  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x33763  stloc.0
0x33764  br.s     loc_337BA
0x33766  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::.ctor()
0x3376b  ldc.i4.1
0x3376c  newarr   [mscorlib]System.String
0x33771  dup
0x33772  ldc.i4.0
0x33773  ldstr    aConfigurationd// "ConfigurationDataMatrix"
0x33778  stelem.ref
0x33779  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::Retrieve(string[] columns)
0x3377e  ldstr    aConfigurationd// "ConfigurationDataMatrix"
0x33783  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x33788  castclass unsigned int8[]
0x3378d  ldarg.1
0x3378e  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Admin.AdminService.StoredLicenseData::get_InstalledOn()
0x33793  call     void Microsoft.Crm.Admin.AdminService.LicenseHash::VerifyHash(unsigned int8[] hash, valuetype [mscorlib]System.DateTime installedOn)
0x33798  ldarg.1
0x33799  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Admin.AdminService.StoredLicenseData::get_InstalledOn()
0x3379e  stloc.s  4
0x337a0  ldloca.s 4
0x337a2  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x337a7  stloc.s  4
0x337a9  ldloca.s 4
0x337ab  ldc.r8   90.0
0x337b4  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x337b9  stloc.0
0x337ba  ldc.i4.0
0x337bb  stloc.1
0x337bc  ldc.i4.0
0x337bd  stloc.2
0x337be  ldloca.s 3
0x337c0  ldc.i4.0
0x337c1  conv.i8
0x337c2  call     instance void [mscorlib]System.TimeSpan::.ctor(int64)
0x337c7  ldloc.0
0x337c8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x337cd  stloc.s  4
0x337cf  ldloca.s 4
0x337d1  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x337d6  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x337db  brfalse.s loc_337E1
0x337dd  ldc.i4.1
0x337de  stloc.1
0x337df  br.s     loc_337F5
0x337e1  ldloc.0
0x337e2  call     valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Admin.AdminService.TrialHelper::GetDaysRemaining(valuetype [mscorlib]System.DateTime expireTime)
0x337e7  stloc.3
0x337e8  ldloca.s 3
0x337ea  call     instance int32 [mscorlib]System.TimeSpan::get_Days()
0x337ef  call     bool Microsoft.Crm.Admin.AdminService.TrialHelper::CheckIsWarningDay(int32 daysRemaining)
0x337f4  stloc.2
0x337f5  ldarg.1
0x337f6  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Admin.AdminService.StoredLicenseData::get_InstalledOn()
0x337fb  ldloc.0
0x337fc  ldloc.1
0x337fd  ldloc.3
0x337fe  ldloc.2
0x337ff  newobj   instance void Microsoft.Crm.Admin.AdminService.StoredTrialData::.ctor(valuetype [mscorlib]System.DateTime trialStartDate, valuetype [mscorlib]System.DateTime trialEndDate, bool isTrialPeriodExpired, valuetype [mscorlib]System.TimeSpan trialPeriodRemaining, bool isNotificationDay)
0x33804  ret
```
