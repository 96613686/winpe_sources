# Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::PopulateInstanceSelection

- ea: `0x9170`
- end: `0x92a6`
- name: `Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::PopulateInstanceSelection`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8f70`

## callees

- `0x8f50`
- `0x9170`
- `0x1dbe0`

## string_xrefs

- `0x918f`: `Web.Tools.NetBreeze.Config.Instance.None`
- `0x91c8`: `Web.Tools.NetBreeze.Config.Instance.Option`

## pseudocode

```c

```

## disassembly

```asm
0x9170  newobj   instance void <>c__DisplayClass51_0::.ctor()
0x9175  stloc.0
0x9176  ldloc.0
0x9177  ldarg.1
0x9178  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState <>c__DisplayClass51_0::state
0x917d  call     class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.SocialInsightsState::get_AvailableNetBreezeInstances()
0x9182  stloc.1
0x9183  ldarg.0
0x9184  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_NetbreezeInstance()
0x9189  ldarg.0
0x918a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x918f  ldstr    aWebToolsNetbre_0// "Web.Tools.NetBreeze.Config.Instance.Non"...
0x9194  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9199  ldstr    asc_1F1DE// ""
0x919e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x91a3  ldloc.1
0x91a4  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo>::get_Count()
0x91a9  ldc.i4.0
0x91aa  bgt.s    loc_91AD
0x91ac  ret
0x91ad  ldloc.1
0x91ae  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo>::GetEnumerator()
0x91b3  stloc.2
0x91b4  br.s     loc_9204
0x91b6  ldloc.2
0x91b7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo>::get_Current()
0x91bc  stloc.3
0x91bd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x91c2  ldarg.0
0x91c3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x91c8  ldstr    aWebToolsNetbre_1// "Web.Tools.NetBreeze.Config.Instance.Opt"...
0x91cd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x91d2  ldc.i4.2
0x91d3  newarr   [mscorlib]System.Object
0x91d8  dup
0x91d9  ldc.i4.0
0x91da  ldloc.3
0x91db  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo::get_SolutionDisplayName()
0x91e0  stelem.ref
0x91e1  dup
0x91e2  ldc.i4.1
0x91e3  ldloc.3
0x91e4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo::get_SolutionId()
0x91e9  stelem.ref
0x91ea  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x91ef  stloc.s  4
0x91f1  ldarg.0
0x91f2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_NetbreezeInstance()
0x91f7  ldloc.s  4
0x91f9  ldloc.3
0x91fa  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo::get_SolutionId()
0x91ff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x9204  ldloc.2
0x9205  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x920a  brtrue.s loc_91B6
0x920c  leave.s  loc_9218
0x920e  ldloc.2
0x920f  brfalse.s loc_9217
0x9211  ldloc.2
0x9212  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9217  endfinally
0x9218  ldloc.0
0x9219  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState <>c__DisplayClass51_0::state
0x921e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState::get_CurrentSocialInsightsInstance()
0x9223  brtrue.s loc_9226
0x9225  ret
0x9226  ldloc.1
0x9227  ldloc.0
0x9228  ldftn    instance bool <>c__DisplayClass51_0::<PopulateInstanceSelection>b__0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo instance)
0x922e  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo, bool>::.ctor(object, native int)
0x9233  call     T0x2B000007
0x9238  brfalse.s loc_928A
0x923a  ldarg.0
0x923b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_NetbreezeInstance()
0x9240  ldloc.0
0x9241  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState <>c__DisplayClass51_0::state
0x9246  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState::get_CurrentSocialInsightsInstance()
0x924b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo::get_SolutionDisplayName()
0x9250  ldloc.0
0x9251  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState <>c__DisplayClass51_0::state
0x9256  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState::get_CurrentSocialInsightsInstance()
0x925b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo::get_SolutionId()
0x9260  newobj   instance void [System]System.Collections.Specialized.ListDictionary::.ctor()
0x9265  dup
0x9266  ldstr    aDisabled// "disabled"
0x926b  ldstr    aTrue// "true"
0x9270  callvirt instance void [System]System.Collections.Specialized.ListDictionary::Add(object, object)
0x9275  dup
0x9276  ldstr    aUnavailable// "unavailable"
0x927b  ldstr    aTrue// "true"
0x9280  callvirt instance void [System]System.Collections.Specialized.ListDictionary::Add(object, object)
0x9285  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string, class [System]System.Collections.Specialized.ListDictionary)
0x928a  ldarg.0
0x928b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::get_NetbreezeInstance()
0x9290  ldloc.0
0x9291  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState <>c__DisplayClass51_0::state
0x9296  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState::get_CurrentSocialInsightsInstance()
0x929b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Core.SocialInsights.NetBreezeInstanceInfo::get_SolutionId()
0x92a0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x92a5  ret
```
