# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::SetExpandos

- ea: `0x20130`
- end: `0x203b9`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::SetExpandos`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1fe30`

## callees

- `0x17cf0`
- `0x1f8a0`
- `0x1f8d0`
- `0x1fa70`
- `0x1fa90`
- `0x1fab0`
- `0x1fad0`
- `0x20130`

## string_xrefs

- `0x2019f`: `generatedataxml`

## pseudocode

```c

```

## disassembly

```asm
0x20130  ldarg.0
0x20131  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x20136  ldstr    aLookuptypes// "lookuptypes"
0x2013b  ldarg.1
0x2013c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x20141  ldarg.0
0x20142  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x20147  ldstr    aCrmattributeid// "crmattributeid"
0x2014c  ldarg.s  4
0x2014e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x20153  ldarg.0
0x20154  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x20159  ldstr    aLookuptypename// "lookuptypenames"
0x2015e  ldarg.2
0x2015f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x20164  ldarg.0
0x20165  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x2016a  ldstr    aLookuptypeicon// "lookuptypeIcons"
0x2016f  ldarg.3
0x20170  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x20175  ldarg.0
0x20176  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x2017b  ldstr    aLookupbrowse// "lookupbrowse"
0x20180  ldarg.0
0x20181  ldfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_lookupBrowse
0x20186  brtrue.s loc_2018F
0x20188  ldstr    a0// "0"
0x2018d  br.s     loc_20194
0x2018f  ldstr    a1_0// "1"
0x20194  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x20199  ldarg.0
0x2019a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x2019f  ldstr    aGeneratedataxm// "generatedataxml"
0x201a4  ldarg.0
0x201a5  ldfld    string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_generateDataXmlEvent
0x201aa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x201af  ldarg.0
0x201b0  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x201b5  ldstr    aLookupstyle// "lookupstyle"
0x201ba  ldarg.0
0x201bb  ldfld    string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_lookupStyle
0x201c0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x201c5  ldarg.0
0x201c6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x201cb  ldstr    aDefaulttype// "defaulttype"
0x201d0  ldarg.0
0x201d1  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_DefaultType()
0x201d6  stloc.0
0x201d7  ldloca.s 0
0x201d9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x201de  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x201e3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x201e8  ldarg.0
0x201e9  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x201ee  ldstr    aAutoresolve// "autoresolve"
0x201f3  ldarg.0
0x201f4  ldfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_autoResolve
0x201f9  brtrue.s loc_20202
0x201fb  ldstr    a0// "0"
0x20200  br.s     loc_20207
0x20202  ldstr    a1_0// "1"
0x20207  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x2020c  ldarg.0
0x2020d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x20212  ldstr    aAllowfilteroff// "allowFilterOff"
0x20217  ldarg.0
0x20218  ldfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_allowFilterOff
0x2021d  brtrue.s loc_20226
0x2021f  ldstr    a0// "0"
0x20224  br.s     loc_2022B
0x20226  ldstr    a1_0// "1"
0x2022b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x20230  ldarg.0
0x20231  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x20236  ldstr    aDisablemru// "disableMru"
0x2023b  ldarg.0
0x2023c  ldfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_disableMru
0x20241  brtrue.s loc_2024A
0x20243  ldstr    a0// "0"
0x20248  br.s     loc_2024F
0x2024a  ldstr    a1_0// "1"
0x2024f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x20254  ldarg.0
0x20255  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x2025a  ldstr    aDisablequickfi// "disableQuickFind"
0x2025f  ldarg.0
0x20260  ldfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_disableQuickFind
0x20265  brtrue.s loc_2026E
0x20267  ldstr    a0// "0"
0x2026c  br.s     loc_20273
0x2026e  ldstr    a1_0// "1"
0x20273  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x20278  ldarg.0
0x20279  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x2027e  ldstr    aDisableviewpic// "disableViewPicker"
0x20283  ldarg.0
0x20284  ldfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_disableViewPicker
0x20289  brtrue.s loc_20292
0x2028b  ldstr    a0// "0"
0x20290  br.s     loc_20297
0x20292  ldstr    a1_0// "1"
0x20297  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x2029c  ldarg.0
0x2029d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x202a2  ldstr    aAvailableviewi// "availableViewIds"
0x202a7  ldarg.0
0x202a8  ldfld    string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_availableViewIds
0x202ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x202b2  ldarg.0
0x202b3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x202b8  ldstr    aShowproperty// "showproperty"
0x202bd  ldarg.0
0x202be  ldfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_showProperty
0x202c3  brtrue.s loc_202CC
0x202c5  ldstr    a0// "0"
0x202ca  br.s     loc_202D1
0x202cc  ldstr    a1_0// "1"
0x202d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x202d6  ldarg.0
0x202d7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x202dc  ldstr    aResolveemailad_0// "resolveemailaddress"
0x202e1  ldarg.0
0x202e2  ldfld    bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_resolveEmailAddress
0x202e7  brtrue.s loc_202F0
0x202e9  ldstr    a0// "0"
0x202ee  br.s     loc_202F5
0x202f0  ldstr    a1_0// "1"
0x202f5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x202fa  ldarg.0
0x202fb  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x20300  ldstr    aIsdisplayonly// "isDisplayOnly"
0x20305  ldarg.0
0x20306  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_IsDisplayOnlyLookup()
0x2030b  stloc.1
0x2030c  ldloca.s 1
0x2030e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20313  call     instance string [mscorlib]System.Boolean::ToString(class [mscorlib]System.IFormatProvider)
0x20318  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x2031d  ldarg.0
0x2031e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x20323  ldstr    aSavedquerytype// "savedquerytype"
0x20328  ldarg.0
0x20329  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_SavedQueryType()
0x2032e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x20333  ldarg.0
0x20334  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_FilterRelationshipName()
0x20339  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2033e  brtrue.s loc_203B8
0x20340  ldarg.0
0x20341  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_DependentAttributeName()
0x20346  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2034b  brtrue.s loc_203B8
0x2034d  ldarg.0
0x2034e  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_DependentAttributeType()
0x20353  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x20358  brtrue.s loc_203B8
0x2035a  ldarg.0
0x2035b  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x20360  ldstr    aRelationshipid// "RelationshipId"
0x20365  ldarg.0
0x20366  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_FilterRelationshipName()
0x2036b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x20370  ldarg.0
0x20371  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x20376  ldstr    aDependantattri// "DependantAttributeName"
0x2037b  ldarg.0
0x2037c  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_DependentAttributeName()
0x20381  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x20386  ldarg.0
0x20387  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x2038c  ldstr    aDependantattri_0// "DependantAttributeType"
0x20391  ldarg.0
0x20392  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_DependentAttributeType()
0x20397  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2039c  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x203a1  call     instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x203a6  stloc.0
0x203a7  ldloca.s 0
0x203a9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x203ae  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x203b3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x203b8  ret
```
