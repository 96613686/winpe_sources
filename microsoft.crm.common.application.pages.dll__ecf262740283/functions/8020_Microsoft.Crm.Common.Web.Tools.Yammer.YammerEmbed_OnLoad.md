# Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::OnLoad

- ea: `0x8020`
- end: `0x810b`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::OnLoad`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x7e10`
- `0x7e50`
- `0x7e70`
- `0x7e90`
- `0x7ef0`
- `0x8020`
- `0x8110`

## string_xrefs

- `0x8083`: `WRPCTokenState`
- `0x8095`: `Invalid WRPC token key.`

## pseudocode

```c

```

## disassembly

```asm
0x8020  ldarg.0
0x8021  ldarg.1
0x8022  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::OnLoad(class [mscorlib]System.EventArgs)
0x8027  ldarg.0
0x8028  ldc.i4.0
0x8029  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::set_IsSystemUser(bool value)
0x802e  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x8033  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x8038  stloc.0
0x8039  ldarg.0
0x803a  ldloc.0
0x803b  ldc.i4.2
0x803c  ceq
0x803e  ldc.i4.0
0x803f  ceq
0x8041  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::set_IsOnPremise(bool value)
0x8046  ldarg.0
0x8047  ldfld    class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::state
0x804c  callvirt instance string [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_YammerAppId()
0x8051  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8056  brfalse.s loc_8073
0x8058  ldarg.0
0x8059  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x805e  ldc.i4   0x194
0x8063  callvirt instance void [System.Web]System.Web.HttpResponse::set_StatusCode(int32)
0x8068  ldarg.0
0x8069  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x806e  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x8073  ldarg.0
0x8074  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ValidateWrpcContext()
0x8079  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x807e  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x8083  ldstr    aWrpctokenstate// "WRPCTokenState"
0x8088  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x808d  unbox.any [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.WrpcTokenState
0x8092  ldc.i4.1
0x8093  bne.un.s loc_80A5
0x8095  ldstr    aInvalidWrpcTok// "Invalid WRPC token key."
0x809a  ldc.i4   0x80631109
0x809f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x80a4  throw
0x80a5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x80aa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x80af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x80b4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x80b9  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x80be  stloc.1
0x80bf  ldarg.0
0x80c0  ldloc.1
0x80c1  brfalse.s loc_80CB
0x80c3  ldloc.1
0x80c4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_IsYammerConfigured()
0x80c9  brtrue.s loc_80D2
0x80cb  ldsfld   string [mscorlib]System.String::Empty
0x80d0  br.s     loc_80D8
0x80d2  ldloc.1
0x80d3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_YammerUserId()
0x80d8  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::set_YammerUserId(string value)
0x80dd  ldarg.0
0x80de  ldloc.1
0x80df  call     instance string Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::BuildFeedOptions(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser userData)
0x80e4  stloc.2
0x80e5  ldarg.0
0x80e6  ldloc.2
0x80e7  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::set_FeedOptionsString(string value)
0x80ec  ldarg.0
0x80ed  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x80f2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x80f7  stloc.3
0x80f8  ldloca.s 3
0x80fa  constrained. [mscorlib]System.Guid
0x8100  callvirt instance string [mscorlib]System.Object::ToString()
0x8105  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerEmbed::set_UserId(string value)
0x810a  ret
```
