# Microsoft.Crm.Controls.ExportToExcelPage::ConfigurePage

- ea: `0x6ba0`
- end: `0x6cae`
- name: `Microsoft.Crm.Controls.ExportToExcelPage::ConfigurePage`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x6760`
- `0x6a30`
- `0x6a70`
- `0x6b40`
- `0x6ba0`
- `0x6cb0`
- `0x72c0`
- `0x7460`

## string_xrefs

- `0x6c88`: `WordTemplate`
- `0x6c76`: `MergeWordTemplate`
- `0x6c39`: `DocumentTemplate`
- `0x6c4b`: `FillDocumentTemplateXlsx`
- `0x6c5d`: `FillPersonalDocumentTemplateXlsx`

## pseudocode

```c

```

## disassembly

```asm
0x6ba0  ldarg.0
0x6ba1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x6ba6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x6bab  ldstr    aTweener// "tweener"
0x6bb0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6bb5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6bba  brtrue.s loc_6BDF
0x6bbc  ldarg.0
0x6bbd  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x6bc2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x6bc7  callvirt instance bool [System]System.Collections.Specialized.NameValueCollection::HasKeys()
0x6bcc  brtrue.s loc_6BDF
0x6bce  ldc.i4   0x800609B8
0x6bd3  ldc.i4.0
0x6bd4  newarr   [mscorlib]System.Object
0x6bd9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x6bde  throw
0x6bdf  ldarg.0
0x6be0  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings Microsoft.Crm.Controls.ExportToExcelPage::get_OrgSettings()
0x6be5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_AllowWebExcelExport()
0x6bea  brtrue.s loc_6BFD
0x6bec  ldc.i4   0x80048405
0x6bf1  ldc.i4.0
0x6bf2  newarr   [mscorlib]System.Object
0x6bf7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x6bfc  throw
0x6bfd  ldarg.0
0x6bfe  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_ExportType()
0x6c03  ldstr    aXlsx_0// "xlsx"
0x6c08  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c0d  brtrue.s loc_6C69
0x6c0f  ldarg.0
0x6c10  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_ExportType()
0x6c15  ldstr    aDynamicxlsx// "dynamicXlsx"
0x6c1a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c1f  brtrue.s loc_6C69
0x6c21  ldarg.0
0x6c22  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_ExportType()
0x6c27  ldstr    aPivotxlsx// "pivotXlsx"
0x6c2c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c31  brtrue.s loc_6C69
0x6c33  ldarg.0
0x6c34  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_ExportType()
0x6c39  ldstr    aDocumenttempla// "DocumentTemplate"
0x6c3e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c43  brtrue.s loc_6C69
0x6c45  ldarg.0
0x6c46  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_ExportType()
0x6c4b  ldstr    aFilldocumentte// "FillDocumentTemplateXlsx"
0x6c50  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c55  brtrue.s loc_6C69
0x6c57  ldarg.0
0x6c58  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_ExportType()
0x6c5d  ldstr    aFillpersonaldo// "FillPersonalDocumentTemplateXlsx"
0x6c62  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c67  brfalse.s loc_6C70
0x6c69  ldarg.0
0x6c6a  call     instance void Microsoft.Crm.Controls.ExportToExcelPage::ConfigureForXlsxExport()
0x6c6f  ret
0x6c70  ldarg.0
0x6c71  ldfld    string Microsoft.Crm.Controls.ExportToExcelPage::exportType
0x6c76  ldstr    aMergewordtempl// "MergeWordTemplate"
0x6c7b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c80  brtrue.s loc_6C94
0x6c82  ldarg.0
0x6c83  ldfld    string Microsoft.Crm.Controls.ExportToExcelPage::exportType
0x6c88  ldstr    aWordtemplate// "WordTemplate"
0x6c8d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c92  brfalse.s loc_6C9B
0x6c94  ldarg.0
0x6c95  call     instance void Microsoft.Crm.Controls.ExportToExcelPage::ConfigureForDocxExport()
0x6c9a  ret
0x6c9b  ldarg.0
0x6c9c  ldarg.0
0x6c9d  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_FetchXml()
0x6ca2  ldarg.0
0x6ca3  call     instance string Microsoft.Crm.Controls.ExportToExcelPage::get_LayoutXml()
0x6ca8  call     instance void Microsoft.Crm.Controls.ExportToExcelPage::ConfigureFormInternal(string fetchXml, string layoutXml)
0x6cad  ret
```
