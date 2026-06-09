# Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::BuildFeedOptions

- ea: `0x8110`
- end: `0x8367`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::BuildFeedOptions`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8020`

## callees

- `0x7e30`
- `0x7e90`
- `0x7eb0`
- `0x7ed0`
- `0x8110`
- `0x8370`

## string_xrefs

- `0x819f`: `config: { use_sso:true, header: false`

## pseudocode

```c

```

## disassembly

```asm
0x8110  ldarg.0
0x8111  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x8116  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x811b  ldstr    aId// "id"
0x8120  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x8125  stloc.0
0x8126  ldarg.0
0x8127  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x812c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x8131  ldstr    aEtn// "etn"
0x8136  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x813b  stloc.1
0x813c  ldarg.0
0x813d  ldloc.0
0x813e  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::set_CurrentEntityId(string value)
0x8143  ldarg.0
0x8144  ldc.i4.0
0x8145  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::set_NoConversations(bool value)
0x814a  ldarg.0
0x814b  ldc.i4.0
0x814c  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::set_UserNeverConfigured(bool value)
0x8151  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x8156  stloc.2
0x8157  ldarg.0
0x8158  ldfld    class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::state
0x815d  callvirt instance int64 [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_YammerGroupId()
0x8162  brtrue.s loc_816B
0x8164  ldsfld   string [mscorlib]System.String::Empty
0x8169  br.s     loc_8193
0x816b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8170  ldstr    aDefaultgroupid// ", defaultGroupId: {0}"
0x8175  ldc.i4.1
0x8176  newarr   [mscorlib]System.Object
0x817b  dup
0x817c  ldc.i4.0
0x817d  ldarg.0
0x817e  ldfld    class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::state
0x8183  callvirt instance int64 [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_YammerGroupId()
0x8188  box      [mscorlib]System.Int64
0x818d  stelem.ref
0x818e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8193  stloc.3
0x8194  ldloc.2
0x8195  ldstr    asc_258C8// "{ "
0x819a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x819f  ldstr    aConfigUseSsoTr// "config: { use_sso:true, header: false"
0x81a4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x81a9  ldloc.3
0x81aa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x81af  ldstr    asc_2591A// " }, "
0x81b4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x81b9  ldstr    aContainer0// "container: \"{0}\""
0x81be  ldstr    aYammerembed// "#yammerEmbed"
0x81c3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x81c8  ldstr    asc_25960// ", "
0x81cd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x81d2  ldstr    aNetwork0// "network: \"{0}\""
0x81d7  ldarg.0
0x81d8  ldfld    class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::state
0x81dd  callvirt instance string [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_YammerNetworkName()
0x81e2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x81e7  pop
0x81e8  ldloc.1
0x81e9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x81ee  brtrue   loc_8278
0x81f3  ldloc.1
0x81f4  ldstr    aSystemuser// "systemuser"
0x81f9  ldc.i4.4
0x81fa  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x81ff  brfalse.s loc_8278
0x8201  ldarg.0
0x8202  ldc.i4.1
0x8203  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::set_IsSystemUser(bool value)
0x8208  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x820d  ldloc.0
0x820e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x8213  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8218  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x821d  stloc.s  4
0x821f  ldloc.s  4
0x8221  brfalse.s loc_826C
0x8223  ldloc.s  4
0x8225  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_YammerUserId()
0x822a  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x822f  brtrue.s loc_826C
0x8231  ldloc.2
0x8232  ldstr    asc_25960// ", "
0x8237  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x823c  ldstr    aFeedtypeUser// "feedType: \"user\""
0x8241  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8246  ldstr    asc_25960// ", "
0x824b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8250  ldstr    aFeedid0// "feedId: {0}"
0x8255  ldloc.s  4
0x8257  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_YammerUserId()
0x825c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x8261  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x8266  pop
0x8267  br       loc_8354
0x826c  ldarg.0
0x826d  ldc.i4.1
0x826e  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::set_UserNeverConfigured(bool value)
0x8273  br       loc_8354
0x8278  ldloc.0
0x8279  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x827e  brfalse.s loc_828B
0x8280  ldloc.1
0x8281  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8286  brtrue   loc_830D
0x828b  ldloc.0
0x828c  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x8291  brtrue.s loc_829B
0x8293  ldloc.1
0x8294  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x8299  brfalse.s loc_82A7
0x829b  ldarg.0
0x829c  ldc.i4.1
0x829d  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::set_NoConversations(bool value)
0x82a2  br       loc_8354
0x82a7  ldarg.0
0x82a8  ldloc.2
0x82a9  ldloc.0
0x82aa  ldloc.1
0x82ab  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::BuildOpenGraphFeedOptions(class [mscorlib]System.Text.StringBuilder sb, string entityId, string etn)
0x82b0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x82b5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x82ba  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x82bf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x82c4  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x82c9  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.Sdk.Caching.CacheData.YammerPostMethod [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_YammerPostMethod()
0x82ce  ldc.i4.1
0x82cf  bne.un   loc_8354
0x82d4  ldloc.2
0x82d5  ldstr    aPrivateTrue// ", private: true"
0x82da  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x82df  pop
0x82e0  ldloc.2
0x82e1  ldstr    aUsers// ", users: ["
0x82e6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x82eb  ldstr    aEmail0// "{{\"email\" : \"{0}\"}}"
0x82f0  ldarg.1
0x82f1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_YammerEmailAddress()
0x82f6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x82fb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x8300  ldstr    asc_25A1C// "]"
0x8305  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x830a  pop
0x830b  br.s     loc_8354
0x830d  ldarg.0
0x830e  ldfld    class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::state
0x8313  callvirt instance int64 [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_YammerGroupId()
0x8318  brfalse.s loc_8354
0x831a  ldloc.2
0x831b  ldstr    asc_25960// ", "
0x8320  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8325  ldstr    aFeedtypeGroup// "feedType: \"group\""
0x832a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x832f  ldstr    asc_25960// ", "
0x8334  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8339  ldstr    aFeedid0_0// "feedId: \"{0}\""
0x833e  ldarg.0
0x833f  ldfld    class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::state
0x8344  callvirt instance int64 [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_YammerGroupId()
0x8349  box      [mscorlib]System.Int64
0x834e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x8353  pop
0x8354  ldloc.2
0x8355  ldstr    asc_23888// "}"
0x835a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x835f  pop
0x8360  ldloc.2
0x8361  callvirt instance string [mscorlib]System.Object::ToString()
0x8366  ret
```
