# Microsoft.Crm.Application.Components.UI.Lookup::RenderLookup

- ea: `0x1fa80`
- end: `0x1fdee`
- name: `Microsoft.Crm.Application.Components.UI.Lookup::RenderLookup`
- size: `878`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1f420`

## callees

- `0x1f300`
- `0x1f320`
- `0x1f340`
- `0x1f390`
- `0x1f660`
- `0x1fa80`
- `0x1fdf0`
- `0x23c20`
- `0x241d0`
- `0x24280`
- `0x242c0`

## string_xrefs

- `0x1fb87`: `Recommended_Fields_Background_Color`
- `0x1fb2e`: ` ms-crm-ReadOnly ms-crm-Lookup-ReadOnly`
- `0x1fba1`: ` ms-crm-Lookup-Recommended`

## pseudocode

```c

```

## disassembly

```asm
0x1fa80  ldsfld   string [mscorlib]System.String::Empty
0x1fa85  stloc.0
0x1fa86  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1fa8b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1fa90  brfalse.s loc_1FA98
0x1fa92  ldstr    aWebkitOverflow// "-webkit-overflow-scrolling: touch;"
0x1fa97  stloc.0
0x1fa98  ldarg.1
0x1fa99  ldc.i4.s 9
0x1fa9b  newarr   [mscorlib]System.String
0x1faa0  dup
0x1faa1  ldc.i4.0
0x1faa2  ldstr    aTableId// "<table id=\""
0x1faa7  stelem.ref
0x1faa8  dup
0x1faa9  ldc.i4.1
0x1faaa  ldarg.0
0x1faab  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1fab0  ldstr    aLookuptable// "_lookupTable"
0x1fab5  call     string [mscorlib]System.String::Concat(string, string)
0x1faba  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1fabf  stelem.ref
0x1fac0  dup
0x1fac1  ldc.i4.2
0x1fac2  ldstr    aClassMsCrmLook// "\" class=\"ms-crm-Lookup\" cellpadding="...
0x1fac7  stelem.ref
0x1fac8  dup
0x1fac9  ldc.i4.3
0x1faca  ldloc.0
0x1facb  stelem.ref
0x1facc  dup
0x1facd  ldc.i4.4
0x1face  ldstr    aLookupid// "\" lookupid=\""
0x1fad3  stelem.ref
0x1fad4  dup
0x1fad5  ldc.i4.5
0x1fad6  ldarg.0
0x1fad7  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1fadc  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1fae1  stelem.ref
0x1fae2  dup
0x1fae3  ldc.i4.6
0x1fae4  ldstr    aTrTdValignTopS// "\"><tr><td vAlign=\"top\" style=\"paddi"...
0x1fae9  stelem.ref
0x1faea  dup
0x1faeb  ldc.i4.7
0x1faec  ldarg.0
0x1faed  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1faf2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1faf7  stelem.ref
0x1faf8  dup
0x1faf9  ldc.i4.8
0x1fafa  ldstr    aClassMsCrmLook_0// "\" class=\"ms-crm-Lookup"
0x1faff  stelem.ref
0x1fb00  call     string [mscorlib]System.String::Concat(string[])
0x1fb05  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1fb0a  ldarg.0
0x1fb0b  call     instance bool Microsoft.Crm.Application.Components.UI.Lookup::get_IsDisplayOnlyLookup()
0x1fb10  brfalse.s loc_1FB1D
0x1fb12  ldarg.1
0x1fb13  ldstr    aMsCrmLookupDis// " ms-crm-Lookup-DisplayOnly"
0x1fb18  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1fb1d  ldarg.0
0x1fb1e  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1fb23  brtrue.s loc_1FB2D
0x1fb25  ldarg.0
0x1fb26  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x1fb2b  brfalse.s loc_1FB38
0x1fb2d  ldarg.1
0x1fb2e  ldstr    aMsCrmReadonlyM// " ms-crm-ReadOnly ms-crm-Lookup-ReadOnly"
0x1fb33  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1fb38  ldarg.0
0x1fb39  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Required()
0x1fb3e  stloc.3
0x1fb3f  ldloc.3
0x1fb40  switch   loc_1FBAB, loc_1FBAB, loc_1FB57, loc_1FB82
0x1fb55  br.s     loc_1FBAB
0x1fb57  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1fb5c  ldstr    aRequiredFields// "Required_Fields_Background_Color"
0x1fb61  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fb66  stloc.s  4
0x1fb68  ldloc.s  4
0x1fb6a  brfalse.s loc_1FBAB
0x1fb6c  ldloc.s  4
0x1fb6e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1fb73  brfalse.s loc_1FBAB
0x1fb75  ldarg.1
0x1fb76  ldstr    aMsCrmLookupReq// " ms-crm-Lookup-Required"
0x1fb7b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1fb80  br.s     loc_1FBAB
0x1fb82  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1fb87  ldstr    aRecommendedFie// "Recommended_Fields_Background_Color"
0x1fb8c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fb91  stloc.s  5
0x1fb93  ldloc.s  5
0x1fb95  brfalse.s loc_1FBAB
0x1fb97  ldloc.s  5
0x1fb99  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1fb9e  brfalse.s loc_1FBAB
0x1fba0  ldarg.1
0x1fba1  ldstr    aMsCrmLookupRec// " ms-crm-Lookup-Recommended"
0x1fba6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1fbab  ldarg.1
0x1fbac  ldstr    asc_32802// "\""
0x1fbb1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1fbb6  ldarg.0
0x1fbb7  call     instance string Microsoft.Crm.Application.Components.UI.Lookup::get_LookupImageClass()
0x1fbbc  ldstr    aMsCrmLookupPar// "ms-crm-Lookup-Party"
0x1fbc1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1fbc6  brfalse.s loc_1FBD9
0x1fbc8  ldarg.1
0x1fbc9  ldstr    aStyle_0// "style"
0x1fbce  ldstr    aOverflowYAuto// "overflow-y:auto"
0x1fbd3  ldc.i4.0
0x1fbd4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1fbd9  ldarg.0
0x1fbda  call     instance bool Microsoft.Crm.Application.Components.UI.Lookup::get_IsDisplayOnlyLookup()
0x1fbdf  brtrue.s loc_1FBE9
0x1fbe1  ldarg.0
0x1fbe2  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x1fbe7  brtrue.s loc_1FC0F
0x1fbe9  ldarg.1
0x1fbea  ldstr    aTabindex// "tabindex"
0x1fbef  ldarg.0
0x1fbf0  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x1fbf5  stloc.3
0x1fbf6  ldloca.s 3
0x1fbf8  ldstr    aD_1// "D"
0x1fbfd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1fc02  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1fc07  ldc.i4.0
0x1fc08  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1fc0d  br.s     loc_1FC35
0x1fc0f  ldarg.1
0x1fc10  ldstr    aTabindex// "tabindex"
0x1fc15  ldarg.0
0x1fc16  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x1fc1b  ldc.i4.1
0x1fc1c  add
0x1fc1d  stloc.3
0x1fc1e  ldloca.s 3
0x1fc20  ldstr    aD_1// "D"
0x1fc25  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1fc2a  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1fc2f  ldc.i4.0
0x1fc30  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1fc35  ldarg.1
0x1fc36  ldstr    asc_2B7B6// ">"
0x1fc3b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1fc40  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1fc45  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x1fc4a  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x1fc4f  brfalse.s loc_1FC85
0x1fc51  ldarg.1
0x1fc52  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1fc57  ldstr    aUlStyleFloatRi// "<ul style=\"float:right;width:100%;text"...
0x1fc5c  ldc.i4.1
0x1fc5d  newarr   [mscorlib]System.Object
0x1fc62  dup
0x1fc63  ldc.i4.0
0x1fc64  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1fc69  ldstr    aWebControlsLoo_1// "Web._controls.lookup.lookupmulti.aspx_1"...
0x1fc6e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fc73  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1fc78  stelem.ref
0x1fc79  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1fc7e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1fc83  br.s     loc_1FCB7
0x1fc85  ldarg.1
0x1fc86  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1fc8b  ldstr    aUlStyleFloatLe// "<ul style=\"float:left;width:100%;text-"...
0x1fc90  ldc.i4.1
0x1fc91  newarr   [mscorlib]System.Object
0x1fc96  dup
0x1fc97  ldc.i4.0
0x1fc98  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1fc9d  ldstr    aWebControlsLoo_1// "Web._controls.lookup.lookupmulti.aspx_1"...
0x1fca2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fca7  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x1fcac  stelem.ref
0x1fcad  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1fcb2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1fcb7  ldarg.0
0x1fcb8  ldarg.1
0x1fcb9  call     instance void Microsoft.Crm.Application.Components.UI.Lookup::RenderItems(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x1fcbe  ldarg.1
0x1fcbf  ldstr    aUl// "</ul>"
0x1fcc4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1fcc9  ldnull
0x1fcca  stloc.1
0x1fccb  ldarg.0
0x1fccc  call     instance string Microsoft.Crm.Application.Components.UI.Lookup::get_AccessibilityLabelResourceId()
0x1fcd1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1fcd6  brtrue.s loc_1FCEB
0x1fcd8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1fcdd  ldarg.0
0x1fcde  call     instance string Microsoft.Crm.Application.Components.UI.Lookup::get_AccessibilityLabelResourceId()
0x1fce3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fce8  stloc.1
0x1fce9  br.s     loc_1FCFF
0x1fceb  ldarg.0
0x1fcec  call     instance string Microsoft.Crm.Application.Components.UI.Lookup::get_AccessibilityLabel()
0x1fcf1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1fcf6  brtrue.s loc_1FCFF
0x1fcf8  ldarg.0
0x1fcf9  call     instance string Microsoft.Crm.Application.Components.UI.Lookup::get_AccessibilityLabel()
0x1fcfe  stloc.1
0x1fcff  ldarg.1
0x1fd00  ldstr    aDivLabelClassM// "</div><label class=\"ms-crm-Hidden-NoBe"...
0x1fd05  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1fd0a  ldstr    aFor// "for"
0x1fd0f  ldarg.0
0x1fd10  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1fd15  ldstr    aLedit// "_ledit"
0x1fd1a  call     string [mscorlib]System.String::Concat(string, string)
0x1fd1f  ldarg.1
0x1fd20  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1fd25  ldarg.1
0x1fd26  ldstr    a0LabelInputCla// ">{0}</label><input class=\"ms-crm-Hidde"...
0x1fd2b  ldloc.1
0x1fd2c  brfalse.s loc_1FD36
0x1fd2e  ldloc.1
0x1fd2f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1fd34  br.s     loc_1FD3B
0x1fd36  ldsfld   string [mscorlib]System.String::Empty
0x1fd3b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x1fd40  ldarg.1
0x1fd41  ldstr    aTabindex// "tabindex"
0x1fd46  ldarg.0
0x1fd47  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x1fd4c  stloc.3
0x1fd4d  ldloca.s 3
0x1fd4f  ldstr    aD_1// "D"
0x1fd54  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1fd59  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1fd5e  ldc.i4.0
0x1fd5f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1fd64  ldstr    aId// "id"
0x1fd69  ldarg.0
0x1fd6a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1fd6f  ldstr    aLedit// "_ledit"
0x1fd74  call     string [mscorlib]System.String::Concat(string, string)
0x1fd79  ldarg.1
0x1fd7a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1fd7f  ldarg.1
0x1fd80  ldstr    aMaxlength// "maxlength"
0x1fd85  ldarg.0
0x1fd86  ldflda   int32 Microsoft.Crm.Application.Components.UI.Lookup::_maxUnresolvedTextLength
0x1fd8b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1fd90  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1fd95  ldc.i4.0
0x1fd96  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1fd9b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1fda0  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x1fda5  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x1fdaa  brtrue.s loc_1FDB3
0x1fdac  ldstr    aBorderRight0// "border-right:0;"
0x1fdb1  br.s     loc_1FDB8
0x1fdb3  ldstr    aBorderLeft0// "border-left:0;"
0x1fdb8  stloc.2
0x1fdb9  ldarg.1
0x1fdba  ldstr    aStyle_0// "style"
0x1fdbf  ldloc.2
0x1fdc0  ldstr    aHeight100Paddi// "height: 100%; padding-top:2px; padding-"...
0x1fdc5  call     string [mscorlib]System.String::Concat(string, string)
0x1fdca  ldc.i4.0
0x1fdcb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1fdd0  ldarg.1
0x1fdd1  ldstr    aTd_4// "/></td>"
0x1fdd6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1fddb  ldarg.0
0x1fddc  ldarg.1
0x1fddd  call     instance void Microsoft.Crm.Application.Components.UI.Lookup::RenderButton(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x1fde2  ldarg.1
0x1fde3  ldstr    aTdTrTable// "</td></tr></table>"
0x1fde8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1fded  ret
```
