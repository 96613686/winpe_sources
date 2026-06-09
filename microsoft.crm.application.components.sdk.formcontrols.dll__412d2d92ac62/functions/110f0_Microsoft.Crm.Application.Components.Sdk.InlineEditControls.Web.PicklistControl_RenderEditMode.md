# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.PicklistControl::RenderEditMode

- ea: `0x110f0`
- end: `0x11539`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.PicklistControl::RenderEditMode`
- size: `1097`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1450`
- `0x110f0`
- `0x11540`
- `0x115f0`
- `0x11690`

## string_xrefs

- `0x111f4`: `ms-crm-SelectBox ms-crm-Inline-OptionSet-AutoOpen ms-crm-InlineMultiPicklist`
- `0x113ba`: `ms-crm-SelectBox ms-crm-Inline-OptionSet-AutoOpen ms-crm-Inline-HideByZeroHeight-Ie7`

## pseudocode

```c

```

## disassembly

```asm
0x110f0  ldarg.0
0x110f1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x110f6  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeMetadata
0x110fb  stloc.0
0x110fc  ldarg.0
0x110fd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x11102  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Description()
0x11107  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1110c  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x11111  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x11116  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1111b  stloc.1
0x1111c  ldloc.1
0x1111d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11122  brtrue.s loc_11127
0x11124  ldloc.1
0x11125  br.s     loc_1112C
0x11127  ldstr    asc_30804// ""
0x1112c  stloc.1
0x1112d  ldloc.0
0x1112e  brfalse  loc_11315
0x11133  ldarg.1
0x11134  ldstr    aDiv// "div"
0x11139  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x1113e  ldarg.1
0x1113f  ldstr    aClass// "class"
0x11144  ldstr    aMsCrmInlineEdi_5// "ms-crm-Inline-Edit ms-crm-Inline-Option"...
0x11149  ldc.i4.0
0x1114a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1114f  ldarg.1
0x11150  ldstr    aStyle// "style"
0x11155  ldstr    aDisplayNone_1// "display: none"
0x1115a  ldc.i4.0
0x1115b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11160  ldarg.1
0x11161  ldc.i4.s 0x3E
0x11163  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x11168  ldarg.1
0x11169  ldstr    aSelect// "select"
0x1116e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x11173  ldstr    aId// "id"
0x11178  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1117d  ldstr    a0I// "{0}_i"
0x11182  ldc.i4.1
0x11183  newarr   [mscorlib]System.Object
0x11188  dup
0x11189  ldc.i4.0
0x1118a  ldarg.0
0x1118b  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x11190  stelem.ref
0x11191  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11196  ldarg.1
0x11197  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1119c  ldarg.1
0x1119d  ldstr    aAttrname// "attrname"
0x111a2  ldloc.0
0x111a3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x111a8  ldc.i4.0
0x111a9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x111ae  ldarg.1
0x111af  ldstr    aDefaultselecte// "defaultselected"
0x111b4  ldstr    aNull// "null"
0x111b9  ldc.i4.0
0x111ba  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x111bf  ldarg.1
0x111c0  ldstr    aAttrpriv// "attrpriv"
0x111c5  ldstr    a7// "7"
0x111ca  ldc.i4.0
0x111cb  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x111d0  ldarg.1
0x111d1  ldstr    aTitle// "title"
0x111d6  ldloc.1
0x111d7  ldc.i4.0
0x111d8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x111dd  ldarg.1
0x111de  ldstr    aTabindex// "tabindex"
0x111e3  ldstr    a1// "-1"
0x111e8  ldc.i4.0
0x111e9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x111ee  ldarg.1
0x111ef  ldstr    aClass// "class"
0x111f4  ldstr    aMsCrmSelectbox_0// "ms-crm-SelectBox ms-crm-Inline-OptionSe"...
0x111f9  ldc.i4.0
0x111fa  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x111ff  ldstr    aAriaLabelledby// "aria-labelledby"
0x11204  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11209  ldstr    a0C0W// "{0}_c {0}_w"
0x1120e  ldc.i4.1
0x1120f  newarr   [mscorlib]System.Object
0x11214  dup
0x11215  ldc.i4.0
0x11216  ldarg.0
0x11217  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1121c  stelem.ref
0x1121d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11222  ldarg.1
0x11223  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x11228  ldloc.0
0x11229  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x1122e  ldc.i4.2
0x1122f  beq.s    loc_1123A
0x11231  ldloc.0
0x11232  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x11237  ldc.i4.1
0x11238  bne.un.s loc_1124B
0x1123a  ldarg.1
0x1123b  ldstr    aAriaRequired// "aria-required"
0x11240  ldstr    aTrue// "true"
0x11245  ldc.i4.0
0x11246  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1124b  ldarg.1
0x1124c  ldstr    aSize// "size"
0x11251  ldstr    a2// "2"
0x11256  ldc.i4.0
0x11257  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1125c  ldarg.1
0x1125d  ldstr    aStyle// "style"
0x11262  ldstr    aPositionRelati// "position: relative;"
0x11267  ldc.i4.0
0x11268  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1126d  ldarg.1
0x1126e  ldc.i4.s 0x3E
0x11270  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x11275  ldarg.1
0x11276  ldsfld   string [mscorlib]System.String::Empty
0x1127b  ldsfld   string [mscorlib]System.String::Empty
0x11280  call     void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.PicklistControl::RenderOptionValue(class [System.Web]System.Web.UI.HtmlTextWriter writer, string displayText, string displayValue)
0x11285  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x1128a  stloc.2
0x1128b  ldloc.0
0x1128c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x11291  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeFormats::get_Language()
0x11296  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1129b  brfalse.s loc_112A6
0x1129d  ldarg.0
0x1129e  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.PicklistControl::CreateLanguageOptions()
0x112a3  stloc.2
0x112a4  br.s     loc_112BF
0x112a6  ldloc.0
0x112a7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x112ac  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IntegerAttributeFormats::get_Timezone()
0x112b1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x112b6  brfalse.s loc_112BF
0x112b8  ldarg.0
0x112b9  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.PicklistControl::CreateTimeZoneOptions()
0x112be  stloc.2
0x112bf  ldloc.2
0x112c0  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x112c5  stloc.3
0x112c6  br.s     loc_112E5
0x112c8  ldloca.s 3
0x112ca  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x112cf  stloc.s  4
0x112d1  ldarg.1
0x112d2  ldloca.s 4
0x112d4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x112d9  ldloca.s 4
0x112db  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x112e0  call     void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.PicklistControl::RenderOptionValue(class [System.Web]System.Web.UI.HtmlTextWriter writer, string displayText, string displayValue)
0x112e5  ldloca.s 3
0x112e7  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x112ec  brtrue.s loc_112C8
0x112ee  leave.s  loc_112FE
0x112f0  ldloca.s 3
0x112f2  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x112f8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x112fd  endfinally
0x112fe  ldarg.1
0x112ff  ldstr    aSelect// "select"
0x11304  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x11309  ldarg.1
0x1130a  ldstr    aDiv// "div"
0x1130f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x11314  ret
0x11315  ldarg.0
0x11316  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x1131b  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata
0x11320  stloc.s  5
0x11322  ldarg.1
0x11323  ldstr    aDiv// "div"
0x11328  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x1132d  ldarg.1
0x1132e  ldstr    aClass// "class"
0x11333  ldstr    aMsCrmInlineEdi_6// "ms-crm-Inline-Edit ms-crm-Inline-Option"...
0x11338  ldc.i4.0
0x11339  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1133e  ldarg.1
0x1133f  ldstr    aStyle// "style"
0x11344  ldstr    aDisplayNone_0// "display: none;"
0x11349  ldc.i4.0
0x1134a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1134f  ldstr    aId// "id"
0x11354  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11359  ldstr    a0Idiv// "{0}_iDiv"
0x1135e  ldc.i4.1
0x1135f  newarr   [mscorlib]System.Object
0x11364  dup
0x11365  ldc.i4.0
0x11366  ldarg.0
0x11367  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1136c  stelem.ref
0x1136d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11372  ldarg.1
0x11373  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x11378  ldarg.1
0x11379  ldc.i4.s 0x3E
0x1137b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x11380  ldarg.1
0x11381  ldstr    aSelect// "select"
0x11386  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x1138b  ldstr    aId// "id"
0x11390  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11395  ldstr    a0I// "{0}_i"
0x1139a  ldc.i4.1
0x1139b  newarr   [mscorlib]System.Object
0x113a0  dup
0x113a1  ldc.i4.0
0x113a2  ldarg.0
0x113a3  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x113a8  stelem.ref
0x113a9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x113ae  ldarg.1
0x113af  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x113b4  ldarg.1
0x113b5  ldstr    aClass// "class"
0x113ba  ldstr    aMsCrmSelectbox_1// "ms-crm-SelectBox ms-crm-Inline-OptionSe"...
0x113bf  ldc.i4.0
0x113c0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x113c5  ldstr    aAriaLabelledby// "aria-labelledby"
0x113ca  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x113cf  ldstr    a0W// "{0}_w"
0x113d4  ldc.i4.1
0x113d5  newarr   [mscorlib]System.Object
0x113da  dup
0x113db  ldc.i4.0
0x113dc  ldarg.0
0x113dd  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x113e2  stelem.ref
0x113e3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x113e8  ldarg.1
0x113e9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x113ee  ldstr    aAttrname// "attrname"
0x113f3  ldloc.s  5
0x113f5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x113fa  ldarg.1
0x113fb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x11400  ldloc.s  5
0x11402  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x11407  ldc.i4.2
0x11408  beq.s    loc_11414
0x1140a  ldloc.s  5
0x1140c  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x11411  ldc.i4.1
0x11412  bne.un.s loc_11425
0x11414  ldarg.1
0x11415  ldstr    aAriaRequired// "aria-required"
0x1141a  ldstr    aTrue// "true"
0x1141f  ldc.i4.0
0x11420  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11425  ldarg.0
0x11426  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x1142b  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.BooleanAttributeMetadata
0x11430  ldnull
0x11431  cgt.un
0x11433  ldc.i4.0
0x11434  ceq
0x11436  dup
0x11437  brtrue.s loc_11447
0x11439  ldloc.s  5
0x1143b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_Options()
0x11440  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>>::get_Count()
0x11445  br.s     loc_11455
0x11447  ldloc.s  5
0x11449  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_Options()
0x1144e  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>>::get_Count()
0x11453  ldc.i4.1
0x11454  add
0x11455  stloc.s  6
0x11457  ldarg.1
0x11458  ldstr    aSize// "size"
0x1145d  ldloca.s 6
0x1145f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11464  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x11469  ldc.i4.0
0x1146a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1146f  ldarg.1
0x11470  ldc.i4.s 0x3E
0x11472  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x11477  brfalse.s loc_11489
0x11479  ldarg.1
0x1147a  ldsfld   string [mscorlib]System.String::Empty
0x1147f  ldsfld   string [mscorlib]System.String::Empty
0x11484  call     void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.PicklistControl::RenderOptionValue(class [System.Web]System.Web.UI.HtmlTextWriter writer, string displayText, string displayValue)
0x11489  ldloc.s  5
0x1148b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_OptionsInDisplayOrder()
0x11490  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::GetEnumerator()
0x11495  stloc.s  7
0x11497  br.s     loc_1150B
0x11499  ldloc.s  7
0x1149b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Current()
  ... truncated ...
```
