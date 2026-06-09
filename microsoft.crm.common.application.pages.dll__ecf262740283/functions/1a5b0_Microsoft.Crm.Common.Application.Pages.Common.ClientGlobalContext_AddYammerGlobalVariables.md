# Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddYammerGlobalVariables

- ea: `0x1a5b0`
- end: `0x1a6fd`
- name: `Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddYammerGlobalVariables`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1a050`

## callees

- `0x19f10`
- `0x19f20`
- `0x19f40`
- `0x19f60`
- `0x1a5b0`

## string_xrefs

- `0x1a6ae`: `CRMWRPCToken`
- `0x1a6ca`: `CRMWRPCTokenTimeStamp`
- `0x1a5bd`: `YAMMER_IS_INSTALLED`
- `0x1a5cf`: `YAMMER_IS_CONFIGURED_FOR_ORG`
- `0x1a617`: `YAMMER_TOKEN_EXPIRED`
- `0x1a629`: `YAMMER_IS_CONFIGURED_FOR_USER`
- `0x1a63b`: `YAMMER_HAS_CONFIGURE_PRIVILEGE`
- `0x1a6a3`: `YAMMER_YAMMEREMBED_WRPCTOKEN`
- `0x1a6dc`: `YAMMER_YAMMEREMBED_WRPCTOKEN`

## pseudocode

```c

```

## disassembly

```asm
0x1a5b0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a5b5  call     class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.YammerState::Read(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation)
0x1a5ba  stloc.0
0x1a5bb  ldarg.0
0x1a5bc  ldarg.1
0x1a5bd  ldstr    aYammerIsInstal// "YAMMER_IS_INSTALLED"
0x1a5c2  ldloc.0
0x1a5c3  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_IsYammerFeatureAvailable()
0x1a5c8  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a5cd  ldarg.0
0x1a5ce  ldarg.1
0x1a5cf  ldstr    aYammerIsConfig// "YAMMER_IS_CONFIGURED_FOR_ORG"
0x1a5d4  ldloc.0
0x1a5d5  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_IsYammerConfiguredForOrg()
0x1a5da  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a5df  ldarg.0
0x1a5e0  ldarg.1
0x1a5e1  ldstr    aYammerAppId// "YAMMER_APP_ID"
0x1a5e6  ldloc.0
0x1a5e7  callvirt instance string [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_YammerAppId()
0x1a5ec  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a5f1  ldarg.0
0x1a5f2  ldarg.1
0x1a5f3  ldstr    aYammerNetworkN// "YAMMER_NETWORK_NAME"
0x1a5f8  ldloc.0
0x1a5f9  callvirt instance string [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_YammerNetworkName()
0x1a5fe  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a603  ldarg.0
0x1a604  ldarg.1
0x1a605  ldstr    aYammerGroupId// "YAMMER_GROUP_ID"
0x1a60a  ldloc.0
0x1a60b  callvirt instance int64 [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_YammerGroupId()
0x1a610  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, int64 varValue)
0x1a615  ldarg.0
0x1a616  ldarg.1
0x1a617  ldstr    aYammerTokenExp// "YAMMER_TOKEN_EXPIRED"
0x1a61c  ldloc.0
0x1a61d  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_IsYammerOAuthTokenExpired()
0x1a622  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a627  ldarg.0
0x1a628  ldarg.1
0x1a629  ldstr    aYammerIsConfig_0// "YAMMER_IS_CONFIGURED_FOR_USER"
0x1a62e  ldloc.0
0x1a62f  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_IsYammerConfiguredForUser()
0x1a634  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a639  ldarg.0
0x1a63a  ldarg.1
0x1a63b  ldstr    aYammerHasConfi// "YAMMER_HAS_CONFIGURE_PRIVILEGE"
0x1a640  ldloc.0
0x1a641  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_CanConfigureYammer()
0x1a646  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, bool varValue)
0x1a64b  ldarg.0
0x1a64c  ldarg.1
0x1a64d  ldstr    aYammerPostMeth// "YAMMER_POST_METHOD"
0x1a652  ldloc.0
0x1a653  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.Sdk.Caching.CacheData.YammerPostMethod [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_YammerPostMethod()
0x1a658  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, int32 varValue)
0x1a65d  ldloc.0
0x1a65e  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_IsYammerFeatureAvailable()
0x1a663  brfalse  loc_1A6FC
0x1a668  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext::.ctor()
0x1a66d  ldstr    aToolsYammerYam_1// "/tools/yammer/yammerembed.aspx"
0x1a672  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a677  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a67c  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext::GetWrpcTokenAsQueryString(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x1a681  stloc.1
0x1a682  ldloc.1
0x1a683  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a688  brtrue.s loc_1A6DA
0x1a68a  ldstr    asc_1F1DE// ""
0x1a68f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a694  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a699  stloc.2
0x1a69a  ldloc.2
0x1a69b  ldloc.1
0x1a69c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::AppendToQuery(string)
0x1a6a1  ldarg.0
0x1a6a2  ldarg.1
0x1a6a3  ldstr    aYammerYammerem// "YAMMER_YAMMEREMBED_WRPCTOKEN"
0x1a6a8  ldloc.2
0x1a6a9  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x1a6ae  ldstr    aCrmwrpctoken_0// "CRMWRPCToken"
0x1a6b3  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Item(void)
0x1a6b8  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a6bd  ldarg.0
0x1a6be  ldarg.1
0x1a6bf  ldstr    aYammerYammerem_0// "YAMMER_YAMMEREMBED_TIMESTAMP"
0x1a6c4  ldloc.2
0x1a6c5  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x1a6ca  ldstr    aCrmwrpctokenti_0// "CRMWRPCTokenTimeStamp"
0x1a6cf  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Item(void)
0x1a6d4  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a6d9  ret
0x1a6da  ldarg.0
0x1a6db  ldarg.1
0x1a6dc  ldstr    aYammerYammerem// "YAMMER_YAMMEREMBED_WRPCTOKEN"
0x1a6e1  ldsfld   string [mscorlib]System.String::Empty
0x1a6e6  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a6eb  ldarg.0
0x1a6ec  ldarg.1
0x1a6ed  ldstr    aYammerYammerem_0// "YAMMER_YAMMEREMBED_TIMESTAMP"
0x1a6f2  ldsfld   string [mscorlib]System.String::Empty
0x1a6f7  call     instance void Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::AddClientVar(class [mscorlib]System.Text.StringBuilder builder, string varName, string varValue)
0x1a6fc  ret
```
