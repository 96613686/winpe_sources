# Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::Render

- ea: `0xf7c0`
- end: `0xf96a`
- name: `Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::Render`
- size: `426`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0xf7a0`
- `0xf7c0`
- `0xf970`
- `0xf9a0`
- `0xf9b0`
- `0xfba0`
- `0xfc00`

## pseudocode

```c

```

## disassembly

```asm
0xf7c0  ldarg.0
0xf7c1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::_entityId
0xf7c6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf7cb  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf7d0  brfalse.s loc_F7EA
0xf7d2  ldarg.0
0xf7d3  ldarg.1
0xf7d4  ldarg.0
0xf7d5  ldfld    string Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::_entityType
0xf7da  ldstr    aWebresource// "webresource"
0xf7df  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xf7e4  call     instance void Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::RenderForNew(class [System.Web]System.Web.UI.HtmlTextWriter writer, bool addStyle)
0xf7e9  ret
0xf7ea  ldarg.0
0xf7eb  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xf7f0  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0xf7f5  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentEncoding(class [mscorlib]System.Text.Encoding)
0xf7fa  ldarg.0
0xf7fb  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0xf800  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0xf805  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetPreamble()
0xf80a  callvirt instance void [System.Web]System.Web.HttpResponse::BinaryWrite(unsigned int8[])
0xf80f  ldarg.0
0xf810  ldfld    string Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::_entityType
0xf815  stloc.0
0xf816  ldloc.0
0xf817  ldstr    aAppointment// "appointment"
0xf81c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf821  brtrue.s loc_F868
0xf823  ldloc.0
0xf824  ldstr    aEmail// "email"
0xf829  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf82e  brtrue   loc_F926
0xf833  ldloc.0
0xf834  ldstr    aCampaign_0// "campaign"
0xf839  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf83e  brtrue   loc_F92E
0xf843  ldloc.0
0xf844  ldstr    aKbarticle// "kbarticle"
0xf849  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf84e  brtrue   loc_F936
0xf853  ldloc.0
0xf854  ldstr    aWebresource// "webresource"
0xf859  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf85e  brtrue   loc_F93E
0xf863  br       loc_F946
0xf868  ldarg.0
0xf869  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::get_OrganizationContext()
0xf86e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf873  ldstr    aOrganization// "organization"
0xf878  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0xf87d  ldstr    aAppointmentric// "appointmentricheditorexperience"
0xf882  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0xf887  brtrue.s loc_F8AD
0xf889  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf88e  ldstr    aUnsupportedEnt// "Unsupported entity type rendering html "...
0xf893  ldc.i4.1
0xf894  newarr   [mscorlib]System.Object
0xf899  dup
0xf89a  ldc.i4.0
0xf89b  ldarg.0
0xf89c  ldfld    string Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::_entityType
0xf8a1  stelem.ref
0xf8a2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf8a7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xf8ac  throw
0xf8ad  ldstr    aOrganization// "organization"
0xf8b2  ldarg.0
0xf8b3  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::get_OrganizationContext()
0xf8b8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0xf8bd  ldc.i4.1
0xf8be  newarr   [mscorlib]System.String
0xf8c3  dup
0xf8c4  ldc.i4.0
0xf8c5  ldstr    aAppointmentric// "appointmentricheditorexperience"
0xf8ca  stelem.ref
0xf8cb  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0xf8d0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf8d5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf8da  stloc.1
0xf8db  ldloc.1
0xf8dc  ldstr    aAppointmentric// "appointmentricheditorexperience"
0xf8e1  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttributeAndNotNull(string)
0xf8e6  brfalse.s loc_F8FA
0xf8e8  ldloc.1
0xf8e9  ldstr    aAppointmentric// "appointmentricheditorexperience"
0xf8ee  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xf8f3  unbox.any [mscorlib]System.Boolean
0xf8f8  brtrue.s loc_F91E
0xf8fa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf8ff  ldstr    aUnsupportedEnt// "Unsupported entity type rendering html "...
0xf904  ldc.i4.1
0xf905  newarr   [mscorlib]System.Object
0xf90a  dup
0xf90b  ldc.i4.0
0xf90c  ldarg.0
0xf90d  ldfld    string Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::_entityType
0xf912  stelem.ref
0xf913  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf918  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xf91d  throw
0xf91e  ldarg.0
0xf91f  ldarg.1
0xf920  call     instance void Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::RenderEmail(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xf925  ret
0xf926  ldarg.0
0xf927  ldarg.1
0xf928  call     instance void Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::RenderEmail(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xf92d  ret
0xf92e  ldarg.0
0xf92f  ldarg.1
0xf930  call     instance void Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::RenderCampaign(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xf935  ret
0xf936  ldarg.0
0xf937  ldarg.1
0xf938  call     instance void Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::RenderKbArticle(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xf93d  ret
0xf93e  ldarg.0
0xf93f  ldarg.1
0xf940  call     instance void Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::RenderWebResource(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0xf945  ret
0xf946  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf94b  ldstr    aUnsupportedEnt// "Unsupported entity type rendering html "...
0xf950  ldc.i4.1
0xf951  newarr   [mscorlib]System.Object
0xf956  dup
0xf957  ldc.i4.0
0xf958  ldarg.0
0xf959  ldfld    string Microsoft.Crm.Common.Web.Controls.EmailBody.MessageBodyPage::_entityType
0xf95e  stelem.ref
0xf95f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf964  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xf969  throw
```
