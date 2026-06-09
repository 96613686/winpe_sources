# Microsoft.Crm.Application.Controls.NotesDataControl::RenderNoteData

- ea: `0xa88e0`
- end: `0xa9589`
- name: `Microsoft.Crm.Application.Controls.NotesDataControl::RenderNoteData`
- size: `3241`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0xa87f0`
- `0xa8850`

## callees

- `0x80770`
- `0x80c20`
- `0xa8420`
- `0xa86c0`
- `0xa88e0`
- `0xa9590`
- `0xa9670`
- `0xa9710`

## string_xrefs

- `0xa891c`: `Notes.No.Access`
- `0xa8950`: `<columnset><column>annotationid</column><column>notetext</column><column>subject</column><column>createdon</column>\n					<column>modifiedon</column><column>createdby</column><column>modifiedby</column>\n					<column>isdocument</column><column>filename</column><column>filesize</column>{0}</columnset>`
- `0xa8961`: `<descend>createdon</descend>`
- `0xa8968`: `<ascend>createdon</ascend>`
- `0xa8af2`: `wrpcTokenAsQueryString`
- `0xa8b39`: `noteWritePermission`
- `0xa8c2e`: `DeleteText`
- `0xa8c34`: `NotesV2.DeleteNoteTitle`
- `0xa9413`: `NotesV2.DeleteNoteTitle`
- `0xa8c49`: `<a href="#" onclick="openObj(8, '{0}');" tabIndex="0" class="ms-crm-NotesUserLink">{1}</a>`
- `0xa8cb1`: `currentUserLink`
- `0xa8e59`: `" noDelete="true`
- `0xa90d1`: `contenteditable="false" readonly `
- `0xa92fc`: `<a href="#" onclick="openObj(8, '{0}');" tabIndex="0" class="ms-crm-NotesUserLink" {2}>{1}</a>`
- `0xa93d4`: `<td class="NotesDataControl_Render_td3 modifyLinkCell"><span style="visibility: hidden;">`
- `0xa93ed`: `<a href="#" class="NoteActionLink" onclick="$find('`
- `0xa94e9`: `<a href="#" class="NoteActionLink" onclick="$find('`
- `0xa9401`: `').deleteCurrentNote(new Sys.UI.DomEvent(event));" > `
- `0xa9441`: `/_imgs/grid/actions_delete_16.png`
- `0xa94fd`: `').openNote(new Sys.UI.DomEvent(event), this);"><img alt="{0}" title="{0}"`

## pseudocode

```c

```

## disassembly

