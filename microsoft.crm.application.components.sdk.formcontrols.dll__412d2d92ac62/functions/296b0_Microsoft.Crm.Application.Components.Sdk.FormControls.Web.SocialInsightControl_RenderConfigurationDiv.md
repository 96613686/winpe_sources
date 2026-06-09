# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderConfigurationDiv

- ea: `0x296b0`
- end: `0x297b8`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::RenderConfigurationDiv`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x293e0`

## callees

- `0x17950`
- `0x17a10`
- `0x296b0`

## string_xrefs

- `0x296c8`: `<div id='configuration' class='configurationMessage hidden'><p tabindex='{1}'>{0}</p></div>`
- `0x29723`: `<div id='configuration' class='configurationMessage hidden'><p tabindex='{1}'>{0}</p></div>`
- `0x296da`: `NetBreeze.Runtime.Dashboard.NoInstanceConfigured`
- `0x29735`: `NetBreeze.Runtime.EditDashboardToConfigure`
- `0x2976d`: `<div id='configuration' class='configurationLink hidden'><a href='#' tabindex='{1}'>{0}</a></div>`
- `0x2977f`: `NetBreeze.Runtime.ConfigureControl`

## pseudocode

```c

```

## disassembly

```asm
0x296b0  ldstr    asc_30804// ""
0x296b5  stloc.0
0x296b6  ldarg.0
0x296b7  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::_instanceState
0x296bc  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Core.SocialInsights.ISocialInsightsState::get_IsSocialInsightsInstanceAvailable()
0x296c1  brtrue.s loc_29710
0x296c3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x296c8  ldstr    aDivIdConfigura// "<div id='configuration' class='configur"...
0x296cd  ldc.i4.2
0x296ce  newarr   [mscorlib]System.Object
0x296d3  dup
0x296d4  ldc.i4.0
0x296d5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x296da  ldstr    aNetbreezeRunti_4// "NetBreeze.Runtime.Dashboard.NoInstanceC"...
0x296df  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x296e4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x296e9  stelem.ref
0x296ea  dup
0x296eb  ldc.i4.1
0x296ec  ldarg.0
0x296ed  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x296f2  stloc.1
0x296f3  ldloca.s 1
0x296f5  ldstr    aD// "D"
0x296fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x296ff  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x29704  stelem.ref
0x29705  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2970a  stloc.0
0x2970b  br       loc_297B0
0x29710  ldarg.0
0x29711  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentFormDescriptor()
0x29716  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_FormType()
0x2971b  ldc.i4.5
0x2971c  bne.un.s loc_29768
0x2971e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29723  ldstr    aDivIdConfigura// "<div id='configuration' class='configur"...
0x29728  ldc.i4.2
0x29729  newarr   [mscorlib]System.Object
0x2972e  dup
0x2972f  ldc.i4.0
0x29730  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x29735  ldstr    aNetbreezeRunti_5// "NetBreeze.Runtime.EditDashboardToConfig"...
0x2973a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2973f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x29744  stelem.ref
0x29745  dup
0x29746  ldc.i4.1
0x29747  ldarg.0
0x29748  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x2974d  stloc.1
0x2974e  ldloca.s 1
0x29750  ldstr    aD// "D"
0x29755  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2975a  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x2975f  stelem.ref
0x29760  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x29765  stloc.0
0x29766  br.s     loc_297B0
0x29768  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2976d  ldstr    aDivIdConfigura_0// "<div id='configuration' class='configur"...
0x29772  ldc.i4.2
0x29773  newarr   [mscorlib]System.Object
0x29778  dup
0x29779  ldc.i4.0
0x2977a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2977f  ldstr    aNetbreezeRunti_6// "NetBreeze.Runtime.ConfigureControl"
0x29784  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x29789  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x2978e  stelem.ref
0x2978f  dup
0x29790  ldc.i4.1
0x29791  ldarg.0
0x29792  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x29797  stloc.1
0x29798  ldloca.s 1
0x2979a  ldstr    aD// "D"
0x2979f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x297a4  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x297a9  stelem.ref
0x297aa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x297af  stloc.0
0x297b0  ldarg.1
0x297b1  ldloc.0
0x297b2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x297b7  ret
```
