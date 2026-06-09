# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.InlineJsonCoverterGetPartyList::AppendPartyList

- ea: `0x22fb0`
- end: `0x230e0`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.InlineJsonCoverterGetPartyList::AppendPartyList`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x22e20`

## callees

- `0x224b0`
- `0x22fb0`
- `0x230e0`

## string_xrefs

- `0x22fbd`: `"_noread":"none",`

## pseudocode

```c

```

## disassembly

```asm
0x22fb0  ldarg.0
0x22fb1  ldstr    aVisibleInline// "\"_visible\":\"inline\","
0x22fb6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x22fbb  pop
0x22fbc  ldarg.0
0x22fbd  ldstr    aNoreadNone// "\"_noread\":\"none\","
0x22fc2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x22fc7  pop
0x22fc8  ldarg.0
0x22fc9  ldarg.2
0x22fca  ldarg.3
0x22fcb  brtrue.s loc_22FD5
0x22fcd  ldarg.1
0x22fce  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Name()
0x22fd3  br.s     loc_22FE5
0x22fd5  ldarg.1
0x22fd6  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Name()
0x22fdb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x22fe0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x22fe5  ldc.i4.1
0x22fe6  call     void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.InlineJsonCoverterGetPartyList::AppendDataValueForAttribute(class [mscorlib]System.Text.StringBuilder dataValues, bool isSecuredRead, string dataValue, bool appendComma)
0x22feb  ldarg.0
0x22fec  ldstr    aOid// "oid"
0x22ff1  ldarg.1
0x22ff2  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x22ff7  ldc.i4.1
0x22ff8  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0x22ffd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x23002  pop
0x23003  ldarg.0
0x23004  ldstr    aActivitypartyi// "activitypartyid"
0x23009  ldarg.1
0x2300a  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PartyListLookupItem::get_ActivityPartyId()
0x2300f  ldc.i4.1
0x23010  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0x23015  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2301a  pop
0x2301b  ldarg.0
0x2301c  ldstr    aOtype// "otype"
0x23021  ldarg.1
0x23022  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TypedLookupItem::get_Type()
0x23027  stloc.0
0x23028  ldloca.s 0
0x2302a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2302f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x23034  ldc.i4.1
0x23035  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0x2303a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2303f  pop
0x23040  ldarg.0
0x23041  ldstr    aImg// "img"
0x23046  ldarg.1
0x23047  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TypedLookupItem::get_Type()
0x2304c  ldc.i4.0
0x2304d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType)
0x23052  callvirt instance string [mscorlib]System.Object::ToString()
0x23057  ldc.i4.1
0x23058  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0x2305d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x23062  pop
0x23063  ldarg.0
0x23064  ldstr    aOtypename// "otypename"
0x23069  ldarg.1
0x2306a  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.TypedLookupItem::get_Type()
0x2306f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x23074  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x23079  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x2307e  ldc.i4.1
0x2307f  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0x23084  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x23089  pop
0x2308a  ldarg.0
0x2308b  ldstr    aStyle// "style"
0x23090  ldarg.1
0x23091  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Style()
0x23096  ldc.i4.1
0x23097  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0x2309c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x230a1  pop
0x230a2  ldarg.1
0x230a3  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_IsProcessEnabled()
0x230a8  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x230ad  brtrue.s loc_230C7
0x230af  ldarg.0
0x230b0  ldstr    aIsprocessenabl// "isprocessenabled"
0x230b5  ldarg.1
0x230b6  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_IsProcessEnabled()
0x230bb  ldc.i4.1
0x230bc  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0x230c1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x230c6  pop
0x230c7  ldarg.0
0x230c8  ldstr    aCallback// "callback"
0x230cd  ldarg.1
0x230ce  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LookupItem::get_Callback()
0x230d3  ldc.i4.0
0x230d4  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::GetJsonPair(string, string, bool)
0x230d9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x230de  pop
0x230df  ret
```
