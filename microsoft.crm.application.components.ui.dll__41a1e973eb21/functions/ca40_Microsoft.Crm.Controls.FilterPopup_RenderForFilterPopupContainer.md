# Microsoft.Crm.Controls.FilterPopup::RenderForFilterPopupContainer

- ea: `0xca40`
- end: `0xcdc8`
- name: `Microsoft.Crm.Controls.FilterPopup::RenderForFilterPopupContainer`
- size: `904`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0xc760`
- `0xe800`

## callees

- `0xca20`
- `0xca40`
- `0xffb0`
- `0x116d0`
- `0x11710`
- `0x11740`
- `0x11800`
- `0x118d0`
- `0x119e0`
- `0x11ab0`
- `0x11ad0`
- `0x1a0a0`
- `0x1a0d0`
- `0x1a350`
- `0x1a390`

## string_xrefs

- `0xcaa0`: `accessKey`

## pseudocode

```c

```

## disassembly

```asm
0xca40  ldarg.0
0xca41  ldstr    aMb// "_MB"
0xca46  call     instance void Microsoft.Crm.Controls.CommandBarControl::SetTestIdFromAction(string prefix)
0xca4b  ldarg.1
0xca4c  ldstr    aLi_0// "LI"
0xca51  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xca56  ldarg.1
0xca57  ldstr    aClass_1// "class"
0xca5c  ldstr    aMsCrmFilterpop_0// "ms-crm-FilterPopupMenu"
0xca61  ldc.i4.0
0xca62  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xca67  ldarg.1
0xca68  ldstr    aTabindex// "tabindex"
0xca6d  ldstr    a1_0// "-1"
0xca72  ldc.i4.0
0xca73  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xca78  ldstr    aMenu// "menu"
0xca7d  ldstr    aMnu// "mnu"
0xca82  ldarg.0
0xca83  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xca88  call     string [mscorlib]System.String::Concat(string, string)
0xca8d  ldarg.1
0xca8e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xca93  ldarg.0
0xca94  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_AccessKey()
0xca99  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xca9e  brtrue.s loc_CAB1
0xcaa0  ldstr    aAccesskey// "accessKey"
0xcaa5  ldarg.0
0xcaa6  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_AccessKey()
0xcaab  ldarg.1
0xcaac  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xcab1  ldarg.0
0xcab2  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xcab7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xcabc  brtrue.s loc_CACF
0xcabe  ldstr    aId// "id"
0xcac3  ldarg.0
0xcac4  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xcac9  ldarg.1
0xcaca  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xcacf  ldarg.0
0xcad0  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_ToolTip()
0xcad5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xcada  brtrue.s loc_CAED
0xcadc  ldstr    aTitle_2// "title"
0xcae1  ldarg.0
0xcae2  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_ToolTip()
0xcae7  ldarg.1
0xcae8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xcaed  ldarg.0
0xcaee  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Controls.CommandBarControl::get_CustomProperties()
0xcaf3  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0xcaf8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xcafd  stloc.0
0xcafe  br.s     loc_CB24
0xcb00  ldloc.0
0xcb01  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xcb06  stloc.1
0xcb07  ldloc.1
0xcb08  castclass [mscorlib]System.String
0xcb0d  ldarg.0
0xcb0e  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Controls.CommandBarControl::get_CustomProperties()
0xcb13  ldloc.1
0xcb14  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xcb19  castclass [mscorlib]System.String
0xcb1e  ldarg.1
0xcb1f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xcb24  ldloc.0
0xcb25  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xcb2a  brtrue.s loc_CB00
0xcb2c  leave.s  loc_CB3F
0xcb2e  ldloc.0
0xcb2f  isinst   [mscorlib]System.IDisposable
0xcb34  stloc.2
0xcb35  ldloc.2
0xcb36  brfalse.s loc_CB3E
0xcb38  ldloc.2
0xcb39  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcb3e  endfinally
0xcb3f  ldarg.1
0xcb40  ldc.i4.s 0x3E
0xcb42  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xcb47  ldarg.1
0xcb48  ldstr    aDiv_3// "DIV"
0xcb4d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xcb52  ldarg.1
0xcb53  ldstr    aClass_1// "class"
0xcb58  ldstr    aMsCrmFilterpop_1// "ms-crm-FilterPopupMenu-Label"
0xcb5d  ldc.i4.0
0xcb5e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xcb63  ldarg.1
0xcb64  ldc.i4.s 0x3E
0xcb66  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xcb6b  ldarg.1
0xcb6c  ldstr    aA_1// "A"
0xcb71  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xcb76  ldstr    aHref// "href"
0xcb7b  ldstr    aJavascriptVoid// "javascript:void(0)"
0xcb80  ldarg.1
0xcb81  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xcb86  ldarg.1
0xcb87  ldstr    aClass_1// "class"
0xcb8c  ldstr    aMsCrmFilterpop_1// "ms-crm-FilterPopupMenu-Label"
0xcb91  ldc.i4.0
0xcb92  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xcb97  ldstr    aTabindex_0// "tabIndex"
0xcb9c  ldarg.0
0xcb9d  call     instance string Microsoft.Crm.Controls.FilterPopup::get_TabIndex()
0xcba2  ldarg.1
0xcba3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xcba8  ldstr    aAriaLabel// "aria-label"
0xcbad  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xcbb2  ldstr    aFormEditorFilt// "Form_Editor_Filter_Caption"
0xcbb7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcbbc  ldarg.1
0xcbbd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xcbc2  ldarg.1
0xcbc3  ldc.i4.s 0x3E
0xcbc5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xcbca  ldarg.0
0xcbcb  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.CommandBarControl::get_Icon()
0xcbd0  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0xcbd5  brtrue   loc_CD0A
0xcbda  call     class Microsoft.Crm.Application.Components.UI.ImageStrip Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0xcbdf  ldarg.0
0xcbe0  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.CommandBarControl::get_Icon()
0xcbe5  callvirt instance class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri imagePath)
0xcbea  stloc.3
0xcbeb  ldarg.1
0xcbec  ldstr    aDiv_3// "DIV"
0xcbf1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xcbf6  ldarg.1
0xcbf7  ldstr    aClass_1// "class"
0xcbfc  ldstr    aMsCrmMenuFilte// "ms-crm-Menu-FilterImgWrapper"
0xcc01  ldc.i4.0
0xcc02  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xcc07  ldarg.1
0xcc08  ldc.i4.s 0x3E
0xcc0a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xcc0f  ldarg.1
0xcc10  ldstr    aImg// "IMG"
0xcc15  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xcc1a  ldstr    aSrc_0// "src"
0xcc1f  ldloc.3
0xcc20  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0xcc25  callvirt instance string [mscorlib]System.Object::ToString()
0xcc2a  ldarg.1
0xcc2b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xcc30  ldstr    aAlt// "alt"
0xcc35  ldarg.0
0xcc36  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_ToolTip()
0xcc3b  ldarg.1
0xcc3c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xcc41  ldarg.1
0xcc42  ldstr    aId// "id"
0xcc47  ldstr    aMnudown// "mnuDown"
0xcc4c  ldc.i4.0
0xcc4d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xcc52  ldarg.1
0xcc53  ldstr    aRole// "role"
0xcc58  ldstr    aApplication// "application"
0xcc5d  ldc.i4.0
0xcc5e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xcc63  ldarg.1
0xcc64  ldstr    aClass_1// "class"
0xcc69  ldstr    aMsCrmMenuButto// "ms-crm-Menu-ButtonFilter "
0xcc6e  ldloc.3
0xcc6f  callvirt instance string Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0xcc74  call     string [mscorlib]System.String::Concat(string, string)
0xcc79  ldc.i4.0
0xcc7a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xcc7f  ldarg.0
0xcc80  call     instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0xcc85  callvirt instance int32 [System.Web]System.Web.UI.CssStyleCollection::get_Count()
0xcc8a  ldc.i4.0
0xcc8b  ble.s    loc_CCF7
0xcc8d  ldarg.0
0xcc8e  call     instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0xcc93  callvirt instance class [mscorlib]System.Collections.ICollection [System.Web]System.Web.UI.CssStyleCollection::get_Keys()
0xcc98  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xcc9d  stloc.s  4
0xcc9f  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xcca4  stloc.s  5
0xcca6  ldsfld   string [mscorlib]System.String::Empty
0xccab  stloc.s  6
0xccad  br.s     loc_CCD9
0xccaf  ldloc.s  4
0xccb1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xccb6  castclass [mscorlib]System.String
0xccbb  stloc.s  6
0xccbd  ldloc.s  5
0xccbf  ldstr    a01_1// "{0}:{1};"
0xccc4  ldloc.s  6
0xccc6  ldarg.0
0xccc7  call     instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0xcccc  ldloc.s  6
0xccce  callvirt instance string [System.Web]System.Web.UI.CssStyleCollection::get_Item(string)
0xccd3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0xccd8  pop
0xccd9  ldloc.s  4
0xccdb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xcce0  brtrue.s loc_CCAF
0xcce2  ldstr    aStyle_0// "style"
0xcce7  ldloc.s  5
0xcce9  callvirt instance string [mscorlib]System.Object::ToString()
0xccee  ldarg.1
0xccef  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xccf4  ldnull
0xccf5  stloc.s  5
0xccf7  ldarg.1
0xccf8  ldc.i4.s 0x3E
0xccfa  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xccff  ldarg.1
0xcd00  ldstr    aDiv_3// "DIV"
0xcd05  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0xcd0a  ldarg.0
0xcd0b  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_Title()
0xcd10  brfalse  loc_CD9A
0xcd15  ldarg.0
0xcd16  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_Title()
0xcd1b  callvirt instance int32 [mscorlib]System.String::get_Length()
0xcd20  ldc.i4.0
0xcd21  ble.s    loc_CD9A
0xcd23  ldarg.1
0xcd24  ldstr    aSpan_0// "SPAN"
0xcd29  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xcd2e  ldstr    aClass_1// "class"
0xcd33  ldstr    aMsCrmMenuitemT// "ms-crm-MenuItem-Text"
0xcd38  ldarg.0
0xcd39  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.CommandBarControl::get_Icon()
0xcd3e  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0xcd43  ldc.i4.0
0xcd44  ceq
0xcd46  ldarg.0
0xcd47  call     instance bool Microsoft.Crm.Controls.CommandBarPopup::get_DownArrow()
0xcd4c  call     string Microsoft.Crm.Controls.CommandBarButton::GetTextClassVariant(bool isIcon, bool isDownArrow)
0xcd51  call     string [mscorlib]System.String::Concat(string, string)
0xcd56  ldarg.1
0xcd57  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xcd5c  ldarg.1
0xcd5d  ldc.i4.s 0x3E
0xcd5f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xcd64  ldarg.1
0xcd65  ldarg.0
0xcd66  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_Title()
0xcd6b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xcd70  ldarg.0
0xcd71  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_AccessKey()
0xcd76  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xcd7b  ldstr    aU// "<u>"
0xcd80  ldstr    aU_0// "</u>"
0xcd85  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::StringInjector(string, string, string, string)
0xcd8a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xcd8f  ldarg.1
0xcd90  ldstr    aSpan_0// "SPAN"
0xcd95  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0xcd9a  ldarg.1
0xcd9b  ldstr    aA_1// "A"
0xcda0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0xcda5  ldarg.1
0xcda6  ldstr    aDiv_3// "DIV"
0xcdab  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0xcdb0  ldarg.0
0xcdb1  call     instance class Microsoft.Crm.Controls.Menu Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0xcdb6  ldarg.1
0xcdb7  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0xcdbc  ldarg.1
0xcdbd  ldstr    aLi_0// "LI"
0xcdc2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0xcdc7  ret
```
