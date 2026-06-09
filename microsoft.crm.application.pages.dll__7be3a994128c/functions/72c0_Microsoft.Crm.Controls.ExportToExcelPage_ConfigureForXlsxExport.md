# Microsoft.Crm.Controls.ExportToExcelPage::ConfigureForXlsxExport

- ea: `0x72c0`
- end: `0x7451`
- name: `Microsoft.Crm.Controls.ExportToExcelPage::ConfigureForXlsxExport`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6ba0`

## callees

- `0x6730`
- `0x69d0`
- `0x6a00`
- `0x6a30`
- `0x6a90`
- `0x6af0`
- `0x6b10`
- `0x6b40`
- `0x7250`
- `0x72c0`
- `0x7530`

## string_xrefs

- `0x73f1`: `WordTemplate`
- `0x7353`: `templateType`
- `0x7379`: `templateId`
- `0x73c4`: `DocumentTemplate`
- `0x731f`: `FillDocumentTemplateXlsx`
- `0x7331`: `FillPersonalDocumentTemplateXlsx`

## pseudocode

```c

```

## disassembly

```asm
0x72c0  ldarg.0
0x72c1  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::ConfigureFetch()
0x72c6  stloc.0
0x72c7  ldarg.0
0x72c8  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Controls.ExportToExcelPage::get_ViewEntityMetadata()
0x72cd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x72d2  ldarg.0
0x72d3  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_ViewId()
0x72d8  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x72dd  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x72e2  stloc.1
0x72e3  ldarg.0
0x72e4  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_GridXml()
0x72e9  call     class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InputArgumentCollection Microsoft.Crm.Controls.ExportToExcelPage::GridParameters(string gridXml)
0x72ee  stloc.2
0x72ef  ldloc.2
0x72f0  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InputArgument [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InputArgumentCollection::get_Arguments()
0x72f5  ldstr    aQueryapi// "queryapi"
0x72fa  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x72ff  brtrue.s loc_7308
0x7301  ldsfld   string [mscorlib]System.String::Empty
0x7306  br.s     loc_7318
0x7308  ldloc.2
0x7309  ldstr    aQueryapi// "queryapi"
0x730e  callvirt instance object [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InputArgumentCollection::get_Item(string)
0x7313  castclass [mscorlib]System.String
0x7318  stloc.3
0x7319  ldarg.0
0x731a  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_ExportType()
0x731f  ldstr    aFilldocumentte// "FillDocumentTemplateXlsx"
0x7324  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7329  brtrue.s loc_733D
0x732b  ldarg.0
0x732c  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_ExportType()
0x7331  ldstr    aFillpersonaldo// "FillPersonalDocumentTemplateXlsx"
0x7336  call     bool [mscorlib]System.String::op_Equality(string, string)
0x733b  brfalse.s loc_73AC
0x733d  ldarg.0
0x733e  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Controls.ExportToExcelPage::get_OrgContext()
0x7343  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7348  ldarg.0
0x7349  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x734e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x7353  ldstr    aTemplatetype// "templateType"
0x7358  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x735d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7362  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x7367  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x736c  ldloca.s 4
0x736e  ldarg.0
0x736f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7374  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x7379  ldstr    aTemplateid// "templateId"
0x737e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7383  call     instance void [mscorlib]System.Guid::.ctor(string)
0x7388  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x738d  ldloc.s  4
0x738f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x7394  stloc.s  5
0x7396  ldarg.0
0x7397  ldloc.s  5
0x7399  ldloc.0
0x739a  ldloc.3
0x739b  ldloc.2
0x739c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x73a1  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.RenderTemplateCommand::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference, string, string, class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InputArgumentCollection, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x73a6  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.RenderTemplateCommand Microsoft.Crm.Controls.ExportToExcelPage::_renderTemplateCommand
0x73ab  ret
0x73ac  ldarg.0
0x73ad  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_ExportType()
0x73b2  ldstr    aXlsx_0// "xlsx"
0x73b7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x73bc  brtrue.s loc_73D0
0x73be  ldarg.0
0x73bf  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_ExportType()
0x73c4  ldstr    aDocumenttempla// "DocumentTemplate"
0x73c9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x73ce  brfalse.s loc_73EB
0x73d0  ldarg.0
0x73d1  ldloc.1
0x73d2  ldloc.0
0x73d3  ldarg.0
0x73d4  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_LayoutXml()
0x73d9  ldloc.3
0x73da  ldloc.2
0x73db  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x73e0  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.ExportToExcelCommand::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference, string, string, string, class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InputArgumentCollection, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x73e5  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.ExportToExcelCommand Microsoft.Crm.Controls.ExportToExcelPage::_exportToExcelCommand
0x73ea  ret
0x73eb  ldarg.0
0x73ec  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_ExportType()
0x73f1  ldstr    aWordtemplate// "WordTemplate"
0x73f6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x73fb  brfalse.s loc_741A
0x73fd  ldarg.0
0x73fe  ldarg.0
0x73ff  call     instance int32 Microsoft.Crm.Controls.ExportToExcelPage::get_AssociatedEntityTypeCode()
0x7404  ldarg.0
0x7405  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_SelectedEntities()
0x740a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x740f  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.ExportTemplateToWordCommand::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7414  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.ExportTemplateToWordCommand Microsoft.Crm.Controls.ExportToExcelPage::_exportTemplateToWordCommand
0x7419  ret
0x741a  ldarg.0
0x741b  ldloc.1
0x741c  ldloc.0
0x741d  ldarg.0
0x741e  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_LayoutXml()
0x7423  ldstr    aNone// "NONE"
0x7428  ldarg.0
0x7429  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_ExportType()
0x742e  ldstr    aDynamicxlsx// "dynamicXlsx"
0x7433  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7438  brtrue.s loc_743D
0x743a  ldc.i4.1
0x743b  br.s     loc_743E
0x743d  ldc.i4.0
0x743e  ldc.i4.1
0x743f  ldloc.3
0x7440  ldloc.2
0x7441  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7446  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.ExportDynamicToExcelCommand::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference, string, string, string, valuetype [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ExportDynamicToExcelType, bool, string, class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.InputArgumentCollection, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x744b  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.ExportDynamicToExcelCommand Microsoft.Crm.Controls.ExportToExcelPage::_exportDynamicToExcelCommand
0x7450  ret
```
