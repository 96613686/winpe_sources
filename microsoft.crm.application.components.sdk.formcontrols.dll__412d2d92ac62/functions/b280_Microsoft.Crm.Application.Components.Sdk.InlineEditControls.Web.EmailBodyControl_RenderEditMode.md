# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.EmailBodyControl::RenderEditMode

- ea: `0xb280`
- end: `0xb70f`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.EmailBodyControl::RenderEditMode`
- size: `1167`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1260`
- `0x1270`
- `0x1450`
- `0x1520`
- `0x1ba0`
- `0xb280`
- `0xb8a0`

## string_xrefs

- `0xb43e`: `<tr><td><span id="WarningWithOpen" `
- `0xb4cd`: `</span><span id="WarningWithoutOpen" `
- `0xb503`: `Email_BadContent_Warning_With_No_Option_To_Open`
- `0xb538`: `ms-crm-Unblock-Content-Link`
- `0xb56f`: `Email_BadContent_Unblock_Command`
- `0xb614`: `security`

## pseudocode

```c

```

## disassembly

```asm
0xb280  ldarg.1
0xb281  ldstr    aDiv// "div"
0xb286  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0xb28b  ldarg.1
0xb28c  ldstr    aClass// "class"
0xb291  ldstr    aMsCrmInlineEdi_2// "ms-crm-Inline-Edit ms-crm-Inline-Edit-e"...
0xb296  ldc.i4.0
0xb297  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xb29c  ldarg.1
0xb29d  ldstr    aStyle// "style"
0xb2a2  ldstr    aDisplayNone_0// "display: none;"
0xb2a7  ldc.i4.0
0xb2a8  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xb2ad  ldarg.1
0xb2ae  ldc.i4.s 0x3E
0xb2b0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xb2b5  ldarg.1
0xb2b6  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb2bb  ldstr    aTableWidth100H// "<table width=\"100%\" height=\"90%\" ce"...
0xb2c0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb2c5  ldstr    aId// "id"
0xb2ca  ldarg.0
0xb2cb  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xb2d0  ldstr    aI// "_i"
0xb2d5  call     string [mscorlib]System.String::Concat(string, string)
0xb2da  ldarg.1
0xb2db  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xb2e0  ldarg.1
0xb2e1  ldstr    aClass// "class"
0xb2e6  ldstr    aMsCrmEmailBody// "ms-crm-Email-Body"
0xb2eb  ldc.i4.0
0xb2ec  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xb2f1  ldarg.1
0xb2f2  ldstr    aAttrformat// "attrformat"
0xb2f7  ldarg.0
0xb2f8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xb2fd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0xb302  ldc.i4.0
0xb303  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xb308  ldarg.1
0xb309  ldstr    aMainelement// "mainElement"
0xb30e  ldstr    aTrue// "true"
0xb313  ldc.i4.0
0xb314  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xb319  ldarg.0
0xb31a  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_IsDefaultDirty()
0xb31f  brfalse.s loc_B332
0xb321  ldarg.1
0xb322  ldstr    aIsdefaultdirty// "IsDefaultDirty"
0xb327  ldstr    aTrue// "true"
0xb32c  ldc.i4.0
0xb32d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xb332  ldarg.1
0xb333  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb338  ldarg.0
0xb339  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_Expandos()
0xb33e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb343  ldarg.1
0xb344  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb349  ldc.i4.s 0x3E
0xb34b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xb350  ldarg.1
0xb351  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb356  ldstr    aTrHeight26// "<tr height=\"26\""
0xb35b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb360  ldstr    aId// "id"
0xb365  ldarg.0
0xb366  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xb36b  ldstr    aHtmlbar// "HtmlBar"
0xb370  call     string [mscorlib]System.String::Concat(string, string)
0xb375  ldarg.1
0xb376  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xb37b  ldarg.1
0xb37c  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb381  ldstr    aTd// "><td>"
0xb386  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb38b  ldarg.0
0xb38c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailBodyControl::_emailHtmlBar
0xb391  ldarg.0
0xb392  ldfld    valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.HtmlBarHeaderType Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailBodyControl::_type
0xb397  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl::set_HeaderType(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.HtmlBarHeaderType)
0xb39c  ldarg.0
0xb39d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailBodyControl::_emailHtmlBar
0xb3a2  ldarg.1
0xb3a3  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0xb3a8  ldarg.1
0xb3a9  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb3ae  ldstr    aTdTr// "</td></tr>"
0xb3b3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb3b8  ldarg.1
0xb3b9  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb3be  ldstr    aTrIdTrblockmsg// "<tr id=\"trBlockMsg\">"
0xb3c3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb3c8  ldarg.1
0xb3c9  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb3ce  ldstr    aTdIdTdeditbloc// "<td id=\"tdEditBlockMsg\""
0xb3d3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb3d8  ldarg.1
0xb3d9  ldstr    aStyle// "style"
0xb3de  ldstr    aDisplayNone// "display:none;"
0xb3e3  ldc.i4.0
0xb3e4  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xb3e9  ldarg.1
0xb3ea  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb3ef  ldstr    asc_3033C// ">"
0xb3f4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb3f9  ldarg.1
0xb3fa  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb3ff  ldstr    aTableIdWarning// "<table id=\"warningTbl\" cellpadding=\""...
0xb404  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb409  ldarg.1
0xb40a  ldstr    aClass// "class"
0xb40f  ldstr    aMsCrmEmailBody_0// "ms-crm-Email-Body-Error ms-crm-Inline-E"...
0xb414  ldc.i4.0
0xb415  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xb41a  ldarg.1
0xb41b  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb420  ldarg.0
0xb421  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_Expandos()
0xb426  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb42b  ldarg.1
0xb42c  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb431  ldc.i4.s 0x3E
0xb433  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0xb438  ldarg.1
0xb439  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb43e  ldstr    aTrTdSpanIdWarn// "<tr><td><span id=\"WarningWithOpen\" "
0xb443  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb448  ldarg.1
0xb449  ldstr    aStyle// "style"
0xb44e  ldstr    aDisplayNone// "display:none;"
0xb453  ldc.i4.0
0xb454  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xb459  ldarg.1
0xb45a  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb45f  ldstr    asc_3033C// ">"
0xb464  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb469  ldarg.0
0xb46a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xb46f  brfalse.s loc_B4AD
0xb471  ldarg.0
0xb472  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xb477  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_EntityId()
0xb47c  ldarg.0
0xb47d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.EmailBodyControl::_appointmentEntityId
0xb482  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xb487  brfalse.s loc_B4AD
0xb489  ldarg.0
0xb48a  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.EmailBodyControl::IsRteAppointmentExperienceEnabled()
0xb48f  brfalse.s loc_B4AD
0xb491  ldarg.1
0xb492  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb497  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb49c  ldstr    aAppointmentBad// "Appointment_BadContent_Warning"
0xb4a1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb4a6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb4ab  br.s     loc_B4C7
0xb4ad  ldarg.1
0xb4ae  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb4b3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb4b8  ldstr    aEmailBadconten_0// "Email_BadContent_Warning"
0xb4bd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb4c2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb4c7  ldarg.1
0xb4c8  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb4cd  ldstr    aSpanSpanIdWarn// "</span><span id=\"WarningWithoutOpen\" "
0xb4d2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb4d7  ldarg.1
0xb4d8  ldstr    aStyle// "style"
0xb4dd  ldstr    aDisplayNone// "display:none;"
0xb4e2  ldc.i4.0
0xb4e3  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xb4e8  ldarg.1
0xb4e9  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb4ee  ldstr    asc_3033C// ">"
0xb4f3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb4f8  ldarg.1
0xb4f9  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb4fe  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb503  ldstr    aEmailBadconten_1// "Email_BadContent_Warning_With_No_Option"...
0xb508  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb50d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb512  ldarg.1
0xb513  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb518  ldstr    aSpan_0// "</span>"
0xb51d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb522  ldarg.1
0xb523  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb528  ldstr    aSpanIdActualms// "<span id=\"ActualMsg\" "
0xb52d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb532  ldarg.1
0xb533  ldstr    aClass// "class"
0xb538  ldstr    aMsCrmUnblockCo// "ms-crm-Unblock-Content-Link"
0xb53d  ldc.i4.0
0xb53e  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xb543  ldarg.1
0xb544  ldstr    aStyle// "style"
0xb549  ldstr    aDisplayNone// "display:none;"
0xb54e  ldc.i4.0
0xb54f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xb554  ldarg.1
0xb555  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb55a  ldstr    asc_3033C// ">"
0xb55f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb564  ldarg.1
0xb565  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb56a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xb56f  ldstr    aEmailBadconten_2// "Email_BadContent_Unblock_Command"
0xb574  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb579  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb57e  ldarg.1
0xb57f  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb584  ldstr    aSpanTdTr// "</span></td></tr>"
0xb589  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb58e  ldarg.1
0xb58f  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb594  ldstr    aTableTdTr// "</table></td></tr>"
0xb599  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb59e  ldarg.1
0xb59f  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb5a4  ldstr    aTrTdClassMsCrm// "<tr><td class=\"ms-crm-Email-Body\" sty"...
0xb5a9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb5ae  ldarg.1
0xb5af  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb5b4  ldstr    aDivStyleWebkit// "<div style=\"-webkit-overflow-scrolling"...
0xb5b9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0xb5be  ldarg.1
0xb5bf  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0xb5c4  ldstr    aIframeFramebor// "<iframe frameborder=0"
0xb5c9  ldarg.0
0xb5ca  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_ReadOnly()
0xb5cf  brtrue.s loc_B5E0
0xb5d1  ldarg.0
0xb5d2  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0xb5d7  brtrue.s loc_B5E0
0xb5d9  ldsfld   string [mscorlib]System.String::Empty
0xb5de  br.s     loc_B5E5
0xb5e0  ldstr    aDisabledTrue// "disabled = \"true\""
0xb5e5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0xb5ea  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb5ef  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::UseTabletExperience(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb5f4  brfalse.s loc_B607
0xb5f6  ldarg.1
0xb5f7  ldstr    aScrolling// "scrolling"
0xb5fc  ldstr    aAuto// "auto"
0xb601  ldc.i4.0
0xb602  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xb607  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0xb60c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsRenderSecureIFrameForEmail()
0xb611  brfalse.s loc_B635
0xb613  ldarg.1
0xb614  ldstr    aSecurity// "security"
0xb619  ldstr    aRestricted// "restricted"
0xb61e  ldc.i4.0
0xb61f  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xb624  ldarg.1
0xb625  ldstr    aSandbox// "sandbox"
0xb62a  ldstr    asc_30804// ""
0xb62f  ldc.i4.0
0xb630  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0xb635  ldstr    aId// "id"
0xb63a  ldarg.0
0xb63b  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xb640  ldstr    aEditiframe// "EditIFrame"
0xb645  call     string [mscorlib]System.String::Concat(string, string)
0xb64a  ldarg.1
0xb64b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xb650  ldstr    aName// "name"
0xb655  ldarg.0
0xb656  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xb65b  ldstr    aIframe// "IFrame"
0xb660  call     string [mscorlib]System.String::Concat(string, string)
0xb665  ldarg.1
0xb666  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xb66b  ldstr    aControlsEmailb// "/_controls/emailbody/msgBody.aspx"
0xb670  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb675  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb67a  stloc.0
0xb67b  ldarg.0
0xb67c  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailBodyControl::get_IsFollowUp()
0xb681  brfalse.s loc_B698
0xb683  ldloc.0
0xb684  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0xb689  ldstr    aFollowup// "followup"
0xb68e  ldstr    a1_0// "1"
0xb693  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0xb698  ldstr    aUrl// "url"
0xb69d  ldloc.0
0xb69e  callvirt instance string [mscorlib]System.Object::ToString()
0xb6a3  ldarg.1
0xb6a4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xb6a9  ldstr    aSrc// "src"
0xb6ae  ldstr    aStaticBlankHtm// "/_static/blank.htm"
0xb6b3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb6b8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb6bd  callvirt instance string [mscorlib]System.Object::ToString()
0xb6c2  ldarg.1
0xb6c3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0xb6c8  ldarg.1
0xb6c9  ldstr    aClass// "class"
  ... truncated ...
```
