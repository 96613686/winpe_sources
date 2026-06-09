# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::RenderStandard

- ea: `0x1b4d0`
- end: `0x1b9be`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::RenderStandard`
- size: `1262`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x179c0`
- `0x179d0`
- `0x179f0`
- `0x17a10`
- `0x17a40`
- `0x17b90`
- `0x17e80`
- `0x18070`
- `0x1b170`
- `0x1b1e0`
- `0x1b240`
- `0x1b4d0`
- `0x1b9c0`
- `0x1b9f0`

## string_xrefs

- `0x1b6c5`: `Email_BadContent_Warning_With_No_Option_To_Open`
- `0x1b7ec`: `Email_BadContent_Unblock_Command`
- `0x1b84a`: `security`
- `0x1b66c`: `SecuritySettingForEmail`
- `0x1b7ad`: `<span class="ms-crm-Unblock-Content-Link" onclick="unblock('`

## pseudocode

```c

```

## disassembly

```asm
0x1b4d0  ldarg.0
0x1b4d1  call     instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlRenderMode Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_RenderMode()
0x1b4d6  brtrue.s loc_1B4E0
0x1b4d8  ldarg.0
0x1b4d9  ldarg.1
0x1b4da  callvirt instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::RenderForPrinting(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x1b4df  ret
0x1b4e0  ldarg.1
0x1b4e1  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x1b4e6  stloc.0
0x1b4e7  ldarg.0
0x1b4e8  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1b4ed  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage
0x1b4f2  stloc.1
0x1b4f3  ldloc.1
0x1b4f4  brfalse.s loc_1B568
0x1b4f6  ldloc.1
0x1b4f7  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x1b4fc  stloc.s  5
0x1b4fe  ldloc.s  5
0x1b500  brfalse.s loc_1B51B
0x1b502  ldloc.s  5
0x1b504  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_ErrorDuringSave()
0x1b509  brfalse.s loc_1B51B
0x1b50b  ldarg.0
0x1b50c  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::MessageContainsUnsafeScript()
0x1b511  brtrue.s loc_1B51B
0x1b513  ldarg.0
0x1b514  callvirt instance object Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_Value()
0x1b519  brtrue.s loc_1B523
0x1b51b  ldarg.0
0x1b51c  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_IsDefaultDirty()
0x1b521  brfalse.s loc_1B568
0x1b523  ldloc.0
0x1b524  ldstr    aInputTypeHidde// "<input type=\"hidden\" name=\"savedEmai"...
0x1b529  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b52e  ldstr    aValue// "value"
0x1b533  ldarg.0
0x1b534  callvirt instance object Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_Value()
0x1b539  castclass [mscorlib]System.String
0x1b53e  ldarg.1
0x1b53f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1b544  ldarg.0
0x1b545  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_IsDefaultDirty()
0x1b54a  brfalse.s loc_1B55D
0x1b54c  ldarg.1
0x1b54d  ldstr    aDonotsubmit// "DoNotSubmit"
0x1b552  ldstr    aTrue// "true"
0x1b557  ldc.i4.0
0x1b558  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1b55d  ldloc.0
0x1b55e  ldstr    asc_3033C// ">"
0x1b563  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b568  ldloc.0
0x1b569  ldstr    aTableWidth100H_0// "<table width=\"100%\" height=\"100%\" c"...
0x1b56e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b573  ldstr    aId// "id"
0x1b578  ldarg.0
0x1b579  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1b57e  ldarg.1
0x1b57f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1b584  ldarg.1
0x1b585  ldstr    aClass// "class"
0x1b58a  ldstr    aMsCrmEmailBody// "ms-crm-Email-Body"
0x1b58f  ldc.i4.0
0x1b590  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1b595  ldarg.1
0x1b596  ldstr    aAttrformat// "attrformat"
0x1b59b  ldarg.0
0x1b59c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_Metadata()
0x1b5a1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Format()
0x1b5a6  ldc.i4.0
0x1b5a7  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1b5ac  ldarg.0
0x1b5ad  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_IsDefaultDirty()
0x1b5b2  brfalse.s loc_1B5C5
0x1b5b4  ldarg.1
0x1b5b5  ldstr    aIsdefaultdirty// "IsDefaultDirty"
0x1b5ba  ldstr    aTrue// "true"
0x1b5bf  ldc.i4.0
0x1b5c0  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1b5c5  ldloc.0
0x1b5c6  ldarg.0
0x1b5c7  callvirt instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_Expandos()
0x1b5cc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b5d1  ldloc.0
0x1b5d2  ldc.i4.s 0x3E
0x1b5d4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x1b5d9  ldloc.0
0x1b5da  ldstr    aTrHeight26// "<tr height=\"26\""
0x1b5df  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b5e4  ldstr    aId// "id"
0x1b5e9  ldarg.0
0x1b5ea  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1b5ef  ldstr    aHtmlbar// "HtmlBar"
0x1b5f4  call     string [mscorlib]System.String::Concat(string, string)
0x1b5f9  ldarg.1
0x1b5fa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1b5ff  ldarg.0
0x1b600  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_ReadOnly()
0x1b605  brtrue.s loc_1B60F
0x1b607  ldarg.0
0x1b608  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1b60d  brfalse.s loc_1B620
0x1b60f  ldarg.1
0x1b610  ldstr    aStyle// "style"
0x1b615  ldstr    aDisplayNone// "display:none;"
0x1b61a  ldc.i4.0
0x1b61b  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1b620  ldloc.0
0x1b621  ldstr    aTd// "><td>"
0x1b626  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b62b  ldarg.0
0x1b62c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::_emailHtmlBar
0x1b631  ldarg.0
0x1b632  ldfld    valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.HtmlBarHeaderType Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::_type
0x1b637  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl::set_HeaderType(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.HtmlBarHeaderType)
0x1b63c  ldarg.0
0x1b63d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHtmlBarControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::_emailHtmlBar
0x1b642  ldarg.1
0x1b643  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x1b648  ldloc.0
0x1b649  ldstr    aTdTr// "</td></tr>"
0x1b64e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b653  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x1b658  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1b65d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x1b662  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1b667  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x1b66c  ldstr    aSecuritysettin// "SecuritySettingForEmail"
0x1b671  ldc.i4.1
0x1b672  box      [mscorlib]System.Int32
0x1b677  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::GetOrgDBOrgSetting(string, object)
0x1b67c  unbox.any [mscorlib]System.Int32
0x1b681  stloc.2
0x1b682  ldarg.0
0x1b683  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_Metadata()
0x1b688  brfalse.s loc_1B6BC
0x1b68a  ldarg.0
0x1b68b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_Metadata()
0x1b690  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_EntityId()
0x1b695  ldarg.0
0x1b696  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::_appointmentEntityId
0x1b69b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1b6a0  brfalse.s loc_1B6BC
0x1b6a2  ldarg.0
0x1b6a3  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::IsRteAppointmentExperienceEnabled()
0x1b6a8  brfalse.s loc_1B6BC
0x1b6aa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1b6af  ldstr    aAppointmentBad// "Appointment_BadContent_Warning"
0x1b6b4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b6b9  stloc.3
0x1b6ba  br.s     loc_1B6E1
0x1b6bc  ldc.i4.2
0x1b6bd  ldloc.2
0x1b6be  bne.un.s loc_1B6D1
0x1b6c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1b6c5  ldstr    aEmailBadconten_1// "Email_BadContent_Warning_With_No_Option"...
0x1b6ca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b6cf  br.s     loc_1B6E0
0x1b6d1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1b6d6  ldstr    aEmailBadconten_0// "Email_BadContent_Warning"
0x1b6db  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b6e0  stloc.3
0x1b6e1  ldarg.0
0x1b6e2  callvirt instance object Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControl::get_Value()
0x1b6e7  brtrue.s loc_1B731
0x1b6e9  ldarg.0
0x1b6ea  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_ReadOnly()
0x1b6ef  brtrue.s loc_1B6FC
0x1b6f1  ldarg.0
0x1b6f2  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1b6f7  brfalse  loc_1B816
0x1b6fc  ldloc.0
0x1b6fd  ldstr    aTrHeight20IdTr// "<tr height=20 id=\"trBlockMsg\"><td sty"...
0x1b702  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b707  ldloc.0
0x1b708  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1b70d  ldstr    aEmailBodyIsEmp// "Email_Body_Is_Empty_Warning"
0x1b712  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b717  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1b71c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b721  ldloc.0
0x1b722  ldstr    aTdTrTableTdTr// "</td></tr></table></td></tr>"
0x1b727  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b72c  br       loc_1B816
0x1b731  ldarg.0
0x1b732  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::MessageContainsUnsafeScript()
0x1b737  brfalse  loc_1B816
0x1b73c  ldc.i4.3
0x1b73d  ldloc.2
0x1b73e  beq      loc_1B816
0x1b743  ldloc.0
0x1b744  ldstr    aTrHeight20IdTr// "<tr height=20 id=\"trBlockMsg\"><td sty"...
0x1b749  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b74e  ldloc.0
0x1b74f  ldloc.3
0x1b750  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1b755  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b75a  ldarg.0
0x1b75b  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::get_IsFollowUp()
0x1b760  brtrue   loc_1B80B
0x1b765  ldarg.0
0x1b766  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::get_EntityType()
0x1b76b  ldstr    aEmail// "email"
0x1b770  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b775  brfalse  loc_1B80B
0x1b77a  ldarg.0
0x1b77b  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::get_EntityId()
0x1b780  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b785  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1b78a  brfalse.s loc_1B80B
0x1b78c  ldc.i4.2
0x1b78d  ldloc.2
0x1b78e  beq.s    loc_1B80B
0x1b790  ldarg.0
0x1b791  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppControl::get_CurrentWrpcContext()
0x1b796  ldstr    aControlsEmailb_0// "/_controls/emailbody/msgbody.aspx"
0x1b79b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1b7a0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b7a5  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext::GetWrpcTokenAsQueryString(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x1b7aa  stloc.s  6
0x1b7ac  ldloc.0
0x1b7ad  ldstr    aSpanClassMsCrm_1// "<span class=\"ms-crm-Unblock-Content-Li"...
0x1b7b2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b7b7  ldloc.0
0x1b7b8  ldarg.0
0x1b7b9  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::get_EntityId()
0x1b7be  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x1b7c3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b7c8  ldloc.0
0x1b7c9  ldstr    asc_4A78E// "','"
0x1b7ce  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b7d3  ldloc.0
0x1b7d4  ldloc.s  6
0x1b7d6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b7db  ldloc.0
0x1b7dc  ldstr    asc_4A796// "');\">"
0x1b7e1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b7e6  ldloc.0
0x1b7e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1b7ec  ldstr    aEmailBadconten_2// "Email_BadContent_Unblock_Command"
0x1b7f1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1b7f6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1b7fb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b800  ldloc.0
0x1b801  ldstr    aSpan_0// "</span>"
0x1b806  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b80b  ldloc.0
0x1b80c  ldstr    aTdTrTableTdTr// "</td></tr></table></td></tr>"
0x1b811  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1b816  ldloc.0
0x1b817  ldstr    aTrTdClassMsCrm_0// "<tr><td class=\"ms-crm-Email-Body\" sty"...
0x1b81c  ldarg.0
0x1b81d  callvirt instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_ReadOnly()
0x1b822  brtrue.s loc_1B833
0x1b824  ldarg.0
0x1b825  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1b82a  brtrue.s loc_1B833
0x1b82c  ldsfld   string [mscorlib]System.String::Empty
0x1b831  br.s     loc_1B838
0x1b833  ldstr    aDisabledTrue// "disabled = \"true\""
0x1b838  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x1b83d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x1b842  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsRenderSecureIFrameForEmail()
0x1b847  brfalse.s loc_1B86B
0x1b849  ldarg.1
0x1b84a  ldstr    aSecurity// "security"
0x1b84f  ldstr    aRestricted// "restricted"
0x1b854  ldc.i4.0
0x1b855  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1b85a  ldarg.1
0x1b85b  ldstr    aSandbox// "sandbox"
0x1b860  ldstr    asc_30804// ""
0x1b865  ldc.i4.0
0x1b866  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1b86b  ldstr    aId// "id"
0x1b870  ldarg.0
0x1b871  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1b876  ldstr    aIframe// "IFrame"
0x1b87b  call     string [mscorlib]System.String::Concat(string, string)
0x1b880  ldarg.1
0x1b881  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1b886  ldstr    aName// "name"
0x1b88b  ldarg.0
0x1b88c  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1b891  ldstr    aIframe// "IFrame"
0x1b896  call     string [mscorlib]System.String::Concat(string, string)
0x1b89b  ldarg.1
0x1b89c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x1b8a1  ldstr    aControlsEmailb// "/_controls/emailbody/msgBody.aspx"
0x1b8a6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1b8ab  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1b8b0  stloc.s  4
0x1b8b2  ldloc.s  4
0x1b8b4  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x1b8b9  ldstr    aId// "id"
0x1b8be  ldarg.0
0x1b8bf  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::get_EntityId()
0x1b8c4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
  ... truncated ...
```
