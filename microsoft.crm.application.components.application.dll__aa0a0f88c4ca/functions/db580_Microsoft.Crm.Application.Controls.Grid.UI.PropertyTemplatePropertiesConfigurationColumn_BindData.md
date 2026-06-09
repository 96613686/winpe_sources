# Microsoft.Crm.Application.Controls.Grid.UI.PropertyTemplatePropertiesConfigurationColumn::BindData

- ea: `0xdb580`
- end: `0xdb74c`
- name: `Microsoft.Crm.Application.Controls.Grid.UI.PropertyTemplatePropertiesConfigurationColumn::BindData`
- size: `460`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0xd97a0`
- `0xd97e0`
- `0xda0a0`
- `0xdb580`
- `0xdfc30`
- `0xdfc40`

## string_xrefs

- `0xdb70a`: `ms-crm-qoi-productgrid-anchor-link-text`
- `0xdb5a6`: `propertyconfigurationstatus`
- `0xdb6af`: `configuration_gridurl_{0}`

## pseudocode

```c

```

## disassembly

```asm
0xdb580  ldarg.2
0xdb581  ldstr    aProductid// "productid"
0xdb586  callvirt instance string Microsoft.Crm.Application.Controls.Grid.UI.IRowDataSource::GetFormattedValue(string columnName)
0xdb58b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xdb590  brfalse.s loc_DB593
0xdb592  ret
0xdb593  ldsfld   string [mscorlib]System.String::Empty
0xdb598  stloc.0
0xdb599  ldsfld   string [mscorlib]System.String::Empty
0xdb59e  stloc.1
0xdb59f  ldsfld   string [mscorlib]System.String::Empty
0xdb5a4  stloc.2
0xdb5a5  ldarg.2
0xdb5a6  ldstr    aPropertyconfig// "propertyconfigurationstatus"
0xdb5ab  callvirt instance object Microsoft.Crm.Application.Controls.Grid.UI.IRowDataSource::GetRawValue(string columnName)
0xdb5b0  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0xdb5b5  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0xdb5ba  stloc.3
0xdb5bb  ldloc.3
0xdb5bc  switch   loc_DB5CF, loc_DB5E3, loc_DB5F7
0xdb5cd  br.s     loc_DB5FF
0xdb5cf  ldstr    aQueryProductCe_0// "query.product.cell.productname.edit"
0xdb5d4  stloc.0
0xdb5d5  ldstr    aQueryProductCe_1// "query.product.cell.productname.edittitl"...
0xdb5da  stloc.1
0xdb5db  ldstr    aImgSrcImgsProc_0// "<img src='/_imgs/processcontrol/edit_pr"...
0xdb5e0  stloc.2
0xdb5e1  br.s     loc_DB605
0xdb5e3  ldstr    aQueryProductCe_0// "query.product.cell.productname.edit"
0xdb5e8  stloc.0
0xdb5e9  ldstr    aQueryProductCe_2// "query.product.cell.productname.rectifyt"...
0xdb5ee  stloc.1
0xdb5ef  ldstr    aImgSrcImgsProc_1// "<img src='/_imgs/processcontrol/rectify"...
0xdb5f4  stloc.2
0xdb5f5  br.s     loc_DB605
0xdb5f7  ldsfld   string [mscorlib]System.String::Empty
0xdb5fc  stloc.0
0xdb5fd  br.s     loc_DB605
0xdb5ff  ldsfld   string [mscorlib]System.String::Empty
0xdb604  stloc.0
0xdb605  ldarg.0
0xdb606  call     instance bool Microsoft.Crm.Application.Controls.Grid.UI.PropertyTemplate::get_IsImageContainingColumn()
0xdb60b  brfalse.s loc_DB615
0xdb60d  ldarg.0
0xdb60e  ldarg.1
0xdb60f  ldarg.2
0xdb610  callvirt instance void Microsoft.Crm.Application.Controls.Grid.UI.PropertyTemplate::AddImageToParentControl(class [System.Web]System.Web.UI.WebControls.WebControl parentControl, class Microsoft.Crm.Application.Controls.Grid.UI.IRowDataSource rowData)
0xdb615  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::.ctor()
0xdb61a  stloc.s  4
0xdb61c  ldloc.0
0xdb61d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xdb622  brtrue.s loc_DB686
0xdb624  ldloc.2
0xdb625  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xdb62a  brtrue.s loc_DB686
0xdb62c  ldloc.s  4
0xdb62e  ldloc.2
0xdb62f  ldstr    aLabelStyleText// "<label style= \"text-decoration: underl"...
0xdb634  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xdb639  ldloc.0
0xdb63a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdb63f  ldstr    aLabel_0// "</label>"
0xdb644  call     string [mscorlib]System.String::Concat(string, string, string, string)
0xdb649  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0xdb64e  ldloc.s  4
0xdb650  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xdb655  ldloc.1
0xdb656  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xdb65b  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_Title(string)
0xdb660  ldloc.s  4
0xdb662  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdb667  ldstr    aTabindex// "tabindex"
0xdb66c  ldarg.0
0xdb66d  call     instance int32 Microsoft.Crm.Application.Controls.Grid.UI.PropertyTemplate::get_TabIndex()
0xdb672  stloc.3
0xdb673  ldloca.s 3
0xdb675  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdb67a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xdb67f  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdb684  br.s     loc_DB69C
0xdb686  ldloc.s  4
0xdb688  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdb68d  ldstr    aTabindex// "tabindex"
0xdb692  ldstr    a1// "-1"
0xdb697  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdb69c  ldloc.s  4
0xdb69e  ldstr    aSelf// "_self"
0xdb6a3  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_Target(string)
0xdb6a8  ldloc.s  4
0xdb6aa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdb6af  ldstr    aConfigurationG// "configuration_gridurl_{0}"
0xdb6b4  ldc.i4.1
0xdb6b5  newarr   [mscorlib]System.Object
0xdb6ba  dup
0xdb6bb  ldc.i4.0
0xdb6bc  ldarg.2
0xdb6bd  ldstr    aRowid// "RowId"
0xdb6c2  callvirt instance string Microsoft.Crm.Application.Controls.Grid.UI.IRowDataSource::GetFormattedValue(string columnName)
0xdb6c7  stelem.ref
0xdb6c8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdb6cd  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xdb6d2  ldloc.s  4
0xdb6d4  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0xdb6d9  ldstr    aCursor// "cursor"
0xdb6de  ldstr    aPointer// "pointer"
0xdb6e3  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::set_Item(string, string)
0xdb6e8  ldloc.s  4
0xdb6ea  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdb6ef  ldstr    aStyle_0// "style"
0xdb6f4  ldstr    aColor0072c6Tex// "color: #0072C6; text-decoration: none;"
0xdb6f9  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdb6fe  ldloc.s  4
0xdb700  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdb705  ldstr    aClass_0// "class"
0xdb70a  ldstr    aMsCrmQoiProduc// "ms-crm-qoi-productgrid-anchor-link-text"
0xdb70f  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdb714  ldloc.s  4
0xdb716  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdb71b  ldstr    aProductname_1// "Productname"
0xdb720  ldarg.2
0xdb721  ldstr    aProductid// "productid"
0xdb726  callvirt instance string Microsoft.Crm.Application.Controls.Grid.UI.IRowDataSource::GetFormattedValue(string columnName)
0xdb72b  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdb730  ldarg.1
0xdb731  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xdb736  ldloc.s  4
0xdb738  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xdb73d  leave.s  loc_DB74B
0xdb73f  ldloc.s  4
0xdb741  brfalse.s loc_DB74A
0xdb743  ldloc.s  4
0xdb745  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdb74a  endfinally
0xdb74b  ret
```
