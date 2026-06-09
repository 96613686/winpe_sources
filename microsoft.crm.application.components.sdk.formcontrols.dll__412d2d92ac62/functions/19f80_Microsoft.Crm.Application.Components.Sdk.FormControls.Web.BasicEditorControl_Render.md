# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.BasicEditorControl::Render

- ea: `0x19f80`
- end: `0x1a1f3`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.BasicEditorControl::Render`
- size: `627`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x179c0`
- `0x179d0`
- `0x17a10`
- `0x19eb0`
- `0x19f80`

## string_xrefs

- `0x1a05a`: `security`

## pseudocode

```c

```

## disassembly

```asm
0x19f80  ldarg.1
0x19f81  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x19f86  stloc.0
0x19f87  ldloc.0
0x19f88  ldstr    aTableStyleWidt_0// "<table style=\"width:100%;height:100%\""...
0x19f8d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19f92  ldstr    aId// "id"
0x19f97  ldarg.0
0x19f98  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x19f9d  ldarg.1
0x19f9e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x19fa3  ldarg.1
0x19fa4  ldstr    aClass// "class"
0x19fa9  ldstr    aMsCrmEmailBody// "ms-crm-Email-Body"
0x19fae  ldc.i4.0
0x19faf  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x19fb4  ldloc.0
0x19fb5  ldarg.0
0x19fb6  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_Expandos()
0x19fbb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19fc0  ldloc.0
0x19fc1  ldc.i4.s 0x3E
0x19fc3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x19fc8  ldloc.0
0x19fc9  ldstr    aTrStyleHeight2// "<tr style=\"height:26px;vertical-align:"...
0x19fce  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19fd3  ldstr    aId// "id"
0x19fd8  ldarg.0
0x19fd9  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x19fde  ldstr    aHtmlbar// "HtmlBar"
0x19fe3  call     string [mscorlib]System.String::Concat(string, string)
0x19fe8  ldarg.1
0x19fe9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x19fee  ldarg.0
0x19fef  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_ReadOnly()
0x19ff4  brtrue.s loc_19FFE
0x19ff6  ldarg.0
0x19ff7  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x19ffc  brfalse.s loc_1A00F
0x19ffe  ldarg.1
0x19fff  ldstr    aStyle// "style"
0x1a004  ldstr    aDisplayNone// "display:none;"
0x1a009  ldc.i4.0
0x1a00a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1a00f  ldloc.0
0x1a010  ldstr    aTdHeight5// "><td height='5%'>"
0x1a015  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1a01a  ldarg.0
0x1a01b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.BasicEditorControl::_baseHtmlBar
0x1a020  ldarg.0
0x1a021  ldfld    valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.HtmlBarHeaderType Microsoft.Crm.Application.Components.Sdk.FormControls.Web.BasicEditorControl::_htmlBartype
0x1a026  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl::set_HeaderType(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.HtmlBarHeaderType)
0x1a02b  ldarg.0
0x1a02c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.BasicEditorControl::_baseHtmlBar
0x1a031  ldarg.1
0x1a032  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x1a037  ldloc.0
0x1a038  ldstr    aTdTr// "</td></tr>"
0x1a03d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1a042  ldloc.0
0x1a043  ldstr    aTrTdStyleHeigh// "<tr><td style=\"height:90%;vertical-ali"...
0x1a048  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1a04d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x1a052  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsRenderSecureIFrameForEmail()
0x1a057  brfalse.s loc_1A07B
0x1a059  ldarg.1
0x1a05a  ldstr    aSecurity// "security"
0x1a05f  ldstr    aRestricted// "restricted"
0x1a064  ldc.i4.0
0x1a065  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1a06a  ldarg.1
0x1a06b  ldstr    aSandbox// "sandbox"
0x1a070  ldstr    asc_30804// ""
0x1a075  ldc.i4.0
0x1a076  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1a07b  ldstr    aId// "id"
0x1a080  ldarg.0
0x1a081  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1a086  ldstr    aIframe// "IFrame"
0x1a08b  call     string [mscorlib]System.String::Concat(string, string)
0x1a090  ldarg.1
0x1a091  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1a096  ldstr    aControlsEmailb// "/_controls/emailbody/msgBody.aspx"
0x1a09b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a0a0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a0a5  stloc.1
0x1a0a6  ldarg.0
0x1a0a7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.BasicEditorControl::_baseHtmlBar
0x1a0ac  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.HtmlBar::get_EntityCode()
0x1a0b1  ldstr    aWebresource_0// "webresource"
0x1a0b6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a0bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a0c0  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x1a0c5  bne.un.s loc_1A136
0x1a0c7  ldloc.1
0x1a0c8  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x1a0cd  ldstr    aId// "id"
0x1a0d2  ldstr    aWebresource_0// "webresource"
0x1a0d7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a0dc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a0e1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x1a0e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x1a0eb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a0f0  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a0f5  brtrue.s loc_1A0FE
0x1a0f7  ldsfld   string [mscorlib]System.String::Empty
0x1a0fc  br.s     loc_1A11C
0x1a0fe  ldstr    aWebresource_0// "webresource"
0x1a103  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a108  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a10d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x1a112  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x1a117  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x1a11c  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1a121  ldloc.1
0x1a122  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x1a127  ldstr    aEntitytype// "entityType"
0x1a12c  ldstr    aWebresource_0// "webresource"
0x1a131  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1a136  ldstr    aUrl// "url"
0x1a13b  ldloc.1
0x1a13c  callvirt instance string [mscorlib]System.Object::ToString()
0x1a141  ldarg.1
0x1a142  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1a147  ldstr    aSrc// "src"
0x1a14c  ldstr    aStaticBlankHtm// "/_static/blank.htm"
0x1a151  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1a156  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1a15b  callvirt instance string [mscorlib]System.Object::ToString()
0x1a160  ldarg.1
0x1a161  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1a166  ldarg.0
0x1a167  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x1a16c  brfalse.s loc_1A192
0x1a16e  ldarg.1
0x1a16f  ldstr    aTabindex_0// "tabIndex"
0x1a174  ldarg.0
0x1a175  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x1a17a  stloc.2
0x1a17b  ldloca.s 2
0x1a17d  ldstr    aD// "D"
0x1a182  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1a187  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1a18c  ldc.i4.0
0x1a18d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1a192  ldarg.0
0x1a193  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.BasicEditorControl::get_OnFrameLoad()
0x1a198  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1a19d  brtrue.s loc_1A1B0
0x1a19f  ldstr    aOnload// "onload"
0x1a1a4  ldarg.0
0x1a1a5  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.BasicEditorControl::get_OnFrameLoad()
0x1a1aa  ldarg.1
0x1a1ab  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1a1b0  ldarg.1
0x1a1b1  ldstr    aClass// "class"
0x1a1b6  ldstr    aMsCrmEmailBody// "ms-crm-Email-Body"
0x1a1bb  ldc.i4.0
0x1a1bc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1a1c1  ldstr    aTitle// "title"
0x1a1c6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1a1cb  ldstr    aGeneralRichtex// "General.RichTextEditor.Body.Title"
0x1a1d0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1a1d5  ldarg.1
0x1a1d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1a1db  ldloc.0
0x1a1dc  ldstr    aIframeTdTrTabl_0// "></iframe></td></tr></table>"
0x1a1e1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1a1e6  leave.s  loc_1A1F2
0x1a1e8  ldloc.0
0x1a1e9  brfalse.s loc_1A1F1
0x1a1eb  ldloc.0
0x1a1ec  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a1f1  endfinally
0x1a1f2  ret
```
