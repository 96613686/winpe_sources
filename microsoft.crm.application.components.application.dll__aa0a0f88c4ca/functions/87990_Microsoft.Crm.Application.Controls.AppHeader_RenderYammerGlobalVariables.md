# Microsoft.Crm.Application.Controls.AppHeader::RenderYammerGlobalVariables

- ea: `0x87990`
- end: `0x87ad1`
- name: `Microsoft.Crm.Application.Controls.AppHeader::RenderYammerGlobalVariables`
- size: `321`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x87990`

## string_xrefs

- `0x87a85`: `CRMWRPCToken`
- `0x8799c`: `YAMMER_IS_INSTALLED`
- `0x879ad`: `YAMMER_IS_CONFIGURED_FOR_ORG`
- `0x879f1`: `YAMMER_TOKEN_EXPIRED`
- `0x87a02`: `YAMMER_IS_CONFIGURED_FOR_USER`
- `0x87a13`: `YAMMER_HAS_CONFIGURE_PRIVILEGE`
- `0x87a7a`: `YAMMER_YAMMEREMBED_WRPCTOKEN`
- `0x87ab1`: `YAMMER_YAMMEREMBED_WRPCTOKEN`
- `0x87aa0`: `CRMWRPCTokenTimeStamp`

## pseudocode

```c

```

## disassembly

```asm
0x87990  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x87995  call     class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.YammerState::Read(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation)
0x8799a  stloc.0
0x8799b  ldarg.0
0x8799c  ldstr    aYammerIsInstal// "YAMMER_IS_INSTALLED"
0x879a1  ldloc.0
0x879a2  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_IsYammerFeatureAvailable()
0x879a7  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x879ac  ldarg.0
0x879ad  ldstr    aYammerIsConfig// "YAMMER_IS_CONFIGURED_FOR_ORG"
0x879b2  ldloc.0
0x879b3  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_IsYammerConfiguredForOrg()
0x879b8  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x879bd  ldarg.0
0x879be  ldstr    aYammerAppId// "YAMMER_APP_ID"
0x879c3  ldloc.0
0x879c4  callvirt instance string [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_YammerAppId()
0x879c9  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x879ce  ldarg.0
0x879cf  ldstr    aYammerNetworkN// "YAMMER_NETWORK_NAME"
0x879d4  ldloc.0
0x879d5  callvirt instance string [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_YammerNetworkName()
0x879da  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x879df  ldarg.0
0x879e0  ldstr    aYammerGroupId// "YAMMER_GROUP_ID"
0x879e5  ldloc.0
0x879e6  callvirt instance int64 [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_YammerGroupId()
0x879eb  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x879f0  ldarg.0
0x879f1  ldstr    aYammerTokenExp// "YAMMER_TOKEN_EXPIRED"
0x879f6  ldloc.0
0x879f7  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_IsYammerOAuthTokenExpired()
0x879fc  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x87a01  ldarg.0
0x87a02  ldstr    aYammerIsConfig_0// "YAMMER_IS_CONFIGURED_FOR_USER"
0x87a07  ldloc.0
0x87a08  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_IsYammerConfiguredForUser()
0x87a0d  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x87a12  ldarg.0
0x87a13  ldstr    aYammerHasConfi// "YAMMER_HAS_CONFIGURE_PRIVILEGE"
0x87a18  ldloc.0
0x87a19  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_CanConfigureYammer()
0x87a1e  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x87a23  ldarg.0
0x87a24  ldstr    aYammerPostMeth// "YAMMER_POST_METHOD"
0x87a29  ldloc.0
0x87a2a  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.Sdk.Caching.CacheData.YammerPostMethod [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_YammerPostMethod()
0x87a2f  conv.i8
0x87a30  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x87a35  ldloc.0
0x87a36  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_IsYammerFeatureAvailable()
0x87a3b  brfalse  loc_87AD0
0x87a40  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext::.ctor()
0x87a45  ldstr    aToolsYammerYam// "/tools/yammer/yammerembed.aspx"
0x87a4a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x87a4f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x87a54  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext::GetWrpcTokenAsQueryString(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x87a59  stloc.1
0x87a5a  ldloc.1
0x87a5b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x87a60  brtrue.s loc_87AB0
0x87a62  ldstr    asc_F537C// ""
0x87a67  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x87a6c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x87a71  stloc.2
0x87a72  ldloc.2
0x87a73  ldloc.1
0x87a74  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::AppendToQuery(string)
0x87a79  ldarg.0
0x87a7a  ldstr    aYammerYammerem// "YAMMER_YAMMEREMBED_WRPCTOKEN"
0x87a7f  ldloc.2
0x87a80  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x87a85  ldstr    aCrmwrpctoken// "CRMWRPCToken"
0x87a8a  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Item(void)
0x87a8f  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x87a94  ldarg.0
0x87a95  ldstr    aYammerYammerem_0// "YAMMER_YAMMEREMBED_TIMESTAMP"
0x87a9a  ldloc.2
0x87a9b  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x87aa0  ldstr    aCrmwrpctokenti// "CRMWRPCTokenTimeStamp"
0x87aa5  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Item(void)
0x87aaa  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x87aaf  ret
0x87ab0  ldarg.0
0x87ab1  ldstr    aYammerYammerem// "YAMMER_YAMMEREMBED_WRPCTOKEN"
0x87ab6  ldsfld   string [mscorlib]System.String::Empty
0x87abb  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x87ac0  ldarg.0
0x87ac1  ldstr    aYammerYammerem_0// "YAMMER_YAMMEREMBED_TIMESTAMP"
0x87ac6  ldsfld   string [mscorlib]System.String::Empty
0x87acb  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x87ad0  ret
```
