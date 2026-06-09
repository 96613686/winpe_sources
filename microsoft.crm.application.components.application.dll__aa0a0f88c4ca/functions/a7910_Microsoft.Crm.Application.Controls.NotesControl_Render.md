# Microsoft.Crm.Application.Controls.NotesControl::Render

- ea: `0xa7910`
- end: `0xa7bdd`
- name: `Microsoft.Crm.Application.Controls.NotesControl::Render`
- size: `717`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x26370`
- `0x8d1a0`
- `0xa7590`
- `0xa75b0`
- `0xa75d0`
- `0xa7610`
- `0xa7680`
- `0xa7890`
- `0xa7910`
- `0xa7be0`
- `0xa7c50`

## string_xrefs

- `0xa7965`: `Notes.No.Access`
- `0xa7a24`: `DisableNotesForDuplicateDetectedEntityCreate`
- `0xa7bbf`: `" notesxml="`

## pseudocode

```c

```

## disassembly

```asm
0xa7910  ldarg.0
0xa7911  call     instance valuetype Microsoft.Crm.Application.Forms.FormControlRenderMode Microsoft.Crm.Application.Controls.NotesControl::get_RenderMode()
0xa7916  brtrue.s loc_A7920
0xa7918  ldarg.0
0xa7919  ldarg.1
0xa791a  call     instance void Microsoft.Crm.Application.Controls.NotesControl::RenderForPrinting(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xa791f  ret
0xa7920  ldarg.0
0xa7921  call     instance valuetype Microsoft.Crm.Application.Forms.FormControlRenderMode Microsoft.Crm.Application.Controls.NotesControl::get_RenderMode()
0xa7926  ldc.i4.1
0xa7927  bne.un.s loc_A7931
0xa7929  ldarg.0
0xa792a  ldarg.1
0xa792b  call     instance void Microsoft.Crm.Application.Controls.NotesControl::RenderForRead(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xa7930  ret
0xa7931  ldarg.0
0xa7932  call     instance valuetype Microsoft.Crm.Application.Forms.FormControlRenderMode Microsoft.Crm.Application.Controls.NotesControl::get_RenderMode()
0xa7937  ldc.i4.7
0xa7938  bne.un.s loc_A7942
0xa793a  ldarg.0
0xa793b  ldarg.1
0xa793c  call     instance void Microsoft.Crm.Application.Controls.NotesControl::RenderForWorkFlow(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xa7941  ret
0xa7942  ldarg.1
0xa7943  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xa7948  stloc.0
0xa7949  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa794e  stloc.1
0xa794f  ldc.i4.0
0xa7950  stloc.2
0xa7951  ldnull
0xa7952  stloc.3
0xa7953  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadNote()
0xa7958  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa795d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa7962  brtrue.s loc_A7972
0xa7964  ldloc.1
0xa7965  ldstr    aNotesNoAccess// "Notes.No.Access"
0xa796a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa796f  stloc.3
0xa7970  ldc.i4.1
0xa7971  stloc.2
0xa7972  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xa7977  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xa797c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xa7981  ldstr    aItotal// "iTotal"
0xa7986  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xa798b  brfalse.s loc_A79A3
0xa798d  ldarg.0
0xa798e  ldfld    bool Microsoft.Crm.Application.Controls.NotesControl::_allowBulkEdit
0xa7993  brtrue.s loc_A79A3
0xa7995  ldloc.1
0xa7996  ldstr    aNotesBulkeditD// "Notes.BulkEdit.Disabled"
0xa799b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa79a0  stloc.3
0xa79a1  ldc.i4.1
0xa79a2  stloc.2
0xa79a3  ldloc.2
0xa79a4  brfalse.s loc_A79C4
0xa79a6  ldloc.0
0xa79a7  ldstr    aDivStyleBorder// "<div style=\"border:1px solid #6699cc;h"...
0xa79ac  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa79b1  ldloc.3
0xa79b2  ldloc.0
0xa79b3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0xa79b8  ldloc.0
0xa79b9  ldstr    aDiv_1// "</div>"
0xa79be  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa79c3  ret
0xa79c4  ldstr    aControlsNotesN// "/_controls/notes/notesdata.aspx"
0xa79c9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa79ce  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa79d3  stloc.s  4
0xa79d5  ldarg.0
0xa79d6  call     instance int32 Microsoft.Crm.Application.Controls.NotesControl::get_ParentEntity()
0xa79db  ldc.i4.0
0xa79dc  cgt.un
0xa79de  ldstr    aParententityIs// "ParentEntity is not set."
0xa79e3  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0xa79e8  ldloc.s  4
0xa79ea  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xa79ef  ldstr    aId_1// "id"
0xa79f4  ldarg.0
0xa79f5  call     instance string Microsoft.Crm.Application.Controls.NotesControl::get_ParentEntityId()
0xa79fa  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa79ff  ldloc.s  4
0xa7a01  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xa7a06  ldstr    aParententity// "ParentEntity"
0xa7a0b  ldarg.0
0xa7a0c  call     instance int32 Microsoft.Crm.Application.Controls.NotesControl::get_ParentEntity()
0xa7a11  stloc.s  7
0xa7a13  ldloca.s 7
0xa7a15  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa7a1a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa7a1f  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7a24  ldstr    aDisablenotesfo// "DisableNotesForDuplicateDetectedEntityC"...
0xa7a29  ldc.i4.0
0xa7a2a  box      [mscorlib]System.Int32
0xa7a2f  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xa7a34  unbox.any [mscorlib]System.Int32
0xa7a39  stloc.s  5
0xa7a3b  ldarg.0
0xa7a3c  call     instance bool Microsoft.Crm.Application.Controls.NotesControl::get_ReadOnly()
0xa7a41  brtrue   loc_A7AE9
0xa7a46  ldarg.0
0xa7a47  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Controls.NotesControl::get_DataSource()
0xa7a4c  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0xa7a51  brfalse.s loc_A7A6A
0xa7a53  ldarg.0
0xa7a54  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Controls.NotesControl::get_DataSource()
0xa7a59  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0xa7a5e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsDuplicateCheckSupported()
0xa7a63  brfalse.s loc_A7A6A
0xa7a65  ldloc.s  5
0xa7a67  ldc.i4.1
0xa7a68  beq.s    loc_A7AE9
0xa7a6a  ldarg.0
0xa7a6b  ldfld    bool Microsoft.Crm.Application.Controls.NotesControl::_enableInlineEdit
0xa7a70  brfalse.s loc_A7A88
0xa7a72  ldloc.s  4
0xa7a74  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xa7a79  ldstr    aEnableinlineed// "EnableInlineEdit"
0xa7a7e  ldstr    aTrue// "true"
0xa7a83  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7a88  ldc.i4.1
0xa7a89  stloc.s  8
0xa7a8b  ldarg.0
0xa7a8c  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xa7a91  isinst   Microsoft.Crm.Application.Controls.AppPage
0xa7a96  stloc.s  9
0xa7a98  ldloc.s  9
0xa7a9a  brfalse.s loc_A7AC8
0xa7a9c  ldloc.s  9
0xa7a9e  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0xa7aa3  isinst   Microsoft.Crm.Application.Forms.EndUserForm
0xa7aa8  stloc.s  0xA
0xa7aaa  ldloc.s  0xA
0xa7aac  brfalse.s loc_A7AC8
0xa7aae  ldloc.s  0xA
0xa7ab0  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Forms.AppForm::get_PrivilegeCheck()
0xa7ab5  brfalse.s loc_A7AC8
0xa7ab7  ldloc.s  0xA
0xa7ab9  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Application.Forms.AppForm::get_PrivilegeCheck()
0xa7abe  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanAppend()
0xa7ac3  brtrue.s loc_A7AC8
0xa7ac5  ldc.i4.0
0xa7ac6  stloc.s  8
0xa7ac8  ldarg.0
0xa7ac9  ldfld    bool Microsoft.Crm.Application.Controls.NotesControl::_enableInsert
0xa7ace  ldloc.s  8
0xa7ad0  and
0xa7ad1  brfalse.s loc_A7AE9
0xa7ad3  ldloc.s  4
0xa7ad5  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xa7ada  ldstr    aEnableinsert// "EnableInsert"
0xa7adf  ldstr    aTrue// "true"
0xa7ae4  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7ae9  ldarg.0
0xa7aea  ldfld    bool Microsoft.Crm.Application.Controls.NotesControl::_ascending
0xa7aef  brfalse.s loc_A7B07
0xa7af1  ldloc.s  4
0xa7af3  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xa7af8  ldstr    aAscending// "Ascending"
0xa7afd  ldstr    aTrue// "true"
0xa7b02  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xa7b07  ldsfld   string [mscorlib]System.String::Empty
0xa7b0c  stloc.s  6
0xa7b0e  ldarg.0
0xa7b0f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Controls.NotesControl::get_DataSource()
0xa7b14  callvirt instance class [System.Xml]System.Xml.XPath.IXPathNavigable [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_NotesXml()
0xa7b19  brfalse.s loc_A7B32
0xa7b1b  ldarg.0
0xa7b1c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Controls.NotesControl::get_DataSource()
0xa7b21  callvirt instance class [System.Xml]System.Xml.XPath.IXPathNavigable [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_NotesXml()
0xa7b26  castclass [System.Xml]System.Xml.XmlNode
0xa7b2b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0xa7b30  stloc.s  6
0xa7b32  ldloc.0
0xa7b33  ldstr    aIframeId// "<iframe id=\""
0xa7b38  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa7b3d  ldarg.0
0xa7b3e  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xa7b43  ldloc.0
0xa7b44  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0xa7b49  ldloc.0
0xa7b4a  ldstr    aName_4// "\" name=\""
0xa7b4f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa7b54  ldarg.0
0xa7b55  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xa7b5a  ldloc.0
0xa7b5b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0xa7b60  ldloc.0
0xa7b61  ldstr    aTabindex_1// "\" tabIndex=\""
0xa7b66  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa7b6b  ldloc.0
0xa7b6c  ldarg.0
0xa7b6d  ldflda   int32 Microsoft.Crm.Application.Controls.NotesControl::_tabIndex
0xa7b72  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa7b77  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa7b7c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa7b81  ldloc.0
0xa7b82  ldstr    aClassNotedataS// "\" class=\"noteData\" style=\"width:100"...
0xa7b87  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa7b8c  ldstr    aStaticBlankHtm// "/_static/blank.htm"
0xa7b91  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa7b96  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa7b9b  callvirt instance string [mscorlib]System.Object::ToString()
0xa7ba0  ldloc.0
0xa7ba1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0xa7ba6  ldloc.0
0xa7ba7  ldstr    aUrl_1// "\" Url=\""
0xa7bac  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa7bb1  ldloc.s  4
0xa7bb3  callvirt instance string [mscorlib]System.Object::ToString()
0xa7bb8  ldloc.0
0xa7bb9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0xa7bbe  ldloc.0
0xa7bbf  ldstr    aNotesxml// "\" notesxml=\""
0xa7bc4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa7bc9  ldloc.s  6
0xa7bcb  ldloc.0
0xa7bcc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string, class [mscorlib]System.IO.TextWriter)
0xa7bd1  ldloc.0
0xa7bd2  ldstr    aIframe_3// "\"></iframe>"
0xa7bd7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa7bdc  ret
```