```asm
0xa88e0  ldnull
0xa88e1  stloc.0
0xa88e2  ldc.i4.5
0xa88e3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa88e8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa88ed  stloc.1
0xa88ee  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa88f3  stloc.2
0xa88f4  ldc.i4.0
0xa88f5  stloc.3
0xa88f6  ldarg.0
0xa88f7  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xa88fc  stloc.s  4
0xa88fe  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadNote()
0xa8903  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa8908  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa890d  brtrue.s loc_A893E
0xa890f  ldloc.s  4
0xa8911  ldstr    aDivStyleBorder_1// "<div style=\"border:1px solid #6699cc;w"...
0xa8916  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa891b  ldloc.2
0xa891c  ldstr    aNotesNoAccess// "Notes.No.Access"
0xa8921  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8926  ldloc.s  4
0xa8928  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0xa892d  ldloc.s  4
0xa892f  ldstr    aDiv_1// "</div>"
0xa8934  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa8939  leave    loc_A9588
0xa893e  ldarg.s  6
0xa8940  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa8945  ldc.i4.0
0xa8946  ble      loc_A89E9
0xa894b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa8950  ldstr    aColumnsetColum_3// "<columnset><column>annotationid</column"...
0xa8955  ldc.i4.1
0xa8956  newarr   [mscorlib]System.Object
0xa895b  dup
0xa895c  ldc.i4.0
0xa895d  ldarg.s  8
0xa895f  brtrue.s loc_A8968
0xa8961  ldstr    aDescendCreated// "<descend>createdon</descend>"
0xa8966  br.s     loc_A896D
0xa8968  ldstr    aAscendCreatedo// "<ascend>createdon</ascend>"
0xa896d  stelem.ref
0xa896e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa8973  stloc.s  8
0xa8975  ldnull
0xa8976  stloc.s  9
0xa8978  ldarg.1
0xa8979  brfalse.s loc_A898A
0xa897b  ldarg.s  6
0xa897d  ldloc.s  8
0xa897f  ldarg.s  4
0xa8981  call     string Microsoft.Crm.Application.Controls.NotesDataControl::RetrieveByObject(string parentId, string columnSet, int32 pageNumber)
0xa8986  stloc.s  9
0xa8988  br.s     loc_A89A4
0xa898a  ldarg.3
0xa898b  brtrue.s loc_A899D
0xa898d  ldstr    aNoteIsNotSuppo// "Note is not supported on this entity"
0xa8992  ldc.i4   0x8004023B
0xa8997  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xa899c  throw
0xa899d  ldsfld   string [mscorlib]System.String::Empty
0xa89a2  stloc.s  9
0xa89a4  ldloc.s  9
0xa89a6  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0xa89ab  stloc.s  0xA
0xa89ad  ldloc.s  0xA
0xa89af  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa89b4  brfalse.s loc_A89DC
0xa89b6  ldloc.s  0xA
0xa89b8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa89bd  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa89c2  ldstr    aMorerecords// "morerecords"
0xa89c7  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xa89cc  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xa89d1  ldstr    a1_0// "1"
0xa89d6  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa89db  stloc.3
0xa89dc  ldloc.s  0xA
0xa89de  ldstr    aAnnotationsAnn// "/annotations/annotation"
0xa89e3  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xa89e8  stloc.0
0xa89e9  ldarg.2
0xa89ea  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0xa89ef  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xa89f4  stloc.s  5
0xa89f6  ldloc.s  4
0xa89f8  ldstr    aDivClassNotesc// "<div class=\"notesContainerScrollDiv\" "...
0xa89fd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa8a02  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xa8a07  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xa8a0c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsIosDevice(class [System.Web]System.Web.HttpRequest)
0xa8a11  brfalse.s loc_A8A21
0xa8a13  ldloc.s  4
0xa8a15  ldstr    aDivClassNotesc_0// "<div class=\"notesContainerDiv\" "
0xa8a1a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa8a1f  br.s     loc_A8A2D
0xa8a21  ldloc.s  4
0xa8a23  ldstr    aDiv_6// "<div "
0xa8a28  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa8a2d  ldarg.3
0xa8a2e  brfalse.s loc_A8A3E
0xa8a30  ldloc.s  4
0xa8a32  ldstr    aStyleHeightAut// " style=\"height:auto;width:100%;\""
0xa8a37  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa8a3c  br.s     loc_A8A7E
0xa8a3e  ldloc.s  4
0xa8a40  ldc.i4.5
0xa8a41  newarr   [mscorlib]System.String
0xa8a46  dup
0xa8a47  ldc.i4.0
0xa8a48  ldstr    aOnkeypressFind// "onkeypress=\"$find('"
0xa8a4d  stelem.ref
0xa8a4e  dup
0xa8a4f  ldc.i4.1
0xa8a50  ldloc.s  5
0xa8a52  stelem.ref
0xa8a53  dup
0xa8a54  ldc.i4.2
0xa8a55  ldstr    aDiveventbubble// "').divEventBubble(new Sys.UI.DomEvent(e"...
0xa8a5a  stelem.ref
0xa8a5b  dup
0xa8a5c  ldc.i4.3
0xa8a5d  ldloc.s  5
0xa8a5f  stelem.ref
0xa8a60  dup
0xa8a61  ldc.i4.4
0xa8a62  ldstr    aDiveventbubble_0// "').divEventBubble(new Sys.UI.DomEvent(e"...
0xa8a67  stelem.ref
0xa8a68  call     string [mscorlib]System.String::Concat(string[])
0xa8a6d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa8a72  ldloc.s  4
0xa8a74  ldstr    aStyleOverflowY// " style=\"overflow-y:visible;overflow-x:"...
0xa8a79  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa8a7e  ldloc.s  4
0xa8a80  ldstr    asc_111CB6// ">"
0xa8a85  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa8a8a  ldarg.3
0xa8a8b  brtrue.s loc_A8A94
0xa8a8d  ldarg.s  8
0xa8a8f  ldc.i4.0
0xa8a90  ceq
0xa8a92  br.s     loc_A8A95
0xa8a94  ldc.i4.0
0xa8a95  ldarg.s  0xA
0xa8a97  and
0xa8a98  ldarg.s  9
0xa8a9a  and
0xa8a9b  brfalse.s loc_A8AA9
0xa8a9d  ldloc.s  4
0xa8a9f  ldarg.2
0xa8aa0  ldarg.s  5
0xa8aa2  ldarg.s  0xC
0xa8aa4  call     void Microsoft.Crm.Application.Controls.NotesDataControl::RenderNotesCreator(class [mscorlib]System.IO.TextWriter writer, string ID, int32 ParentEntity, int32 notch)
0xa8aa9  ldloc.s  4
0xa8aab  ldstr    aTableCellspaci_7// "<table cellspacing=\"0\" cellpadding=\""...
0xa8ab0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xa8ab5  ldstr    aId_1// "id"
0xa8aba  ldarg.2
0xa8abb  ldarg.0
0xa8abc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa8ac1  ldstr    aMorerecords_0// "moreRecords"
0xa8ac6  ldloc.3
0xa8ac7  brtrue.s loc_A8AD0
0xa8ac9  ldstr    a0// "0"
0xa8ace  br.s     loc_A8AD5
0xa8ad0  ldstr    a1_0// "1"
0xa8ad5  ldarg.0
0xa8ad6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa8adb  ldstr    aPagenumber_0// "pageNumber"
0xa8ae0  ldarga.s 4
0xa8ae2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa8ae7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa8aec  ldarg.0
0xa8aed  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa8af2  ldstr    aWrpctokenasque// "wrpcTokenAsQueryString"
0xa8af7  ldarg.s  0xB
0xa8af9  ldarg.0
0xa8afa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa8aff  ldloc.2
0xa8b00  ldstr    aWebNotesEditAs// "Web.Notes.edit.aspx_97"
0xa8b05  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8b0a  stloc.s  6
0xa8b0c  ldloc.2
0xa8b0d  ldstr    aNotesLabelTitl// "Notes_Label_TitleLabelandText"
0xa8b12  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8b17  stloc.s  7
0xa8b19  ldarg.3
0xa8b1a  brtrue   loc_A8CC3
0xa8b1f  ldstr    aUserid_1// "userId"
0xa8b24  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xa8b29  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0xa8b2e  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0xa8b33  ldarg.0
0xa8b34  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa8b39  ldstr    aNotewritepermi// "noteWritePermission"
0xa8b3e  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_WriteNote()
0xa8b43  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa8b48  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa8b4d  brtrue.s loc_A8B56
0xa8b4f  ldstr    aFalse// "false"
0xa8b54  br.s     loc_A8B5B
0xa8b56  ldstr    aTrue// "true"
0xa8b5b  ldarg.0
0xa8b5c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa8b61  ldstr    aOid_1// "oId"
0xa8b66  ldarg.s  6
0xa8b68  ldarg.0
0xa8b69  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa8b6e  ldstr    aParententityty// "parentEntityType"
0xa8b73  ldarga.s 5
0xa8b75  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa8b7a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa8b7f  ldarg.0
0xa8b80  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa8b85  ldarg.s  8
0xa8b87  brfalse.s loc_A8B99
0xa8b89  ldstr    aAscending_0// "ascending"
0xa8b8e  ldstr    aTrue// "true"
0xa8b93  ldarg.0
0xa8b94  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa8b99  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa8b9e  ldstr    aNotesLabelNewn// "Notes_Label_NewNoteTitle"
0xa8ba3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8ba8  stloc.s  0xB
0xa8baa  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xa8baf  ldloc.s  0xB
0xa8bb1  ldc.i4.3
0xa8bb2  newarr   [mscorlib]System.Object
0xa8bb7  dup
0xa8bb8  ldc.i4.0
0xa8bb9  ldstr    a0_1// "{0}"
0xa8bbe  stelem.ref
0xa8bbf  dup
0xa8bc0  ldc.i4.1
0xa8bc1  ldstr    a1_7// "{1}"
0xa8bc6  stelem.ref
0xa8bc7  dup
0xa8bc8  ldc.i4.2
0xa8bc9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xa8bce  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UserName()
0xa8bd3  stelem.ref
0xa8bd4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa8bd9  stloc.s  0xC
0xa8bdb  ldstr    aNewnotetitle// "newNoteTitle"
0xa8be0  ldloc.s  0xC
0xa8be2  ldarg.0
0xa8be3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa8be8  ldstr    aLabeltitleandt// "labelTitleandText"
0xa8bed  ldloc.s  7
0xa8bef  ldarg.0
0xa8bf0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa8bf5  ldstr    aLabeltitle// "labelTitle"
0xa8bfa  ldloc.s  6
0xa8bfc  ldarg.0
0xa8bfd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa8c02  ldstr    aNewnotehinttex// "NewNoteHintText"
0xa8c07  ldloc.2
0xa8c08  ldstr    aNewnotehinttex// "NewNoteHintText"
0xa8c0d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8c12  ldarg.0
0xa8c13  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa8c18  ldstr    aModifytext// "ModifyText"
0xa8c1d  ldloc.2
0xa8c1e  ldstr    aNotesLabelModi// "Notes_Label_Modify"
0xa8c23  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8c28  ldarg.0
0xa8c29  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa8c2e  ldstr    aDeletetext// "DeleteText"
0xa8c33  ldloc.2
0xa8c34  ldstr    aNotesv2Deleten// "NotesV2.DeleteNoteTitle"
0xa8c39  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8c3e  ldarg.0
0xa8c3f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xa8c44  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa8c49  ldstr    aAHrefOnclickOp// "<a href=\"#\" onclick=\"openObj(8, '{0}"...
0xa8c4e  ldc.i4.2
0xa8c4f  newarr   [mscorlib]System.Object
0xa8c54  dup
0xa8c55  ldc.i4.0
0xa8c56  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xa8c5b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0xa8c60  box      [mscorlib]System.Guid
0xa8c65  stelem.ref
0xa8c66  dup
0xa8c67  ldc.i4.1
0xa8c68  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xa8c6d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UserName()
0xa8c72  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xa8c77  stelem.ref
0xa8c78  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa8c7d  stloc.s  0xD
0xa8c7f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa8c84  ldloc.2
0xa8c85  ldstr    aNotesLabelEdit// "Notes_Label_Edited_Refresh"
0xa8c8a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa8c8f  ldc.i4.3
0xa8c90  newarr   [mscorlib]System.Object
  ... truncated ...
```
