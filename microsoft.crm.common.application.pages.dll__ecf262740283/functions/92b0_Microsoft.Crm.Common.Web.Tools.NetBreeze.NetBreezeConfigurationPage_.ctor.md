# Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::.ctor

- ea: `0x92b0`
- end: `0x937f`
- name: `Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::.ctor`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x92bb`: `Web.Tools.NetBreeze.Config.OnPremiseInstanceSelection.ConfigureMSL.Step2`
- `0x92f5`: `Web.Tools.NetBreeze.Config.OnPremiseInstanceSelection.ConfigureMSL.Step2`
- `0x92d2`: `<a href="http://go.microsoft.com/fwlink/?LinkId=402363" target="_blank">`
- `0x932f`: `Web.Tools.NetBreeze.Config.OnPremiseInstanceSelection.SignInFailureMessage`

## pseudocode

```c

```

## disassembly

```asm
0x92b0  ldarg.0
0x92b1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x92b6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x92bb  ldstr    aWebToolsNetbre_2// "Web.Tools.NetBreeze.Config.OnPremiseIns"...
0x92c0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x92c5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0x92ca  ldc.i4.2
0x92cb  newarr   [mscorlib]System.Object
0x92d0  dup
0x92d1  ldc.i4.0
0x92d2  ldstr    aAHrefHttpGoMic_0// "<a href=\"http://go.microsoft.com/fwlin"...
0x92d7  stelem.ref
0x92d8  dup
0x92d9  ldc.i4.1
0x92da  ldstr    aA// "</a>"
0x92df  stelem.ref
0x92e0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x92e5  stfld    string Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::ConfigureMslMicrosoftOnlineServicesPortalStep
0x92ea  ldarg.0
0x92eb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x92f0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x92f5  ldstr    aWebToolsNetbre_2// "Web.Tools.NetBreeze.Config.OnPremiseIns"...
0x92fa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x92ff  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0x9304  ldc.i4.2
0x9305  newarr   [mscorlib]System.Object
0x930a  dup
0x930b  ldc.i4.0
0x930c  ldstr    asc_1F1DE// ""
0x9311  stelem.ref
0x9312  dup
0x9313  ldc.i4.1
0x9314  ldstr    asc_1F1DE// ""
0x9319  stelem.ref
0x931a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x931f  stfld    string Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::ConfigureMslMicrosoftOnlineServicesPortalStepLabel
0x9324  ldarg.0
0x9325  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x932a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x932f  ldstr    aWebToolsNetbre_3// "Web.Tools.NetBreeze.Config.OnPremiseIns"...
0x9334  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9339  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0x933e  ldc.i4.2
0x933f  newarr   [mscorlib]System.Object
0x9344  dup
0x9345  ldc.i4.0
0x9346  ldstr    aAIdSigninnowTa// "<a id=\"signInNow\" target=\"_blank\">"
0x934b  stelem.ref
0x934c  dup
0x934d  ldc.i4.1
0x934e  ldstr    aA// "</a>"
0x9353  stelem.ref
0x9354  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9359  stfld    string Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::ConfigureMslSignInFailureMessage
0x935e  ldarg.0
0x935f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9364  ldstr    aSocialinsights// "SocialInsights.SignInError.AddToTrusted"...
0x9369  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x936e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0x9373  stfld    string Microsoft.Crm.Common.Web.Tools.NetBreeze.NetBreezeConfigurationPage::AddToTrustedSitesMessage
0x9378  ldarg.0
0x9379  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::.ctor()
0x937e  ret
```
