# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.EmailBodyControl::Render

- ea: `0xb1d0`
- end: `0xb27f`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.EmailBodyControl::Render`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1450`
- `0x1c00`
- `0x1c60`
- `0x8e10`
- `0x8e30`
- `0x8e50`
- `0x8e60`
- `0x91b0`
- `0xb1d0`
- `0xb8a0`

## string_xrefs

- `0xb216`: `wrpcToken`
- `0xb23b`: `wrpcTokenForAttachment`

## pseudocode

```c

```

## disassembly

```asm
0xb1d0  ldarg.0
0xb1d1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xb1d6  brfalse.s loc_B1FF
0xb1d8  ldarg.0
0xb1d9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0xb1de  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_EntityId()
0xb1e3  ldarg.0
0xb1e4  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.EmailBodyControl::_appointmentEntityId
0xb1e9  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xb1ee  brfalse.s loc_B1FF
0xb1f0  ldarg.0
0xb1f1  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.EmailBodyControl::IsRteAppointmentExperienceEnabled()
0xb1f6  brfalse.s loc_B1FF
0xb1f8  ldarg.0
0xb1f9  ldc.i4.0
0xb1fa  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailBodyControl::set_Type(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.HtmlBarHeaderType value)
0xb1ff  ldarg.0
0xb200  newobj   instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::.ctor(class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormDataControlUIWrapper readFormControl)
0xb205  dup
0xb206  ldstr    aStyle// "style"
0xb20b  ldstr    aHeight100// "height:100%"
0xb210  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xb215  dup
0xb216  ldstr    aWrpctoken// "wrpcToken"
0xb21b  ldarg.0
0xb21c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppControl::get_CurrentWrpcContext()
0xb221  ldstr    aControlsEmailb_0// "/_controls/emailbody/msgbody.aspx"
0xb226  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb22b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb230  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext::GetWrpcTokenAsQueryString(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xb235  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xb23a  dup
0xb23b  ldstr    aWrpctokenforat// "wrpcTokenForAttachment"
0xb240  ldarg.0
0xb241  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppControl::get_CurrentWrpcContext()
0xb246  ldstr    aActivitiesAtta// "/Activities/Attachment/download.aspx"
0xb24b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb250  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb255  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Security.WrpcContext::GetWrpcTokenAsQueryString(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xb25a  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::SetCustomHtmlAttributes(string name, string value)
0xb25f  dup
0xb260  ldstr    aMsCrmEmailBody_1// "ms-crm-Email-Body-Value"
0xb265  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::set_ValueElementAdditionalCssClass(string value)
0xb26a  dup
0xb26b  ldarg.1
0xb26c  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::BeginRender(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xb271  ldarg.0
0xb272  ldarg.1
0xb273  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.EmailBodyControl::Render(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xb278  ldarg.1
0xb279  callvirt instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.ChromeRenderer::EndRender(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xb27e  ret
```
