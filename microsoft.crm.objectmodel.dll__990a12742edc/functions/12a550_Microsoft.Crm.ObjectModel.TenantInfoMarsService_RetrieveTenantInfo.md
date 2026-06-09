# Microsoft.Crm.ObjectModel.TenantInfoMarsService::RetrieveTenantInfo

- ea: `0x12a550`
- end: `0x12a832`
- name: `Microsoft.Crm.ObjectModel.TenantInfoMarsService::RetrieveTenantInfo`
- size: `738`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x12a550`
- `0x12a8e0`
- `0x12a960`
- `0x12a990`
- `0x12aa20`

## string_xrefs

- `0x12a59f`: `D:\a\1\s\src\Core\ObjectModel\Services\Mars\TenantInfoMarsService.cs`
- `0x12a5fe`: `D:\a\1\s\src\Core\ObjectModel\Services\Mars\TenantInfoMarsService.cs`
- `0x12a738`: `D:\a\1\s\src\Core\ObjectModel\Services\Mars\TenantInfoMarsService.cs`
- `0x12a7b4`: `D:\a\1\s\src\Core\ObjectModel\Services\Mars\TenantInfoMarsService.cs`
- `0x12a7f7`: `D:\a\1\s\src\Core\ObjectModel\Services\Mars\TenantInfoMarsService.cs`
- `0x12a7df`: `select count(1) from SystemUserBase su where su.IsSyncWithDirectory = 1 and su.IsLicensed = 1`
- `0x12a81f`: `CompanySize`

## pseudocode

```c

