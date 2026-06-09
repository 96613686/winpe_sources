# Microsoft.Crm.Common.Yammer.YammerState::Read

- ea: `0x480`
- end: `0x5e2`
- name: `Microsoft.Crm.Common.Yammer.YammerState::Read`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x5f0`

## callees

- `0x350`
- `0x360`
- `0x370`
- `0x380`
- `0x390`
- `0x3b0`
- `0x3d0`
- `0x3f0`
- `0x410`
- `0x430`
- `0x450`
- `0x470`
- `0x480`
- `0x630`

## string_xrefs

- `0x4f8`: `d:\dbs\sh\dccm2\1101_190851\cmd\42\src\Common\Application\WebPlatform\Utility\YammerState.cs`

## pseudocode

```c

```

## disassembly

```asm
0x480  newobj   instance void Microsoft.Crm.Common.Yammer.YammerState::.ctor()
0x485  stloc.0
0x486  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x48b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x490  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_YammerPosts()
0x495  ldarg.0
0x496  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x49b  ldnull
0x49c  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x4a1  brtrue.s loc_4A5
0x4a3  ldloc.0
0x4a4  ret
0x4a5  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x4aa  brfalse.s loc_4C3
0x4ac  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x4b1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x4b6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_RefreshFall()
0x4bb  ldarg.0
0x4bc  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4c1  brtrue.s loc_4C5
0x4c3  ldloc.0
0x4c4  ret
0x4c5  ldarg.0
0x4c6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x4cb  stloc.1
0x4cc  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x4d1  ldstr    aExternalkey// "ExternalKey"
0x4d6  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.ExternalKeyConstants::YammerApplication
0x4db  box      [mscorlib]System.Guid
0x4e0  ldc.i4.1
0x4e1  newarr   [mscorlib]System.String
0x4e6  dup
0x4e7  ldc.i4.0
0x4e8  ldstr    aApplicationid// "ApplicationId"
0x4ed  stelem.ref
0x4ee  ldc.i4   0xD4
0x4f3  ldstr    aRead// "Read"
0x4f8  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x4fd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveById(string, object, string[], int32, string, string)
0x502  stloc.2
0x503  ldloc.2
0x504  brtrue.s loc_508
0x506  ldloc.0
0x507  ret
0x508  ldloc.0
0x509  ldloc.2
0x50a  ldstr    aApplicationid// "ApplicationId"
0x50f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x514  castclass [mscorlib]System.String
0x519  callvirt instance void Microsoft.Crm.Common.Yammer.YammerState::set_YammerAppId(string value)
0x51e  ldloc.0
0x51f  ldarg.0
0x520  call     bool Microsoft.Crm.Common.Yammer.YammerState::IsYammerEnabledActivityFeedsSolutionInstalled(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation currentUser)
0x525  callvirt instance void Microsoft.Crm.Common.Yammer.YammerState::set_IsYammerFeatureAvailable(bool value)
0x52a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x52f  ldloc.1
0x530  ldarg.0
0x531  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x536  stloc.3
0x537  ldloc.1
0x538  call     class [mscorlib]System.Security.SecureString [Microsoft.Crm.Yammer]Microsoft.Crm.Yammer.YammerServiceUtility::GetYammerOAuthAccessToken(valuetype [mscorlib]System.Guid)
0x53d  stloc.s  5
0x53f  ldloc.0
0x540  ldloc.s  5
0x542  brfalse.s loc_559
0x544  ldloc.3
0x545  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_YammerNetworkName()
0x54a  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x54f  brtrue.s loc_559
0x551  ldloc.0
0x552  callvirt instance bool Microsoft.Crm.Common.Yammer.YammerState::get_IsYammerFeatureAvailable()
0x557  br.s     loc_55A
0x559  ldc.i4.0
0x55a  callvirt instance void Microsoft.Crm.Common.Yammer.YammerState::set_IsYammerConfiguredForOrg(bool value)
0x55f  leave.s  loc_56D
0x561  ldloc.s  5
0x563  brfalse.s loc_56C
0x565  ldloc.s  5
0x567  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x56c  endfinally
0x56d  ldloc.0
0x56e  ldloc.0
0x56f  callvirt instance bool Microsoft.Crm.Common.Yammer.YammerState::get_IsYammerConfiguredForOrg()
0x574  brfalse.s loc_57E
0x576  ldloc.3
0x577  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_YammerOAuthAccessTokenExpired()
0x57c  br.s     loc_57F
0x57e  ldc.i4.0
0x57f  callvirt instance void Microsoft.Crm.Common.Yammer.YammerState::set_IsYammerOAuthTokenExpired(bool value)
0x584  ldloc.0
0x585  ldloc.3
0x586  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_YammerNetworkName()
0x58b  callvirt instance void Microsoft.Crm.Common.Yammer.YammerState::set_YammerNetworkName(string value)
0x590  ldloc.0
0x591  ldloc.3
0x592  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_YammerGroupId()
0x597  conv.i8
0x598  callvirt instance void Microsoft.Crm.Common.Yammer.YammerState::set_YammerGroupId(int64 value)
0x59d  ldloc.0
0x59e  ldloc.3
0x59f  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.Sdk.Caching.CacheData.YammerPostMethod [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_YammerPostMethod()
0x5a4  callvirt instance void Microsoft.Crm.Common.Yammer.YammerState::set_YammerPostMethod(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.Sdk.Caching.CacheData.YammerPostMethod value)
0x5a9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x5ae  ldarg.0
0x5af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x5b4  ldarg.0
0x5b5  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x5ba  stloc.s  4
0x5bc  ldloc.0
0x5bd  ldloc.s  4
0x5bf  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_IsYammerConfigured()
0x5c4  callvirt instance void Microsoft.Crm.Common.Yammer.YammerState::set_IsYammerConfiguredForUser(bool value)
0x5c9  ldloc.0
0x5ca  ldstr    a79c8bb808c984b// "{79C8BB80-8C98-4B4B-907E-B82CC1F1EE6E}"
0x5cf  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5d4  ldc.i4.3
0x5d5  ldarg.0
0x5d6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5db  callvirt instance void Microsoft.Crm.Common.Yammer.YammerState::set_CanConfigureYammer(bool value)
0x5e0  ldloc.0
0x5e1  ret
```
