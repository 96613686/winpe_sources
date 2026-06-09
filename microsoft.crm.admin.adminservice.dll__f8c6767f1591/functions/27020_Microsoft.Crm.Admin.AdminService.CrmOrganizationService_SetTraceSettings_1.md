# Microsoft.Crm.Admin.AdminService.CrmOrganizationService::SetTraceSettings_1

- ea: `0x27020`
- end: `0x27194`
- name: `Microsoft.Crm.Admin.AdminService.CrmOrganizationService::SetTraceSettings_1`
- size: `372`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x26ff0`
- `0x27010`

## callees

- `0x260a0`
- `0x27020`
- `0x28560`
- `0x285c0`
- `0x29340`
- `0x29390`
- `0x293e0`
- `0x29430`

## string_xrefs

- `0x270f7`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`
- `0x27177`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x27020  newobj   instance void Microsoft.Crm.Admin.AdminService.OrganizationData::.ctor()
0x27025  stloc.0
0x27026  ldloc.0
0x27027  ldarg.1
0x27028  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationData::set_Id(valuetype [mscorlib]System.Guid value)
0x2702d  ldarg.s  4
0x2702f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x27034  brtrue.s loc_2703E
0x27036  ldloc.0
0x27037  ldarg.s  4
0x27039  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationData::set_TraceCategories(string value)
0x2703e  ldarga.s 2
0x27040  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x27045  brfalse.s loc_27054
0x27047  ldloc.0
0x27048  ldarga.s 2
0x2704a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2704f  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationData::set_TraceEnabled(bool value)
0x27054  ldarg.3
0x27055  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2705a  brtrue.s loc_27063
0x2705c  ldloc.0
0x2705d  ldarg.3
0x2705e  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationData::set_TraceScenario(string value)
0x27063  ldarg.s  6
0x27065  brfalse.s loc_27071
0x27067  ldloc.0
0x27068  ldarg.s  5
0x2706a  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationData::set_TraceExpiration(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0x2706f  br.s     loc_270AC
0x27071  ldarga.s 2
0x27073  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x27078  brfalse.s loc_270AC
0x2707a  ldarga.s 2
0x2707c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x27081  brfalse.s loc_270AC
0x27083  ldloc.0
0x27084  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x27089  stloc.1
0x2708a  ldloca.s 1
0x2708c  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x27091  ldstr    aDefaultorganiz_0// "DefaultOrganizationTraceDuration"
0x27096  ldc.i4.0
0x27097  callvirt T0x2B000020
0x2709c  conv.r8
0x2709d  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x270a2  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x270a7  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationData::set_TraceExpiration(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0x270ac  ldarg.0
0x270ad  ldloc.0
0x270ae  call     instance void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::UpdateWithoutCheckStatus(class Microsoft.Crm.Admin.AdminService.OrganizationData organizationData)
0x270b3  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x270b8  stloc.2
0x270b9  ldloc.2
0x270ba  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x270bf  ldarg.1
0x270c0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetOrganizationLocalDatacenterId(valuetype [mscorlib]System.Guid)
0x270c5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::set_DatacenterId(valuetype [mscorlib]System.Guid)
0x270ca  ldloc.2
0x270cb  ldstr    aServersettings// "ServerSettings"
0x270d0  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x270d5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider::GetSiteSettingId()
0x270da  box      [mscorlib]System.Guid
0x270df  ldc.i4.1
0x270e0  newarr   [mscorlib]System.String
0x270e5  dup
0x270e6  ldc.i4.0
0x270e7  ldstr    aTracerefresh// "TraceRefresh"
0x270ec  stelem.ref
0x270ed  ldc.i4   0x3B0
0x270f2  ldstr    aSettracesettin// "SetTraceSettings"
0x270f7  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x270fc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x27101  stloc.3
0x27102  ldloc.3
0x27103  brfalse.s loc_27182
0x27105  ldloc.3
0x27106  ldstr    aTracerefresh// "TraceRefresh"
0x2710b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x27110  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0x27115  stloc.s  4
0x27117  ldloca.s 4
0x27119  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x2711e  brfalse.s loc_27182
0x27120  ldloca.s 4
0x27122  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x27127  ldc.i4   0x80000000
0x2712c  beq.s    loc_27139
0x2712e  ldloca.s 4
0x27130  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x27135  ldc.i4.1
0x27136  sub
0x27137  br.s     loc_2713A
0x27139  ldc.i4.m1
0x2713a  stloc.s  5
0x2713c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x27141  stloc.s  6
0x27143  ldloc.s  6
0x27145  ldstr    aTracerefresh// "TraceRefresh"
0x2714a  ldloc.s  5
0x2714c  box      [mscorlib]System.Int32
0x27151  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x27156  ldloc.2
0x27157  ldstr    aServersettings// "ServerSettings"
0x2715c  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x27161  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider::GetSiteSettingId()
0x27166  box      [mscorlib]System.Guid
0x2716b  ldloc.s  6
0x2716d  ldc.i4   0x3B9
0x27172  ldstr    aSettracesettin// "SetTraceSettings"
0x27177  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2717c  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x27181  pop
0x27182  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::LocatorServiceUpdated()
0x27187  leave.s  loc_27193
0x27189  ldloc.2
0x2718a  brfalse.s loc_27192
0x2718c  ldloc.2
0x2718d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27192  endfinally
0x27193  ret
```
