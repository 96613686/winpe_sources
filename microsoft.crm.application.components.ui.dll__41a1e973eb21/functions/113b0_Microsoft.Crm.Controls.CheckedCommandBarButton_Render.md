# Microsoft.Crm.Controls.CheckedCommandBarButton::Render

- ea: `0x113b0`
- end: `0x1167a`
- name: `Microsoft.Crm.Controls.CheckedCommandBarButton::Render`
- size: `714`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0xfe60`
- `0x113b0`
- `0x116d0`
- `0x116f0`
- `0x11740`
- `0x11800`
- `0x118d0`
- `0x119e0`
- `0x155d0`

## string_xrefs

- `0x11514`: `ms-crm-MenuLink`

## pseudocode

```c

```

## disassembly

```asm
0x113b0  ldarg.0
0x113b1  callvirt instance bool [System.Web]System.Web.UI.Control::get_Visible()
0x113b6  brtrue.s loc_113B9
0x113b8  ret
0x113b9  ldarg.0
0x113ba  ldstr    aMi// "_MI"
0x113bf  ldarg.0
0x113c0  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Controls.CommandBarControl::get_CustomProperties()
0x113c5  ldstr    aGridid// "gridid"
0x113ca  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x113cf  call     string [mscorlib]System.String::Concat(object, object)
0x113d4  call     instance void Microsoft.Crm.Controls.CommandBarControl::SetTestIdFromAction(string prefix)
0x113d9  ldarg.1
0x113da  ldstr    aLi_0// "LI"
0x113df  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x113e4  ldarg.1
0x113e5  ldstr    aTabindex_0// "tabIndex"
0x113ea  ldstr    a1_0// "-1"
0x113ef  ldc.i4.0
0x113f0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x113f5  ldarg.0
0x113f6  call     instance valuetype CommandBarButtonStyle Microsoft.Crm.Controls.CommandBarButton::get_ButtonStyle()
0x113fb  ldc.i4.2
0x113fc  beq.s    loc_1140F
0x113fe  ldstr    aAction// "action"
0x11403  ldarg.0
0x11404  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_Action()
0x11409  ldarg.1
0x1140a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1140f  ldarg.0
0x11410  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Controls.CommandBarControl::get_CustomProperties()
0x11415  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0x1141a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x1141f  stloc.0
0x11420  br.s     loc_11446
0x11422  ldloc.0
0x11423  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x11428  stloc.1
0x11429  ldloc.1
0x1142a  castclass [mscorlib]System.String
0x1142f  ldarg.0
0x11430  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Controls.CommandBarControl::get_CustomProperties()
0x11435  ldloc.1
0x11436  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x1143b  castclass [mscorlib]System.String
0x11440  ldarg.1
0x11441  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x11446  ldloc.0
0x11447  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1144c  brtrue.s loc_11422
0x1144e  leave.s  loc_11461
0x11450  ldloc.0
0x11451  isinst   [mscorlib]System.IDisposable
0x11456  stloc.2
0x11457  ldloc.2
0x11458  brfalse.s loc_11460
0x1145a  ldloc.2
0x1145b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11460  endfinally
0x11461  ldarg.0
0x11462  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_AccessKey()
0x11467  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1146c  brtrue.s loc_1147F
0x1146e  ldstr    aKey// "key"
0x11473  ldarg.0
0x11474  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_AccessKey()
0x11479  ldarg.1
0x1147a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1147f  ldarg.0
0x11480  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x11485  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1148a  brtrue.s loc_1149D
0x1148c  ldstr    aId// "id"
0x11491  ldarg.0
0x11492  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x11497  ldarg.1
0x11498  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1149d  ldarg.1
0x1149e  ldstr    aClass_1// "class"
0x114a3  ldarg.0
0x114a4  call     instance valuetype CommandBarButtonStyle Microsoft.Crm.Controls.CommandBarButton::get_ButtonStyle()
0x114a9  ldc.i4.2
0x114aa  beq.s    loc_114B3
0x114ac  ldstr    aMsCrmMenuitemL// "ms-crm-MenuItem-Label"
0x114b1  br.s     loc_114B8
0x114b3  ldstr    aMsCrmGroupSpac// "ms-crm-Group-Spacer"
0x114b8  ldc.i4.0
0x114b9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x114be  ldarg.1
0x114bf  ldc.i4.s 0x3E
0x114c1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x114c6  ldarg.1
0x114c7  ldstr    aSpan_0// "SPAN"
0x114cc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x114d1  ldarg.1
0x114d2  ldstr    aClass_1// "class"
0x114d7  ldarg.0
0x114d8  call     instance valuetype CommandBarButtonStyle Microsoft.Crm.Controls.CommandBarButton::get_ButtonStyle()
0x114dd  ldc.i4.2
0x114de  beq.s    loc_114E7
0x114e0  ldstr    aMsCrmMenuitemL// "ms-crm-MenuItem-Label"
0x114e5  br.s     loc_114EC
0x114e7  ldstr    aMsCrmMenuGroup// "ms-crm-Menu-Group"
0x114ec  ldc.i4.0
0x114ed  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x114f2  ldarg.1
0x114f3  ldc.i4.s 0x3E
0x114f5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x114fa  ldarg.0
0x114fb  call     instance valuetype CommandBarButtonStyle Microsoft.Crm.Controls.CommandBarButton::get_ButtonStyle()
0x11500  ldc.i4.2
0x11501  beq.s    loc_1155A
0x11503  ldarg.1
0x11504  ldstr    aA_1// "A"
0x11509  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x1150e  ldarg.1
0x1150f  ldstr    aClass_1// "class"
0x11514  ldstr    aMsCrmMenulink// "ms-crm-MenuLink"
0x11519  ldc.i4.0
0x1151a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1151f  ldarg.1
0x11520  ldstr    aHref// "href"
0x11525  ldstr    aJavascriptVoid_0// "javascript:void(0);"
0x1152a  ldc.i4.0
0x1152b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11530  ldarg.1
0x11531  ldstr    aTabindex_0// "tabIndex"
0x11536  ldstr    a1_0// "-1"
0x1153b  ldc.i4.0
0x1153c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11541  ldarg.1
0x11542  ldstr    aTarget// "target"
0x11547  ldstr    aSelf// "_self"
0x1154c  ldc.i4.0
0x1154d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x11552  ldarg.1
0x11553  ldc.i4.s 0x3E
0x11555  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x1155a  ldarg.1
0x1155b  ldstr    aSpan_0// "SPAN"
0x11560  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x11565  ldarg.1
0x11566  ldc.i4.s 0x3E
0x11568  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x1156d  ldarg.0
0x1156e  ldfld    class Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Controls.CheckedCommandBarButton::_checkBox
0x11573  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x11578  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1157d  brtrue.s loc_1159B
0x1157f  ldarg.0
0x11580  ldfld    class Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Controls.CheckedCommandBarButton::_checkBox
0x11585  ldstr    aMsCrmMenuitemI// "ms-crm-MenuItem-Input"
0x1158a  callvirt instance void Microsoft.Crm.Application.Components.UI.CheckBox::set_ClassName(string value)
0x1158f  ldarg.0
0x11590  ldfld    class Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Controls.CheckedCommandBarButton::_checkBox
0x11595  ldarg.1
0x11596  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x1159b  ldarg.1
0x1159c  ldstr    aSpan_0// "SPAN"
0x115a1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x115a6  ldarg.0
0x115a7  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x115ac  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x115b1  brtrue   loc_1164F
0x115b6  ldarg.1
0x115b7  ldstr    aSpan_0// "SPAN"
0x115bc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x115c1  ldarg.1
0x115c2  ldstr    aTabindex_0// "tabIndex"
0x115c7  ldarg.0
0x115c8  call     instance valuetype CommandBarButtonStyle Microsoft.Crm.Controls.CommandBarButton::get_ButtonStyle()
0x115cd  ldc.i4.2
0x115ce  beq.s    loc_115D7
0x115d0  ldstr    a0// "0"
0x115d5  br.s     loc_115DC
0x115d7  ldstr    a1_0// "-1"
0x115dc  ldc.i4.0
0x115dd  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x115e2  ldarg.1
0x115e3  ldstr    aClass_1// "class"
0x115e8  ldstr    aMsCrmMenuitemT// "ms-crm-MenuItem-Text"
0x115ed  ldc.i4.0
0x115ee  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x115f3  ldarg.0
0x115f4  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_ToolTip()
0x115f9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x115fe  brtrue.s loc_11611
0x11600  ldstr    aTitle_2// "title"
0x11605  ldarg.0
0x11606  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_ToolTip()
0x1160b  ldarg.1
0x1160c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x11611  ldarg.1
0x11612  ldc.i4.s 0x3E
0x11614  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x11619  ldarg.1
0x1161a  ldarg.0
0x1161b  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x11620  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x11625  ldarg.0
0x11626  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_AccessKey()
0x1162b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x11630  ldstr    aU// "<u>"
0x11635  ldstr    aU_0// "</u>"
0x1163a  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::StringInjector(string, string, string, string)
0x1163f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x11644  ldarg.1
0x11645  ldstr    aSpan_0// "SPAN"
0x1164a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x1164f  ldarg.0
0x11650  call     instance valuetype CommandBarButtonStyle Microsoft.Crm.Controls.CommandBarButton::get_ButtonStyle()
0x11655  ldc.i4.2
0x11656  beq.s    loc_11663
0x11658  ldarg.1
0x11659  ldstr    aA_1// "A"
0x1165e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x11663  ldarg.1
0x11664  ldstr    aSpan_0// "SPAN"
0x11669  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x1166e  ldarg.1
0x1166f  ldstr    aLi_0// "LI"
0x11674  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x11679  ret
```
