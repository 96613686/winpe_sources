# Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::OnLoad

- ea: `0x7890`
- end: `0x794c`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::OnLoad`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x76c0`
- `0x76d0`
- `0x7700`
- `0x7710`
- `0x7730`
- `0x7890`
- `0x7950`

## pseudocode

```c

```

## disassembly

```asm
0x7890  ldarg.0
0x7891  ldarg.1
0x7892  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::OnLoad(class [mscorlib]System.EventArgs)
0x7897  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x789c  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x78a1  stloc.0
0x78a2  ldarg.0
0x78a3  ldloc.0
0x78a4  ldc.i4.2
0x78a5  ceq
0x78a7  ldc.i4.0
0x78a8  ceq
0x78aa  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::set_IsOrgOnPremise(bool value)
0x78af  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x78b4  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.YammerState::EnsureUserCanConfigureYammer(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation)
0x78b9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x78be  call     class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.YammerState::Read(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation)
0x78c3  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_IsYammerFeatureAvailable()
0x78c8  brtrue.s loc_78D5
0x78ca  ldstr    aThisPageShould// "This page should not be hit if the yamm"...
0x78cf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x78d4  throw
0x78d5  ldarg.0
0x78d6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x78db  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x78e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x78e5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x78ea  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x78ef  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::set_Config(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings value)
0x78f4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x78f9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x78fe  call     class [mscorlib]System.Security.SecureString [Microsoft.Crm.Yammer]Microsoft.Crm.Yammer.YammerServiceUtility::GetYammerOAuthAccessToken(valuetype [mscorlib]System.Guid)
0x7903  stloc.1
0x7904  ldarg.0
0x7905  ldloc.1
0x7906  brfalse.s loc_792A
0x7908  ldarg.0
0x7909  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_Config()
0x790e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_YammerOAuthAccessTokenExpired()
0x7913  brtrue.s loc_792A
0x7915  ldarg.0
0x7916  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_Config()
0x791b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_YammerNetworkName()
0x7920  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x7925  ldc.i4.0
0x7926  ceq
0x7928  br.s     loc_792B
0x792a  ldc.i4.0
0x792b  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::set_HasValidConfig(bool value)
0x7930  ldarg.0
0x7931  call     instance bool Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_HasValidConfig()
0x7936  brfalse.s loc_793F
0x7938  ldarg.0
0x7939  ldloc.1
0x793a  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::ConfigureSelectedGroup(class [mscorlib]System.Security.SecureString yammerOAuthAccessToken)
0x793f  leave.s  loc_794B
0x7941  ldloc.1
0x7942  brfalse.s loc_794A
0x7944  ldloc.1
0x7945  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x794a  endfinally
0x794b  ret
```
