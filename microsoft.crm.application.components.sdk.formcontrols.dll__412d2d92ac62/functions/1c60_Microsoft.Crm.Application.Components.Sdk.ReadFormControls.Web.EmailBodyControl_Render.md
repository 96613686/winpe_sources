# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailBodyControl::Render

- ea: `0x1c60`
- end: `0x21a0`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailBodyControl::Render`
- size: `1344`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0xb1d0`

## callees

- `0x1260`
- `0x1270`
- `0x1290`
- `0x1330`
- `0x1450`
- `0x1520`
- `0x1b80`
- `0x1ba0`
- `0x1c60`
- `0x21a0`

## string_xrefs

- `0x1e28`: `<tr><td><span id="WarningWithOpen" `
- `0x1eb7`: `</span><span id="WarningWithoutOpen" `
- `0x1eed`: `Email_BadContent_Warning_With_No_Option_To_Open`
- `0x1f22`: `ms-crm-Unblock-Content-Link`
- `0x1f59`: `Email_BadContent_Unblock_Command`
- `0x200e`: `security`

## pseudocode

```c

```

## disassembly

```asm
0x1c60  ldarg.0
0x1c61  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailBodyControl::get_EmailHtmlBar()
0x1c66  brfalse  loc_2142
0x1c6b  ldarg.1
0x1c6c  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1c71  ldstr    aTableWidth100H// "<table width=\"100%\" height=\"90%\" ce"...
0x1c76  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1c7b  ldstr    aId// "id"
0x1c80  ldarg.0
0x1c81  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1c86  ldstr    aI// "_i"
0x1c8b  call     string [mscorlib]System.String::Concat(string, string)
0x1c90  ldarg.1
0x1c91  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1c96  ldarg.1
0x1c97  ldstr    aClass// "class"
0x1c9c  ldstr    aMsCrmEmailBody// "ms-crm-Email-Body"
0x1ca1  ldc.i4.0
0x1ca2  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1ca7  ldarg.1
0x1ca8  ldstr    aAttrformat// "attrformat"
0x1cad  ldarg.0
0x1cae  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x1cb3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x1cb8  ldc.i4.0
0x1cb9  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1cbe  ldarg.1
0x1cbf  ldstr    aMainelement// "mainElement"
0x1cc4  ldstr    aTrue// "true"
0x1cc9  ldc.i4.0
0x1cca  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1ccf  ldarg.0
0x1cd0  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_IsDefaultDirty()
0x1cd5  brfalse.s loc_1CE8
0x1cd7  ldarg.1
0x1cd8  ldstr    aIsdefaultdirty// "IsDefaultDirty"
0x1cdd  ldstr    aTrue// "true"
0x1ce2  ldc.i4.0
0x1ce3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1ce8  ldarg.1
0x1ce9  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1cee  ldarg.0
0x1cef  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_Expandos()
0x1cf4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1cf9  ldarg.1
0x1cfa  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1cff  ldc.i4.s 0x3E
0x1d01  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x1d06  ldarg.1
0x1d07  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1d0c  ldstr    aTrHeight26// "<tr height=\"26\""
0x1d11  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1d16  ldstr    aId// "id"
0x1d1b  ldarg.0
0x1d1c  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1d21  ldstr    aHtmlbar// "HtmlBar"
0x1d26  call     string [mscorlib]System.String::Concat(string, string)
0x1d2b  ldarg.1
0x1d2c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1d31  ldarg.0
0x1d32  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1d37  brfalse.s loc_1D4A
0x1d39  ldarg.1
0x1d3a  ldstr    aStyle// "style"
0x1d3f  ldstr    aDisplayNone// "display:none;"
0x1d44  ldc.i4.0
0x1d45  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1d4a  ldarg.1
0x1d4b  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1d50  ldstr    aTd// "><td>"
0x1d55  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1d5a  ldarg.0
0x1d5b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailBodyControl::_emailHtmlBar
0x1d60  ldarg.0
0x1d61  ldfld    valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.HtmlBarHeaderType Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailBodyControl::_type
0x1d66  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl::set_HeaderType(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.HtmlBarHeaderType)
0x1d6b  ldarg.0
0x1d6c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailBodyControl::_emailHtmlBar
0x1d71  ldarg.1
0x1d72  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x1d77  ldarg.1
0x1d78  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1d7d  ldstr    aTdTr// "</td></tr>"
0x1d82  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1d87  ldarg.1
0x1d88  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1d8d  ldstr    aTrIdTrblockmsg// "<tr id=\"trBlockMsg\">"
0x1d92  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1d97  ldarg.0
0x1d98  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x1d9d  brfalse  loc_1F88
0x1da2  ldarg.0
0x1da3  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x1da8  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x1dad  brfalse  loc_1F88
0x1db2  ldarg.1
0x1db3  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1db8  ldstr    aTdIdTdblockmsg// "<td id=\"tdBlockMsg\""
0x1dbd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1dc2  ldarg.1
0x1dc3  ldstr    aStyle// "style"
0x1dc8  ldstr    aDisplayNone// "display:none;"
0x1dcd  ldc.i4.0
0x1dce  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1dd3  ldarg.1
0x1dd4  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1dd9  ldstr    asc_3033C// ">"
0x1dde  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1de3  ldarg.1
0x1de4  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1de9  ldstr    aTableIdWarning// "<table id=\"warningTbl\" cellpadding=\""...
0x1dee  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1df3  ldarg.1
0x1df4  ldstr    aClass// "class"
0x1df9  ldstr    aMsCrmEmailBody_0// "ms-crm-Email-Body-Error ms-crm-Inline-E"...
0x1dfe  ldc.i4.0
0x1dff  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1e04  ldarg.1
0x1e05  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1e0a  ldarg.0
0x1e0b  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_Expandos()
0x1e10  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e15  ldarg.1
0x1e16  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1e1b  ldc.i4.s 0x3E
0x1e1d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x1e22  ldarg.1
0x1e23  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1e28  ldstr    aTrTdSpanIdWarn// "<tr><td><span id=\"WarningWithOpen\" "
0x1e2d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e32  ldarg.1
0x1e33  ldstr    aStyle// "style"
0x1e38  ldstr    aDisplayNone// "display:none;"
0x1e3d  ldc.i4.0
0x1e3e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1e43  ldarg.1
0x1e44  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1e49  ldstr    asc_3033C// ">"
0x1e4e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e53  ldarg.0
0x1e54  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x1e59  brfalse.s loc_1E97
0x1e5b  ldarg.0
0x1e5c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x1e61  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_EntityId()
0x1e66  ldarg.0
0x1e67  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailBodyControl::_appointmentEntityId
0x1e6c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1e71  brfalse.s loc_1E97
0x1e73  ldarg.0
0x1e74  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailBodyControl::IsRteAppointmentExperienceEnabled()
0x1e79  brfalse.s loc_1E97
0x1e7b  ldarg.1
0x1e7c  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1e81  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1e86  ldstr    aAppointmentBad// "Appointment_BadContent_Warning"
0x1e8b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e90  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1e95  br.s     loc_1EB1
0x1e97  ldarg.1
0x1e98  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1e9d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1ea2  ldstr    aEmailBadconten_0// "Email_BadContent_Warning"
0x1ea7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1eac  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1eb1  ldarg.1
0x1eb2  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1eb7  ldstr    aSpanSpanIdWarn// "</span><span id=\"WarningWithoutOpen\" "
0x1ebc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ec1  ldarg.1
0x1ec2  ldstr    aStyle// "style"
0x1ec7  ldstr    aDisplayNone// "display:none;"
0x1ecc  ldc.i4.0
0x1ecd  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1ed2  ldarg.1
0x1ed3  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1ed8  ldstr    asc_3033C// ">"
0x1edd  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ee2  ldarg.1
0x1ee3  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1ee8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1eed  ldstr    aEmailBadconten_1// "Email_BadContent_Warning_With_No_Option"...
0x1ef2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1ef7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1efc  ldarg.1
0x1efd  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1f02  ldstr    aSpan_0// "</span>"
0x1f07  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f0c  ldarg.1
0x1f0d  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1f12  ldstr    aSpanIdActualms// "<span id=\"ActualMsg\" "
0x1f17  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f1c  ldarg.1
0x1f1d  ldstr    aClass// "class"
0x1f22  ldstr    aMsCrmUnblockCo// "ms-crm-Unblock-Content-Link"
0x1f27  ldc.i4.0
0x1f28  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1f2d  ldarg.1
0x1f2e  ldstr    aStyle// "style"
0x1f33  ldstr    aDisplayNone// "display:none;"
0x1f38  ldc.i4.0
0x1f39  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1f3e  ldarg.1
0x1f3f  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1f44  ldstr    asc_3033C// ">"
0x1f49  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f4e  ldarg.1
0x1f4f  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1f54  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1f59  ldstr    aEmailBadconten_2// "Email_BadContent_Unblock_Command"
0x1f5e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1f63  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f68  ldarg.1
0x1f69  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1f6e  ldstr    aSpanTdTr// "</span></td></tr>"
0x1f73  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f78  ldarg.1
0x1f79  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1f7e  ldstr    aTableTd// "</table></td>"
0x1f83  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f88  ldarg.1
0x1f89  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1f8e  ldstr    aTr// "</tr>"
0x1f93  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1f98  ldarg.1
0x1f99  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1f9e  ldstr    aTrTdClassMsCrm// "<tr><td class=\"ms-crm-Email-Body\" sty"...
0x1fa3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1fa8  ldarg.1
0x1fa9  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1fae  ldstr    aDivStyleWebkit// "<div style=\"-webkit-overflow-scrolling"...
0x1fb3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1fb8  ldarg.1
0x1fb9  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1fbe  ldstr    aIframeFramebor// "<iframe frameborder=0"
0x1fc3  ldarg.0
0x1fc4  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_ReadOnly()
0x1fc9  brtrue.s loc_1FDA
0x1fcb  ldarg.0
0x1fcc  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1fd1  brtrue.s loc_1FDA
0x1fd3  ldsfld   string [mscorlib]System.String::Empty
0x1fd8  br.s     loc_1FDF
0x1fda  ldstr    aDisabledTrue// "disabled = \"true\""
0x1fdf  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x1fe4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1fe9  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1fee  brfalse.s loc_2001
0x1ff0  ldarg.1
0x1ff1  ldstr    aScrolling// "scrolling"
0x1ff6  ldstr    aAuto// "auto"
0x1ffb  ldc.i4.0
0x1ffc  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2001  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x2006  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsRenderSecureIFrameForEmail()
0x200b  brfalse.s loc_202F
0x200d  ldarg.1
0x200e  ldstr    aSecurity// "security"
0x2013  ldstr    aRestricted// "restricted"
0x2018  ldc.i4.0
0x2019  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x201e  ldarg.1
0x201f  ldstr    aSandbox// "sandbox"
0x2024  ldstr    asc_30804// ""
0x2029  ldc.i4.0
0x202a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x202f  ldstr    aId// "id"
0x2034  ldarg.0
0x2035  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x203a  ldstr    aIframe// "IFrame"
0x203f  call     string [mscorlib]System.String::Concat(string, string)
0x2044  ldarg.1
0x2045  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x204a  ldstr    aName// "name"
0x204f  ldarg.0
0x2050  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2055  ldstr    aIframe// "IFrame"
0x205a  call     string [mscorlib]System.String::Concat(string, string)
0x205f  ldarg.1
0x2060  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2065  ldstr    aControlsEmailb// "/_controls/emailbody/msgBody.aspx"
0x206a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x206f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2074  stloc.0
0x2075  ldarg.0
0x2076  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailBodyControl::get_IsFollowUp()
0x207b  brfalse.s loc_2092
0x207d  ldloc.0
0x207e  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x2083  ldstr    aFollowup// "followup"
0x2088  ldstr    a1_0// "1"
0x208d  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x2092  ldstr    aUrl// "url"
0x2097  ldloc.0
0x2098  callvirt instance string [mscorlib]System.Object::ToString()
0x209d  ldarg.1
0x209e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x20a3  ldstr    aSrc// "src"
0x20a8  ldstr    aStaticBlankHtm// "/_static/blank.htm"
0x20ad  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
  ... truncated ...
```
