# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ActivityFeedsControl::ConfigureHeader

- ea: `0x19150`
- end: `0x19443`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ActivityFeedsControl::ConfigureHeader`
- size: `755`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x190f0`
- `0x19110`
- `0x19150`

## string_xrefs

- `0x19174`: `/_static/_common/scripts/SalesCommonImported.js`
- `0x19184`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0x19194`: `/_static/_common/scripts/SalesCommonFramework.js`
- `0x191a4`: `/_static/_common/scripts/SalesCrmSoapProxyService.js`
- `0x191b4`: `/_static/_common/scripts/Wall.Interfaces.js`
- `0x191c4`: `/_static/_common/scripts/Wall.Control.js`
- `0x19382`: `masterComponentId`
- `0x191d4`: `/_static/_common/scripts/jqueryplugins.js`
- `0x191e4`: `$webresource:msdyn_/CrmSoapServiceProxy.js`
- `0x191fe`: `$webresource:msdyn_/Wall.Service.js`
- `0x19239`: `$webresource:msdyn_/ActivityFeeds.Services.js`
- `0x19287`: `$webresource:msdyn_/Wall.Extensions.js`
- `0x193a9`: `wallContentResourceLocalizedUri`
- `0x193e4`: `firstRunContentResourceLocalizedUri`

## pseudocode

```c

