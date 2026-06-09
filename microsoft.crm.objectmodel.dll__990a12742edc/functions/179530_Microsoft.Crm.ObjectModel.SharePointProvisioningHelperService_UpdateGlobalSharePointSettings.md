# Microsoft.Crm.ObjectModel.SharePointProvisioningHelperService::UpdateGlobalSharePointSettings

- ea: `0x179530`
- end: `0x1796c5`
- name: `Microsoft.Crm.ObjectModel.SharePointProvisioningHelperService::UpdateGlobalSharePointSettings`
- size: `405`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x6d5c0`
- `0x179530`
- `0x179810`
- `0x17c910`
- `0x18a640`
- `0x18a780`

## string_xrefs

- `0x179566`: `D:\a\1\s\src\Core\ObjectModel\Services\SharePoint\SharepointProvisioningHelperService.cs`
- `0x179561`: `UpdateGlobalSharePointSettings`
- `0x17959f`: `UpdateGlobalSharePointSettings`
- `0x179605`: `UpdateGlobalSharePointSettings`
- `0x17965e`: `UpdateGlobalSharePointSettings`
- `0x17964b`: `This ACS configuration is not supported`
- `0x179668`: `This ACS configuration is not supported`
- `0x179682`: `prvConfigureSharePoint`

## pseudocode

```c

```

## disassembly

```asm
0x179530  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x179535  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x17953a  ldc.i4.2
0x17953b  bne.un   loc_1795DD
0x179540  ldarg.1
0x179541  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x179546  brfalse  loc_1795DD
0x17954b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x179550  ldarg.s  4
0x179552  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x179557  ldstr    aS2stenantid// "S2STenantId"
0x17955c  ldc.i4   0x27F
0x179561  ldstr    aUpdateglobalsh// "UpdateGlobalSharePointSettings"
0x179566  ldstr    aDA1SSrcCoreObj_46// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0x17956b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x179570  stloc.0
0x179571  ldarg.s  4
0x179573  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x179578  ldc.i4.s 0x11
0x17957a  ldstr    aS2stenantidIs// "S2STenantId is "
0x17957f  ldloc.0
0x179580  brfalse.s loc_17958A
0x179582  ldloc.0
0x179583  callvirt instance string [mscorlib]System.Object::ToString()
0x179588  br.s     loc_17958F
0x17958a  ldstr    aNull_0// "NULL"
0x17958f  call     string [mscorlib]System.String::Concat(string, string)
0x179594  ldc.i4.0
0x179595  newarr   [mscorlib]System.Object
0x17959a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x17959f  ldstr    aUpdateglobalsh// "UpdateGlobalSharePointSettings"
0x1795a4  ldarg.s  4
0x1795a6  ldstr    aS2stenantid// "S2STenantId"
0x1795ab  ldloc.0
0x1795ac  brfalse.s loc_1795B6
0x1795ae  ldloc.0
0x1795af  callvirt instance string [mscorlib]System.Object::ToString()
0x1795b4  br.s     loc_1795BB
0x1795b6  ldstr    aNull_0// "NULL"
0x1795bb  call     void Microsoft.Crm.ObjectModel.SharePointTelemetryHelper::LogInformation(string EventName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string EventParamsKey, string EventParamsValue)
0x1795c0  ldloc.0
0x1795c1  brfalse.s loc_1795DD
0x1795c3  ldloc.0
0x1795c4  unbox.any [mscorlib]System.Guid
0x1795c9  stloc.1
0x1795ca  ldloca.s 1
0x1795cc  ldstr    aD// "D"
0x1795d1  call     instance string [mscorlib]System.Guid::ToString(string)
0x1795d6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1795db  starg.s  1
0x1795dd  ldarg.2
0x1795de  brtrue.s loc_17961B
0x1795e0  ldarg.1
0x1795e1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1795e6  brfalse.s loc_17961B
0x1795e8  ldnull
0x1795e9  ldarg.s  4
0x1795eb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1795f0  ldc.i4.s 0x11
0x1795f2  ldstr    aExceptionOccur_12// "Exception occured as Sharepoint Realm i"...
0x1795f7  ldc.i4.0
0x1795f8  newarr   [mscorlib]System.Object
0x1795fd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x179602  ldc.i4.3
0x179603  ldarg.s  4
0x179605  ldstr    aUpdateglobalsh// "UpdateGlobalSharePointSettings"
0x17960a  ldc.i4   0x80040203
0x17960f  ldstr    aPleaseInsertAV// "Please insert a valid Sharepoint Realm "...
0x179614  ldnull
0x179615  call     class [mscorlib]System.Exception Microsoft.Crm.ObjectModel.SharePointErrorHandler::LogTelemetryAndThrowException(valuetype ErrorTelemetryEventType errorEventType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string callingMethod, int32 crmErrorCode, string exceptionMessage, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x17961a  throw
0x17961b  ldarg.3
0x17961c  brfalse.s loc_17962E
0x17961e  ldarg.2
0x17961f  brtrue.s loc_17962E
0x179621  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x179626  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x17962b  ldc.i4.2
0x17962c  bne.un.s loc_179641
0x17962e  ldarg.3
0x17962f  brtrue.s loc_179674
0x179631  ldarg.2
0x179632  brtrue.s loc_179641
0x179634  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x179639  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x17963e  ldc.i4.2
0x17963f  bne.un.s loc_179674
0x179641  ldnull
0x179642  ldarg.s  4
0x179644  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x179649  ldc.i4.s 0x11
0x17964b  ldstr    aThisAcsConfigu// "This ACS configuration is not supported"
0x179650  ldc.i4.0
0x179651  newarr   [mscorlib]System.Object
0x179656  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x17965b  ldc.i4.3
0x17965c  ldarg.s  4
0x17965e  ldstr    aUpdateglobalsh// "UpdateGlobalSharePointSettings"
0x179663  ldc.i4   0x80040203
0x179668  ldstr    aThisAcsConfigu// "This ACS configuration is not supported"
0x17966d  ldnull
0x17966e  call     class [mscorlib]System.Exception Microsoft.Crm.ObjectModel.SharePointErrorHandler::LogTelemetryAndThrowException(valuetype ErrorTelemetryEventType errorEventType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string callingMethod, int32 crmErrorCode, string exceptionMessage, [opt] class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException ex)
0x179673  throw
0x179674  ldarg.s  4
0x179676  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x17967b  ldarg.s  4
0x17967d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x179682  ldstr    aPrvconfiguresh// "prvConfigureSharePoint"
0x179687  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0x17968c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x179691  ldarg.s  4
0x179693  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x179698  ldarg.s  4
0x17969a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x17969f  stloc.2
0x1796a0  ldarg.0
0x1796a1  ldarg.2
0x1796a2  ldarg.s  4
0x1796a4  call     instance void Microsoft.Crm.ObjectModel.SharePointProvisioningHelperService::ChangeOrgSetting(bool isSharePointOnline, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1796a9  newobj   instance void Microsoft.Crm.ObjectModel.SharePointMigrationHelper::.ctor()
0x1796ae  ldarg.2
0x1796af  ldarg.3
0x1796b0  ldarg.1
0x1796b1  ldarg.s  4
0x1796b3  callvirt instance void Microsoft.Crm.ObjectModel.SharePointMigrationHelper::ProvisionS2S(bool isSharePointOnline, bool useAuthorizationServer, string sharePointRealm, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1796b8  leave.s  loc_1796C4
0x1796ba  ldloc.2
0x1796bb  brfalse.s loc_1796C3
0x1796bd  ldloc.2
0x1796be  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1796c3  endfinally
0x1796c4  ret
```
