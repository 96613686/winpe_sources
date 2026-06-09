# Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::OnLoad

- ea: `0x8f70`
- end: `0x90a5`
- name: `Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::OnLoad`
- size: `309`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8db0`
- `0x8df0`
- `0x8e30`
- `0x8e50`
- `0x8e70`
- `0x8f10`
- `0x8f30`
- `0x8f70`
- `0x90b0`
- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x8f70  ldarg.0
0x8f71  ldarg.1
0x8f72  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::OnLoad(class [mscorlib]System.EventArgs)
0x8f77  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8f7c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.SocialInsightsState::Read(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation)
0x8f81  stloc.0
0x8f82  ldarg.0
0x8f83  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_Disclaimer()
0x8f88  ldloc.0
0x8f89  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState::get_AreSocialInsightsTermsAccepted()
0x8f8e  ldc.i4.0
0x8f8f  ceq
0x8f91  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x8f96  ldarg.0
0x8f97  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_ProvisioningTemporaryError()
0x8f9c  ldc.i4.0
0x8f9d  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x8fa2  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x8fa7  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x8fac  stloc.1
0x8fad  ldloc.1
0x8fae  ldc.i4.1
0x8faf  beq.s    loc_8FB5
0x8fb1  ldloc.1
0x8fb2  ldc.i4.4
0x8fb3  bne.un.s loc_9003
0x8fb5  ldarg.0
0x8fb6  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_OnPremiseInstanceSelection()
0x8fbb  ldc.i4.1
0x8fbc  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x8fc1  ldarg.0
0x8fc2  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_OnlineSolutionPicker()
0x8fc7  ldc.i4.0
0x8fc8  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x8fcd  ldarg.0
0x8fce  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_ConnectMslCheckBox()
0x8fd3  ldloc.0
0x8fd4  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState::get_AreSocialInsightsEnabled()
0x8fd9  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputCheckBox::set_Checked(bool)
0x8fde  ldloc.0
0x8fdf  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState::get_IsSocialInsightsInstanceAvailable()
0x8fe4  brfalse.s loc_8FFC
0x8fe6  ldarg.0
0x8fe7  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlInputText Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_MslUrlText()
0x8fec  ldloc.0
0x8fed  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState::get_CurrentSocialInsightsInstance()
0x8ff2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo::get_DiscoveryUrl()
0x8ff7  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x8ffc  ldarg.0
0x8ffd  call     instance void Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::PopulateOrgUrls()
0x9002  ret
0x9003  ldarg.0
0x9004  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_OnlineSolutionPicker()
0x9009  ldc.i4.1
0x900a  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x900f  ldarg.0
0x9010  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_OnPremiseInstanceSelection()
0x9015  ldc.i4.0
0x9016  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x901b  ldarg.0
0x901c  ldloc.0
0x901d  call     instance void Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::PopulateInstanceSelection(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState state)
0x9022  ldarg.0
0x9023  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_SocialInsightsInstance()
0x9028  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x902d  ldstr    aValue// "value"
0x9032  ldloc.0
0x9033  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState::get_CurrentSocialInsightsInstance()
0x9038  brtrue.s loc_903D
0x903a  ldnull
0x903b  br.s     loc_9048
0x903d  ldloc.0
0x903e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState::get_CurrentSocialInsightsInstance()
0x9043  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo::get_SolutionId()
0x9048  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x904d  leave.s  loc_90A4
0x904f  stloc.2
0x9050  ldarg.0
0x9051  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_OnlineSolutionPicker()
0x9056  ldc.i4.0
0x9057  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x905c  ldarg.0
0x905d  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_ProvisioningTemporaryError()
0x9062  ldarg.0
0x9063  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlControl Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_Disclaimer()
0x9068  callvirt instance bool [System.Web]System.Web.UI.Control::get_Visible()
0x906d  ldc.i4.0
0x906e  ceq
0x9070  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x9075  ldstr    aSocialInsights// "Social Insights Provisioning failed. St"...
0x907a  ldloc.2
0x907b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x9080  call     string [mscorlib]System.String::Concat(string, string)
0x9085  stloc.3
0x9086  ldloc.2
0x9087  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x908c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x9091  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x9096  ldloc.3
0x9097  ldc.i4.0
0x9098  newarr   [mscorlib]System.Object
0x909d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x90a2  leave.s  loc_90A4
0x90a4  ret
```
