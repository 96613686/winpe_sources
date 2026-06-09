# Microsoft.Crm.Application.Components.UI.Button::Render

- ea: `0x15210`
- end: `0x15481`
- name: `Microsoft.Crm.Application.Components.UI.Button::Render`
- size: `625`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x15210`
- `0x23c20`
- `0x24120`
- `0x242c0`

## string_xrefs

- `0x15404`: `accesskey`

## pseudocode

```c

```

## disassembly

```asm
0x15210  ldarg.1
0x15211  ldstr    aButton// "<button"
0x15216  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1521b  ldarg.0
0x1521c  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x15221  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15226  brtrue.s loc_15239
0x15228  ldstr    aId// "id"
0x1522d  ldarg.0
0x1522e  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x15233  ldarg.1
0x15234  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x15239  ldstr    aOnclick_0// "onclick"
0x1523e  ldarg.0
0x1523f  ldfld    string Microsoft.Crm.Application.Components.UI.Button::_onClick
0x15244  ldarg.1
0x15245  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1524a  ldstr    aOnkeydown// "onkeydown"
0x1524f  ldarg.0
0x15250  ldfld    string Microsoft.Crm.Application.Components.UI.Button::_onKeyDown
0x15255  ldarg.1
0x15256  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1525b  ldstr    aType// "type"
0x15260  ldstr    aButton_0// "button"
0x15265  ldarg.1
0x15266  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1526b  ldarg.0
0x1526c  ldfld    int32 Microsoft.Crm.Application.Components.UI.Button::_width
0x15271  ldc.i4.0
0x15272  ble.s    loc_152A5
0x15274  ldarg.1
0x15275  ldstr    aStyleWidth// " style=\"width:"
0x1527a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1527f  ldarg.1
0x15280  ldarg.0
0x15281  ldflda   int32 Microsoft.Crm.Application.Components.UI.Button::_width
0x15286  ldstr    aD_1// "D"
0x1528b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15290  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x15295  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1529a  ldarg.1
0x1529b  ldstr    aPx// "px;\""
0x152a0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x152a5  ldarg.0
0x152a6  ldfld    string Microsoft.Crm.Application.Components.UI.Button::_cssClass
0x152ab  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x152b0  brtrue.s loc_152C5
0x152b2  ldstr    aClass_1// "class"
0x152b7  ldarg.0
0x152b8  ldfld    string Microsoft.Crm.Application.Components.UI.Button::_cssClass
0x152bd  ldarg.1
0x152be  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x152c3  br.s     loc_152E0
0x152c5  ldstr    aClass_1// "class"
0x152ca  ldstr    aMsCrmButton// "ms-crm-Button"
0x152cf  ldarg.1
0x152d0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x152d5  ldarg.0
0x152d6  ldstr    aMsCrmButton// "ms-crm-Button"
0x152db  stfld    string Microsoft.Crm.Application.Components.UI.Button::_cssClass
0x152e0  ldarg.0
0x152e1  ldfld    string Microsoft.Crm.Application.Components.UI.Button::_cssClass
0x152e6  ldstr    aMsCrmButton// "ms-crm-Button"
0x152eb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x152f0  brfalse.s loc_15312
0x152f2  ldstr    aOnmouseover// "onmouseover"
0x152f7  ldstr    aMscrmButtonuti// "Mscrm.ButtonUtils.hoverOn(this);"
0x152fc  ldarg.1
0x152fd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x15302  ldstr    aOnmouseout// "onmouseout"
0x15307  ldstr    aMscrmButtonuti_0// "Mscrm.ButtonUtils.hoverOff(this);"
0x1530c  ldarg.1
0x1530d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x15312  ldarg.0
0x15313  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x15318  ldc.i4.m1
0x15319  beq.s    loc_15346
0x1531b  ldarg.0
0x1531c  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x15321  brfalse.s loc_15346
0x15323  ldstr    aTabindex_1// "TabIndex"
0x15328  ldarg.0
0x15329  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x1532e  stloc.0
0x1532f  ldloca.s 0
0x15331  ldstr    aD_1// "D"
0x15336  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1533b  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x15340  ldarg.1
0x15341  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x15346  ldarg.0
0x15347  ldfld    string Microsoft.Crm.Application.Components.UI.Button::_title
0x1534c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15351  brtrue.s loc_15364
0x15353  ldstr    aTitle_4// "Title"
0x15358  ldarg.0
0x15359  ldfld    string Microsoft.Crm.Application.Components.UI.Button::_title
0x1535e  ldarg.1
0x1535f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x15364  ldarg.0
0x15365  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1536a  brfalse.s loc_15377
0x1536c  ldarg.1
0x1536d  ldstr    aDisabled_0// " disabled"
0x15372  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15377  ldarg.0
0x15378  ldfld    bool Microsoft.Crm.Application.Components.UI.Button::_hidden
0x1537d  brfalse.s loc_15390
0x1537f  ldarg.1
0x15380  ldstr    aStyle_0// "style"
0x15385  ldstr    aDisplayNone_0// "display:none;"
0x1538a  ldc.i4.0
0x1538b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x15390  ldarg.0
0x15391  call     instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x15396  callvirt instance class [mscorlib]System.Collections.ICollection [System.Web]System.Web.UI.CssStyleCollection::get_Keys()
0x1539b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x153a0  stloc.1
0x153a1  br.s     loc_153D8
0x153a3  ldloc.1
0x153a4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x153a9  castclass [mscorlib]System.String
0x153ae  stloc.2
0x153af  ldloc.2
0x153b0  ldstr    asc_4C90A// ":"
0x153b5  ldarg.0
0x153b6  call     instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x153bb  ldloc.2
0x153bc  callvirt instance string [System.Web]System.Web.UI.CssStyleCollection::get_Item(string)
0x153c1  ldstr    asc_43B56// ";"
0x153c6  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x153cb  stloc.3
0x153cc  ldstr    aStyle_0// "style"
0x153d1  ldloc.3
0x153d2  ldarg.1
0x153d3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x153d8  ldloc.1
0x153d9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x153de  brtrue.s loc_153A3
0x153e0  leave.s  loc_153F6
0x153e2  ldloc.1
0x153e3  isinst   [mscorlib]System.IDisposable
0x153e8  stloc.s  4
0x153ea  ldloc.s  4
0x153ec  brfalse.s loc_153F5
0x153ee  ldloc.s  4
0x153f0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x153f5  endfinally
0x153f6  ldarg.0
0x153f7  ldfld    string Microsoft.Crm.Application.Components.UI.Button::_accessKey
0x153fc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15401  brtrue.s loc_15415
0x15403  ldarg.1
0x15404  ldstr    aAccesskey_1// "accesskey"
0x15409  ldarg.0
0x1540a  ldfld    string Microsoft.Crm.Application.Components.UI.Button::_accessKey
0x1540f  ldc.i4.0
0x15410  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x15415  ldarg.1
0x15416  ldarg.0
0x15417  callvirt instance string Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Expandos()
0x1541c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15421  ldarg.1
0x15422  ldc.i4.s 0x3E
0x15424  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x15429  ldarg.0
0x1542a  ldfld    string Microsoft.Crm.Application.Components.UI.Button::_innerHtml
0x1542f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15434  brtrue.s loc_15444
0x15436  ldarg.1
0x15437  ldarg.0
0x15438  ldfld    string Microsoft.Crm.Application.Components.UI.Button::_innerHtml
0x1543d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15442  br.s     loc_15475
0x15444  ldarg.0
0x15445  ldfld    string Microsoft.Crm.Application.Components.UI.Button::_resourceId
0x1544a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1544f  brtrue.s loc_15469
0x15451  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15456  ldarg.0
0x15457  ldfld    string Microsoft.Crm.Application.Components.UI.Button::_resourceId
0x1545c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15461  ldarg.1
0x15462  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x15467  br.s     loc_15475
0x15469  ldarg.0
0x1546a  ldfld    string Microsoft.Crm.Application.Components.UI.Button::_text
0x1546f  ldarg.1
0x15470  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x15475  ldarg.1
0x15476  ldstr    aButton_1// "</button>"
0x1547b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x15480  ret
```
