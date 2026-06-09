# Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderProductSuggestionsGrid::AddFloatingFillerCell

- ea: `0xd2ec0`
- end: `0xd300d`
- name: `Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderProductSuggestionsGrid::AddFloatingFillerCell`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xd2ea0`

## callees

- `0xcd240`
- `0xcd7f0`
- `0xd2ec0`

## string_xrefs

- `0xd2ed6`: `ms-crm-List-DataCell inner-grid-cellPadding floatingCell-suggestions-removeBorder`
- `0xd2fe9`: `ms-crm-List-DataCell inner-grid-cellPadding floatingCell-suggestions-removeBorder`
- `0xd2f10`: `ms-crm-subgrid-add-link`

## pseudocode

```c

```

## disassembly

```asm
0xd2ec0  newobj   instance void [System.Web]System.Web.UI.WebControls.TableCell::.ctor()
0xd2ec5  stloc.0
0xd2ec6  ldnull
0xd2ec7  stloc.1
0xd2ec8  ldstr    aGridaddproduct// "gridAddProductBtn"
0xd2ecd  stloc.1
0xd2ece  ldloc.0
0xd2ecf  ldloc.1
0xd2ed0  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xd2ed5  ldloc.0
0xd2ed6  ldstr    aMsCrmListDatac_1// "ms-crm-List-DataCell inner-grid-cellPad"...
0xd2edb  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0xd2ee0  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::.ctor()
0xd2ee5  stloc.2
0xd2ee6  ldloc.2
0xd2ee7  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd2eec  ldstr    aTitle// "title"
0xd2ef1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd2ef6  ldstr    aTooltipGridadd// "ToolTip_GridAddProductAction"
0xd2efb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd2f00  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0xd2f05  ldloc.2
0xd2f06  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd2f0b  ldstr    aClass_3// "CLASS"
0xd2f10  ldstr    aMsCrmSubgridAd// "ms-crm-subgrid-add-link"
0xd2f15  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xd2f1a  ldloc.2
0xd2f1b  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd2f20  ldstr    aTabindex// "tabindex"
0xd2f25  ldarg.0
0xd2f26  call     instance class Microsoft.Crm.Application.Controls.Grid.UI.LayoutDescriptor Microsoft.Crm.Application.Controls.Grid.UI.LayoutProvider::get_LayoutDescriptor()
0xd2f2b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Controls.Grid.UI.LayoutDescriptor::get_Parameters()
0xd2f30  ldstr    aTabindex// "tabindex"
0xd2f35  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xd2f3a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd2f3f  brfalse.s loc_D2F48
0xd2f41  ldstr    a0// "0"
0xd2f46  br.s     loc_D2F5D
0xd2f48  ldarg.0
0xd2f49  call     instance class Microsoft.Crm.Application.Controls.Grid.UI.LayoutDescriptor Microsoft.Crm.Application.Controls.Grid.UI.LayoutProvider::get_LayoutDescriptor()
0xd2f4e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Controls.Grid.UI.LayoutDescriptor::get_Parameters()
0xd2f53  ldstr    aTabindex// "tabindex"
0xd2f58  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xd2f5d  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0xd2f62  ldloc.2
0xd2f63  ldstr    aAddproduct// "addproduct_"
0xd2f68  ldarg.2
0xd2f69  ldstr    aRowid// "RowId"
0xd2f6e  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0xd2f73  callvirt instance string [mscorlib]System.Object::ToString()
0xd2f78  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xd2f7d  call     string [mscorlib]System.String::Concat(string, string)
0xd2f82  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xd2f87  ldloc.2
0xd2f88  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd2f8d  ldstr    aHref// "href"
0xd2f92  ldstr    aJavascriptVoid_1// "javascript:void(0);"
0xd2f97  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0xd2f9c  ldloc.2
0xd2f9d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd2fa2  ldstr    aGridAddproduct// "Grid_AddProductAction"
0xd2fa7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd2fac  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0xd2fb1  ldloc.0
0xd2fb2  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd2fb7  ldloc.2
0xd2fb8  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd2fbd  leave.s  loc_D2FC9
0xd2fbf  ldloc.2
0xd2fc0  brfalse.s loc_D2FC8
0xd2fc2  ldloc.2
0xd2fc3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd2fc8  endfinally
0xd2fc9  ldarg.1
0xd2fca  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCellCollection [System.Web]System.Web.UI.WebControls.TableRow::get_Cells()
0xd2fcf  ldloc.0
0xd2fd0  callvirt instance int32 [System.Web]System.Web.UI.WebControls.TableCellCollection::Add(class [System.Web]System.Web.UI.WebControls.TableCell)
0xd2fd5  pop
0xd2fd6  leave.s  loc_D2FE2
0xd2fd8  ldloc.0
0xd2fd9  brfalse.s loc_D2FE1
0xd2fdb  ldloc.0
0xd2fdc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd2fe1  endfinally
0xd2fe2  newobj   instance void [System.Web]System.Web.UI.WebControls.TableCell::.ctor()
0xd2fe7  stloc.3
0xd2fe8  ldloc.3
0xd2fe9  ldstr    aMsCrmListDatac_1// "ms-crm-List-DataCell inner-grid-cellPad"...
0xd2fee  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0xd2ff3  ldarg.1
0xd2ff4  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCellCollection [System.Web]System.Web.UI.WebControls.TableRow::get_Cells()
0xd2ff9  ldloc.3
0xd2ffa  callvirt instance int32 [System.Web]System.Web.UI.WebControls.TableCellCollection::Add(class [System.Web]System.Web.UI.WebControls.TableCell)
0xd2fff  pop
0xd3000  leave.s  loc_D300C
0xd3002  ldloc.3
0xd3003  brfalse.s loc_D300B
0xd3005  ldloc.3
0xd3006  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd300b  endfinally
0xd300c  ret
```