```

## disassembly

```asm
0x12a550  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x12a555  stloc.0
0x12a556  ldsfld   string [mscorlib]System.String::Empty
0x12a55b  stloc.1
0x12a55c  ldc.i4.0
0x12a55d  stloc.2
0x12a55e  ldarg.1
0x12a55f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x12a564  stloc.3
0x12a565  ldsfld   string [mscorlib]System.String::Empty
0x12a56a  stloc.s  4
0x12a56c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::.ctor()
0x12a571  stloc.s  5
0x12a573  ldloc.s  5
0x12a575  ldstr    aSharepoint// "SharePoint"
0x12a57a  ldc.i4.0
0x12a57b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0x12a580  ldloc.s  5
0x12a582  ldstr    aExchange// "exchange"
0x12a587  ldc.i4.0
0x12a588  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0x12a58d  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x12a592  ldloc.3
0x12a593  ldstr    aType_0// "Type"
0x12a598  ldc.i4.s 0x41
0x12a59a  ldstr    aRetrievetenant// "RetrieveTenantInfo"
0x12a59f  ldstr    aDA1SSrcCoreObj_32// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0x12a5a4  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x12a5a9  unbox.any [mscorlib]System.Int32
0x12a5ae  stloc.s  6
0x12a5b0  ldloc.3
0x12a5b1  call     bool [Microsoft.Crm.Online.DirectoryData]Microsoft.Crm.Online.DirectoryData.LicenseUtilities::IsTrial(valuetype [mscorlib]System.Guid)
0x12a5b6  brtrue.s loc_12A5BB
0x12a5b8  ldc.i4.1
0x12a5b9  br.s     loc_12A5BC
0x12a5bb  ldc.i4.0
0x12a5bc  stloc.s  7
0x12a5be  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x12a5c3  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x12a5c8  ldc.i4.2
0x12a5c9  beq.s    loc_12A5D8
0x12a5cb  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x12a5d0  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x12a5d5  ldc.i4.4
0x12a5d6  bne.un.s loc_12A62C
0x12a5d8  ldarg.0
0x12a5d9  ldarg.0
0x12a5da  ldloc.3
0x12a5db  call     instance class [Microsoft.Azure.ActiveDirectory.GraphClient]Microsoft.Azure.ActiveDirectory.GraphClient.ActiveDirectoryClient Microsoft.Crm.ObjectModel.TenantInfoMarsService::GetActiveDirectoryClient(valuetype [mscorlib]System.Guid orgId)
0x12a5e0  call     instance class [Microsoft.Azure.ActiveDirectory.GraphClient]Microsoft.Azure.ActiveDirectory.GraphClient.ITenantDetail Microsoft.Crm.ObjectModel.TenantInfoMarsService::GetTenantDetail(class [Microsoft.Azure.ActiveDirectory.GraphClient]Microsoft.Azure.ActiveDirectory.GraphClient.IActiveDirectoryClient activeDirectoryClient)
0x12a5e5  stloc.s  0xD
0x12a5e7  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x12a5ec  ldarg.1
0x12a5ed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x12a5f2  ldstr    aS2stenantid// "S2STenantId"
0x12a5f7  ldc.i4.s 0x4C
0x12a5f9  ldstr    aRetrievetenant// "RetrieveTenantInfo"
0x12a5fe  ldstr    aDA1SSrcCoreObj_32// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0x12a603  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x12a608  stloc.s  0xE
0x12a60a  ldloc.s  0xE
0x12a60c  brfalse.s loc_12A616
0x12a60e  ldloc.s  0xE
0x12a610  callvirt instance string [mscorlib]System.Object::ToString()
0x12a615  stloc.1
0x12a616  ldarg.0
0x12a617  ldloc.s  0xD
0x12a619  call     instance string Microsoft.Crm.ObjectModel.TenantInfoMarsService::GetTenantName(class [Microsoft.Azure.ActiveDirectory.GraphClient]Microsoft.Azure.ActiveDirectory.GraphClient.ITenantDetail tenantDetail)
0x12a61e  stloc.s  4
0x12a620  ldarg.0
0x12a621  ldloc.s  0xD
0x12a623  ldloc.s  5
0x12a625  call     instance void Microsoft.Crm.ObjectModel.TenantInfoMarsService::CheckEnabledAssignedPlans(class [Microsoft.Azure.ActiveDirectory.GraphClient]Microsoft.Azure.ActiveDirectory.GraphClient.ITenantDetail tenantDetail, class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> plans)
0x12a62a  br.s     loc_12A641
0x12a62c  ldloca.s 0xF
0x12a62e  dup
0x12a62f  initobj  [mscorlib]System.Guid
0x12a635  constrained. [mscorlib]System.Guid
0x12a63b  callvirt instance string [mscorlib]System.Object::ToString()
0x12a640  stloc.1
0x12a641  ldloc.0
0x12a642  ldstr    aS2stenantid// "S2STenantId"
0x12a647  ldloc.1
0x12a648  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x12a64d  ldloc.0
0x12a64e  ldstr    aIsmnc// "IsMnc"
0x12a653  ldloca.s 2
0x12a655  call     instance string [mscorlib]System.Boolean::ToString()
0x12a65a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x12a65f  ldloc.0
0x12a660  ldstr    aIspaid// "IsPaid"
0x12a665  ldloca.s 7
0x12a667  call     instance string [mscorlib]System.Int32::ToString()
0x12a66c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x12a671  ldloc.0
0x12a672  ldstr    aOrgtype// "OrgType"
0x12a677  ldloca.s 6
0x12a679  call     instance string [mscorlib]System.Int32::ToString()
0x12a67e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x12a683  ldloc.0
0x12a684  ldstr    aTenantname// "TenantName"
0x12a689  ldloc.s  4
0x12a68b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x12a690  ldloc.0
0x12a691  ldstr    aSharepoint// "SharePoint"
0x12a696  ldloc.s  4
0x12a698  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12a69d  brtrue.s loc_12A6B6
0x12a69f  ldloc.s  5
0x12a6a1  ldstr    aSharepoint// "SharePoint"
0x12a6a6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::get_Item(void)
0x12a6ab  stloc.s  0x10
0x12a6ad  ldloca.s 0x10
0x12a6af  call     instance string [mscorlib]System.Boolean::ToString()
0x12a6b4  br.s     loc_12A6BB
0x12a6b6  ldstr    asc_24F76C// ""
0x12a6bb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x12a6c0  ldloc.0
0x12a6c1  ldstr    aExchange// "exchange"
0x12a6c6  ldloc.s  4
0x12a6c8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12a6cd  brtrue.s loc_12A6E6
0x12a6cf  ldloc.s  5
0x12a6d1  ldstr    aExchange// "exchange"
0x12a6d6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::get_Item(void)
0x12a6db  stloc.s  0x10
0x12a6dd  ldloca.s 0x10
0x12a6df  call     instance string [mscorlib]System.Boolean::ToString()
0x12a6e4  br.s     loc_12A6EB
0x12a6e6  ldstr    asc_24F76C// ""
0x12a6eb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x12a6f0  ldc.i4.0
0x12a6f1  stloc.s  8
0x12a6f3  ldc.i4.0
0x12a6f4  stloc.s  9
0x12a6f6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x12a6fb  stloc.s  0xA
0x12a6fd  ldloc.s  0xA
0x12a6ff  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x12a704  ldloc.3
0x12a705  box      [mscorlib]System.Guid
0x12a70a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12a70f  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x12a714  ldstr    aOrganizationli// "OrganizationLifecycle"
0x12a719  ldc.i4.2
0x12a71a  newarr   [mscorlib]System.String
0x12a71f  dup
0x12a720  ldc.i4.0
0x12a721  ldstr    aIspublicprevie// "IsPublicPreview"
0x12a726  stelem.ref
0x12a727  dup
0x12a728  ldc.i4.1
0x12a729  ldstr    aIssmbtrial// "IsSmbTrial"
0x12a72e  stelem.ref
0x12a72f  ldloc.s  0xA
0x12a731  ldc.i4.s 0x6E
0x12a733  ldstr    aRetrievetenant// "RetrieveTenantInfo"
0x12a738  ldstr    aDA1SSrcCoreObj_32// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0x12a73d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x12a742  dup
0x12a743  ldstr    aIspublicprevie// "IsPublicPreview"
0x12a748  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x12a74d  unbox.any [mscorlib]System.Boolean
0x12a752  stloc.s  8
0x12a754  ldstr    aIssmbtrial// "IsSmbTrial"
0x12a759  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x12a75e  unbox.any [mscorlib]System.Boolean
0x12a763  stloc.s  9
0x12a765  leave.s  loc_12A779
0x12a767  ldstr    aErrorInRetriev_3// "Error in retrieving OrgLc values in Ret"...
0x12a76c  ldc.i4.0
0x12a76d  newarr   [mscorlib]System.Object
0x12a772  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x12a777  leave.s  loc_12A779
0x12a779  ldloc.0
0x12a77a  ldstr    aIspublicprevie// "IsPublicPreview"
0x12a77f  ldloca.s 8
0x12a781  call     instance string [mscorlib]System.Boolean::ToString()
0x12a786  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x12a78b  ldloc.0
0x12a78c  ldstr    aIssmbtrial// "IsSmbTrial"
0x12a791  ldloca.s 9
0x12a793  call     instance string [mscorlib]System.Boolean::ToString()
0x12a798  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x12a79d  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x12a7a2  ldarg.1
0x12a7a3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x12a7a8  ldstr    aUserlicensesus// "UserLicensesUsed"
0x12a7ad  ldc.i4.s 0x7B
0x12a7af  ldstr    aRetrievetenant// "RetrieveTenantInfo"
0x12a7b4  ldstr    aDA1SSrcCoreObj_32// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0x12a7b9  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x12a7be  callvirt instance string [mscorlib]System.Object::ToString()
0x12a7c3  stloc.s  0xB
0x12a7c5  ldloc.0
0x12a7c6  ldstr    aUserlicensesus// "UserLicensesUsed"
0x12a7cb  ldloc.s  0xB
0x12a7cd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x12a7d2  ldstr    a0_2// "0"
0x12a7d7  stloc.s  0xC
0x12a7d9  ldarg.1
0x12a7da  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x12a7df  ldstr    aSelectCount1Fr_0// "select count(1) from SystemUserBase su "...
0x12a7e4  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x12a7e9  stloc.s  0x11
0x12a7eb  ldloc.s  0x11
0x12a7ed  ldc.i4   0x84
0x12a7f2  ldstr    aRetrievetenant// "RetrieveTenantInfo"
0x12a7f7  ldstr    aDA1SSrcCoreObj_32// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0x12a7fc  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x12a801  stloc.s  0x12
0x12a803  ldloc.s  0x12
0x12a805  brfalse.s loc_12A810
0x12a807  ldloc.s  0x12
0x12a809  call     string [mscorlib]System.Convert::ToString(object)
0x12a80e  stloc.s  0xC
0x12a810  leave.s  loc_12A81E
0x12a812  ldloc.s  0x11
0x12a814  brfalse.s loc_12A81D
0x12a816  ldloc.s  0x11
0x12a818  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12a81d  endfinally
0x12a81e  ldloc.0
0x12a81f  ldstr    aCompanysize// "CompanySize"
0x12a824  ldloc.s  0xC
0x12a826  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x12a82b  ldloc.0
0x12a82c  call     string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Serializers.JsonSerializer::Serialize(object)
0x12a831  ret
```