```

## disassembly

```asm
0x19150  ldarg.0
0x19151  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x19156  ldarg.0
0x19157  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1915c  ldc.i4.1
0x1915d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x19162  ldarg.0
0x19163  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x19168  ldc.i4.1
0x19169  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQueryTemplate(bool)
0x1916e  ldarg.0
0x1916f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x19174  ldstr    aStaticCommonSc_0// "/_static/_common/scripts/SalesCommonImp"...
0x19179  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1917e  ldarg.0
0x1917f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x19184  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/CrmInternalUti"...
0x19189  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1918e  ldarg.0
0x1918f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x19194  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/SalesCommonFra"...
0x19199  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1919e  ldarg.0
0x1919f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x191a4  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/SalesCrmSoapPr"...
0x191a9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x191ae  ldarg.0
0x191af  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x191b4  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/Wall.Interface"...
0x191b9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x191be  ldarg.0
0x191bf  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x191c4  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/Wall.Control.j"...
0x191c9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x191ce  ldarg.0
0x191cf  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x191d4  ldstr    aStaticCommonSc_11// "/_static/_common/scripts/jqueryplugins."...
0x191d9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x191de  ldarg.0
0x191df  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x191e4  ldstr    aWebresourceMsd// "$webresource:msdyn_/CrmSoapServiceProxy"...
0x191e9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x191ee  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x191f3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x191f8  ldarg.0
0x191f9  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x191fe  ldstr    aWebresourceMsd_0// "$webresource:msdyn_/Wall.Service.js"
0x19203  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19208  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1920d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x19212  ldarg.0
0x19213  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x19218  ldstr    aWebresourceMsd_1// "$webresource:msdyn_/ActivityFeeds.Menti"...
0x1921d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19222  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19227  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x1922c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x19231  brfalse.s loc_1924D
0x19233  ldarg.0
0x19234  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x19239  ldstr    aWebresourceMsd_2// "$webresource:msdyn_/ActivityFeeds.Servi"...
0x1923e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19243  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19248  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x1924d  ldarg.0
0x1924e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x19253  ldstr    aWebresourceMsd_3// "$webresource:msdyn_/ActivityFeeds.UI.js"
0x19258  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1925d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19262  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x19267  ldarg.0
0x19268  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1926d  ldstr    aWebresourceMsd_4// "$webresource:msdyn_/Wall.FollowActions."...
0x19272  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19277  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1927c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x19281  ldarg.0
0x19282  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x19287  ldstr    aWebresourceMsd_5// "$webresource:msdyn_/Wall.Extensions.js"
0x1928c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19291  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19296  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x1929b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x192a0  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x192a5  stloc.2
0x192a6  ldloca.s 2
0x192a8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x192ad  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x192b2  stloc.0
0x192b3  ldarg.0
0x192b4  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x192b9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x192be  ldstr    a0MsdynActivity// "{0}msdyn_/ActivityFeeds.Resources.{1}js"
0x192c3  ldc.i4.2
0x192c4  newarr   [mscorlib]System.Object
0x192c9  dup
0x192ca  ldc.i4.0
0x192cb  ldstr    aWebresource// "$webresource:"
0x192d0  stelem.ref
0x192d1  dup
0x192d2  ldc.i4.1
0x192d3  ldloc.0
0x192d4  ldstr    a1033// "1033"
0x192d9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x192de  brtrue.s loc_192ED
0x192e0  ldloc.0
0x192e1  ldstr    asc_2D4E6// "."
0x192e6  call     string [mscorlib]System.String::Concat(string, string)
0x192eb  br.s     loc_192F2
0x192ed  ldsfld   string [mscorlib]System.String::Empty
0x192f2  stelem.ref
0x192f3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x192f8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x192fd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19302  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x19307  ldarg.0
0x19308  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1930d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19312  ldstr    a0MsdynStylesWa// "{0}msdyn_/Styles/WallContent.{1}.css"
0x19317  ldc.i4.2
0x19318  newarr   [mscorlib]System.Object
0x1931d  dup
0x1931e  ldc.i4.0
0x1931f  ldstr    aWebresource// "$webresource:"
0x19324  stelem.ref
0x19325  dup
0x19326  ldc.i4.1
0x19327  ldloc.0
0x19328  stelem.ref
0x19329  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1932e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19333  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19338  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x1933d  ldarg.0
0x1933e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x19343  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19348  ldstr    a0MsdynStylesUs// "{0}msdyn_/Styles/UserWall.{1}.css"
0x1934d  ldc.i4.2
0x1934e  newarr   [mscorlib]System.Object
0x19353  dup
0x19354  ldc.i4.0
0x19355  ldstr    aWebresource// "$webresource:"
0x1935a  stelem.ref
0x1935b  dup
0x1935c  ldc.i4.1
0x1935d  ldloc.0
0x1935e  stelem.ref
0x1935f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19364  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19369  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1936e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x19373  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x19378  stloc.1
0x19379  ldarg.0
0x1937a  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ActivityFeedsControl::get_MasterComponentId()
0x1937f  brfalse.s loc_19392
0x19381  ldloc.1
0x19382  ldstr    aMastercomponen// "masterComponentId"
0x19387  ldarg.0
0x19388  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ActivityFeedsControl::get_MasterComponentId()
0x1938d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x19392  ldloc.1
0x19393  ldstr    aLoadwalloninit// "loadWallOnInit"
0x19398  ldarg.0
0x19399  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ActivityFeedsControl::get_LoadWallOnInit()
0x1939e  box      [mscorlib]System.Boolean
0x193a3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x193a8  ldloc.1
0x193a9  ldstr    aWallcontentres// "wallContentResourceLocalizedUri"
0x193ae  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x193b3  ldstr    a0MsdynWallcont// "{0}msdyn_/WallContent.{1}.htm"
0x193b8  ldc.i4.2
0x193b9  newarr   [mscorlib]System.Object
0x193be  dup
0x193bf  ldc.i4.0
0x193c0  ldstr    aWebresource// "$webresource:"
0x193c5  stelem.ref
0x193c6  dup
0x193c7  ldc.i4.1
0x193c8  ldloc.0
0x193c9  stelem.ref
0x193ca  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x193cf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x193d4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x193d9  callvirt instance string [mscorlib]System.Object::ToString()
0x193de  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x193e3  ldloc.1
0x193e4  ldstr    aFirstrunconten// "firstRunContentResourceLocalizedUri"
0x193e9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x193ee  ldstr    a0MsdynFirstrun// "{0}msdyn_/FirstRunContent.{1}.htm"
0x193f3  ldc.i4.2
0x193f4  newarr   [mscorlib]System.Object
0x193f9  dup
0x193fa  ldc.i4.0
0x193fb  ldstr    aWebresource// "$webresource:"
0x19400  stelem.ref
0x19401  dup
0x19402  ldc.i4.1
0x19403  ldloc.0
0x19404  stelem.ref
0x19405  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1940a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1940f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19414  callvirt instance string [mscorlib]System.Object::ToString()
0x19419  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1941e  ldarg.0
0x1941f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x19424  ldstr    aActivityfeedsU// "ActivityFeeds.UI.ActivityFeedsControl"
0x19429  ldloc.1
0x1942a  ldnull
0x1942b  ldnull
0x1942c  ldarg.0
0x1942d  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x19432  ldstr    aContainer// "_container"
0x19437  call     string [mscorlib]System.String::Concat(string, string)
0x1943c  ldc.i4.1
0x1943d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string, bool)
0x19442  ret
```
