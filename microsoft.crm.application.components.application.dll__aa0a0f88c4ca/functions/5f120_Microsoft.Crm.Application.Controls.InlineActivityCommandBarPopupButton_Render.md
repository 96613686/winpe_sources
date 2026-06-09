# Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton::Render

- ea: `0x5f120`
- end: `0x5f5c2`
- name: `Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton::Render`
- size: `1186`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x5e7c0`

## callees

- `0x5f120`
- `0x5f5d0`
- `0x5fa90`
- `0x5fab0`
- `0x5fad0`

## string_xrefs

- `0x5f178`: `masterComponentId`
- `0x5f308`: `activityMoreCommandsImage`
- `0x5f43d`: `activityMoreCommandsImage`

## pseudocode

```c

```

## disassembly

```asm
0x5f120  ldarg.1
0x5f121  ldc.i4.1
0x5f122  stloc.0
0x5f123  ldloca.s 0
0x5f125  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x5f12b  callvirt instance string [mscorlib]System.Object::ToString()
0x5f130  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x5f135  ldarg.1
0x5f136  ldstr    aHref// "href"
0x5f13b  ldstr    asc_12FEF0// "#"
0x5f140  ldc.i4.0
0x5f141  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f146  ldarg.1
0x5f147  ldstr    aId_1// "id"
0x5f14c  ldarg.0
0x5f14d  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x5f152  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x5f157  ldc.i4.0
0x5f158  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f15d  ldarg.1
0x5f15e  ldstr    aOnclick// "onclick"
0x5f163  ldarg.0
0x5f164  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::get_Action()
0x5f169  ldc.i4.0
0x5f16a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f16f  ldarg.0
0x5f170  call     instance string Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton::get_MasterComponentId()
0x5f175  brfalse.s loc_5F18E
0x5f177  ldarg.1
0x5f178  ldstr    aMastercomponen// "masterComponentId"
0x5f17d  ldarg.0
0x5f17e  call     instance string Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton::get_MasterComponentId()
0x5f183  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x5f188  ldc.i4.0
0x5f189  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f18e  ldarg.1
0x5f18f  ldstr    aTitle// "title"
0x5f194  ldarg.0
0x5f195  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::get_ToolTip()
0x5f19a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x5f19f  ldc.i4.0
0x5f1a0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f1a5  ldarg.0
0x5f1a6  call     instance bool Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton::get_IsWallFilter()
0x5f1ab  brfalse.s loc_5F1C0
0x5f1ad  ldarg.1
0x5f1ae  ldstr    aClass_0// "class"
0x5f1b3  ldstr    aActivityfilter_11// "activityFiltersDropdown"
0x5f1b8  ldc.i4.0
0x5f1b9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f1be  br.s     loc_5F1E8
0x5f1c0  ldarg.0
0x5f1c1  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5f1c6  ldtoken  Microsoft.Crm.Application.Controls.MoreActivitiesButton
0x5f1cb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5f1d0  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5f1d5  brfalse.s loc_5F1E8
0x5f1d7  ldarg.1
0x5f1d8  ldstr    aClass_0// "class"
0x5f1dd  ldstr    aActivityfilter_12// "activityFilters"
0x5f1e2  ldc.i4.0
0x5f1e3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f1e8  ldarg.0
0x5f1e9  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5f1ee  ldtoken  Microsoft.Crm.Application.Controls.InlineActivityFilterButton
0x5f1f3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5f1f8  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5f1fd  brfalse.s loc_5F210
0x5f1ff  ldarg.1
0x5f200  ldstr    aClass_0// "class"
0x5f205  ldstr    aActivityfilter_12// "activityFilters"
0x5f20a  ldc.i4.0
0x5f20b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f210  ldarg.0
0x5f211  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5f216  ldtoken  Microsoft.Crm.Application.Controls.InlineActivityWallSortButton
0x5f21b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5f220  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5f225  brfalse.s loc_5F238
0x5f227  ldarg.1
0x5f228  ldstr    aClass_0// "class"
0x5f22d  ldstr    aActivitywallso// "activityWallSort"
0x5f232  ldc.i4.0
0x5f233  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f238  ldarg.1
0x5f239  ldstr    aTabindex_0// "tabIndex"
0x5f23e  ldarg.0
0x5f23f  call     instance int32 Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton::get_TabIndex()
0x5f244  stloc.1
0x5f245  ldloca.s 1
0x5f247  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5f24c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5f251  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x5f256  ldc.i4.0
0x5f257  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f25c  ldarg.1
0x5f25d  ldc.i4.s 0x3E
0x5f25f  stloc.2
0x5f260  ldloca.s 2
0x5f262  call     instance string [mscorlib]System.Char::ToString()
0x5f267  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x5f26c  ldarg.0
0x5f26d  call     instance bool Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton::get_IsWallFilter()
0x5f272  brfalse.s loc_5F2C1
0x5f274  ldarg.1
0x5f275  ldc.i4.s 0x4C
0x5f277  stloc.0
0x5f278  ldloca.s 0
0x5f27a  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x5f280  callvirt instance string [mscorlib]System.Object::ToString()
0x5f285  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x5f28a  ldarg.1
0x5f28b  ldc.i4.s 0x3E
0x5f28d  stloc.2
0x5f28e  ldloca.s 2
0x5f290  call     instance string [mscorlib]System.Char::ToString()
0x5f295  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x5f29a  ldarg.0
0x5f29b  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x5f2a0  ldarg.1
0x5f2a1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x5f2a6  ldarg.1
0x5f2a7  ldc.i4.s 0x4C
0x5f2a9  stloc.0
0x5f2aa  ldloca.s 0
0x5f2ac  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x5f2b2  callvirt instance string [mscorlib]System.Object::ToString()
0x5f2b7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x5f2bc  br       loc_5F366
0x5f2c1  ldarg.0
0x5f2c2  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5f2c7  ldtoken  Microsoft.Crm.Application.Controls.MoreActivitiesButton
0x5f2cc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5f2d1  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5f2d6  brfalse  loc_5F366
0x5f2db  ldarg.1
0x5f2dc  ldc.i4.s 0x2E
0x5f2de  stloc.0
0x5f2df  ldloca.s 0
0x5f2e1  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x5f2e7  callvirt instance string [mscorlib]System.Object::ToString()
0x5f2ec  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x5f2f1  ldarg.1
0x5f2f2  ldstr    aTabindex// "tabindex"
0x5f2f7  ldstr    a1// "-1"
0x5f2fc  ldc.i4.0
0x5f2fd  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f302  ldarg.1
0x5f303  ldstr    aClass_0// "class"
0x5f308  ldstr    aActivitymoreco// "activityMoreCommandsImage"
0x5f30d  ldc.i4.0
0x5f30e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f313  ldarg.1
0x5f314  ldstr    aAlt// "alt"
0x5f319  ldarg.0
0x5f31a  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x5f31f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x5f324  ldc.i4.0
0x5f325  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f32a  ldarg.1
0x5f32b  ldstr    aSrc// "src"
0x5f330  ldarg.0
0x5f331  ldfld    string Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton::CDNUrl
0x5f336  ldstr    aImgsMore16Png// "/_imgs/more_16.png"
0x5f33b  call     string [mscorlib]System.String::Concat(string, string)
0x5f340  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string)
0x5f345  callvirt instance string [mscorlib]System.Object::ToString()
0x5f34a  ldc.i4.0
0x5f34b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f350  ldarg.1
0x5f351  ldc.i4.s 0x2E
0x5f353  stloc.0
0x5f354  ldloca.s 0
0x5f356  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x5f35c  callvirt instance string [mscorlib]System.Object::ToString()
0x5f361  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x5f366  ldarg.0
0x5f367  call     instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ReadFormCommandBarButton::get_DownArrow()
0x5f36c  brfalse  loc_5F3F6
0x5f371  ldarg.1
0x5f372  ldc.i4.s 0x2E
0x5f374  stloc.0
0x5f375  ldloca.s 0
0x5f377  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x5f37d  callvirt instance string [mscorlib]System.Object::ToString()
0x5f382  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x5f387  ldarg.1
0x5f388  ldstr    aTabindex// "tabindex"
0x5f38d  ldstr    a1// "-1"
0x5f392  ldc.i4.0
0x5f393  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f398  ldarg.1
0x5f399  ldstr    aClass_0// "class"
0x5f39e  ldstr    aActivityFilter// "activity-filter-image"
0x5f3a3  ldc.i4.0
0x5f3a4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f3a9  ldarg.1
0x5f3aa  ldstr    aAlt// "alt"
0x5f3af  ldstr    aDropdown// "dropdown"
0x5f3b4  ldc.i4.0
0x5f3b5  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f3ba  ldarg.1
0x5f3bb  ldstr    aSrc// "src"
0x5f3c0  ldarg.0
0x5f3c1  ldfld    string Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton::CDNUrl
0x5f3c6  ldstr    aImgsActivities// "/_imgs/activitiesdropdown.png"
0x5f3cb  call     string [mscorlib]System.String::Concat(string, string)
0x5f3d0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string)
0x5f3d5  callvirt instance string [mscorlib]System.Object::ToString()
0x5f3da  ldc.i4.0
0x5f3db  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f3e0  ldarg.1
0x5f3e1  ldc.i4.s 0x2E
0x5f3e3  stloc.0
0x5f3e4  ldloca.s 0
0x5f3e6  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x5f3ec  callvirt instance string [mscorlib]System.Object::ToString()
0x5f3f1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x5f3f6  ldarg.0
0x5f3f7  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5f3fc  ldtoken  Microsoft.Crm.Application.Controls.InlineActivityFilterButton
0x5f401  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5f406  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5f40b  brfalse  loc_5F49B
0x5f410  ldarg.1
0x5f411  ldc.i4.s 0x2E
0x5f413  stloc.0
0x5f414  ldloca.s 0
0x5f416  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x5f41c  callvirt instance string [mscorlib]System.Object::ToString()
0x5f421  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x5f426  ldarg.1
0x5f427  ldstr    aTabindex// "tabindex"
0x5f42c  ldstr    a1// "-1"
0x5f431  ldc.i4.0
0x5f432  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f437  ldarg.1
0x5f438  ldstr    aClass_0// "class"
0x5f43d  ldstr    aActivitymoreco// "activityMoreCommandsImage"
0x5f442  ldc.i4.0
0x5f443  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f448  ldarg.1
0x5f449  ldstr    aAlt// "alt"
0x5f44e  ldarg.0
0x5f44f  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x5f454  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x5f459  ldc.i4.0
0x5f45a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f45f  ldarg.1
0x5f460  ldstr    aSrc// "src"
0x5f465  ldarg.0
0x5f466  ldfld    string Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton::CDNUrl
0x5f46b  ldstr    aImgsGridGridFi// "/_imgs/grid/grid_filter.png"
0x5f470  call     string [mscorlib]System.String::Concat(string, string)
0x5f475  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string)
0x5f47a  callvirt instance string [mscorlib]System.Object::ToString()
0x5f47f  ldc.i4.0
0x5f480  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f485  ldarg.1
0x5f486  ldc.i4.s 0x2E
0x5f488  stloc.0
0x5f489  ldloca.s 0
0x5f48b  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x5f491  callvirt instance string [mscorlib]System.Object::ToString()
0x5f496  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x5f49b  ldarg.0
0x5f49c  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5f4a1  ldtoken  Microsoft.Crm.Application.Controls.InlineActivityWallSortButton
0x5f4a6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5f4ab  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x5f4b0  brfalse  loc_5F5A5
0x5f4b5  ldarg.1
0x5f4b6  ldc.i4.s 0x2E
0x5f4b8  stloc.0
0x5f4b9  ldloca.s 0
0x5f4bb  constrained. [System.Web]System.Web.UI.HtmlTextWriterTag
0x5f4c1  callvirt instance string [mscorlib]System.Object::ToString()
0x5f4c6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x5f4cb  ldarg.1
0x5f4cc  ldstr    aTabindex// "tabindex"
0x5f4d1  ldstr    a1// "-1"
0x5f4d6  ldc.i4.0
0x5f4d7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f4dc  ldarg.1
0x5f4dd  ldstr    aClass_0// "class"
0x5f4e2  ldstr    aActivitywallso_0// "activityWallSortImage"
0x5f4e7  ldc.i4.0
0x5f4e8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f4ed  ldarg.1
0x5f4ee  ldstr    aAlt// "alt"
0x5f4f3  ldarg.0
0x5f4f4  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x5f4f9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x5f4fe  ldc.i4.0
0x5f4ff  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x5f504  ldarg.1
0x5f505  ldstr    aOrderbyvalue// "orderByValue"
0x5f50a  ldsfld   string Microsoft.Crm.Application.Controls.InlineActivityCommandBarPopupButton::OrderBy
0x5f50f  ldc.i4.0
0x5f510  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
  ... truncated ...
```
