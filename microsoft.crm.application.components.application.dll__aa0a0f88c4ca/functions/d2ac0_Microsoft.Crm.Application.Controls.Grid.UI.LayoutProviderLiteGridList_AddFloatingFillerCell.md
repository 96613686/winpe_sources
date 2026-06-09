# Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderLiteGridList::AddFloatingFillerCell

- ea: `0xd2ac0`
- end: `0xd2d74`
- name: `Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderLiteGridList::AddFloatingFillerCell`
- size: `692`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0xcd620`
- `0xcd6b0`
- `0xd25f0`
- `0xd29e0`

## callees

- `0xcd240`
- `0xcd7f0`
- `0xd2ac0`

## string_xrefs

- `0xd2b21`: `deleteAction`
- `0xd2b66`: `deleteAction`
- `0xd2b2b`: `Delete`
- `0xd2adb`: `ms-crm-List-DeleteContainer`
- `0xd2ae1`: `ms-crm-List-DeleteContainer-Div`
- `0xd2ae7`: `ms-crm-List-DeleteButton`
- `0xd2aee`: `Mscrm.GridControlLite.DeleteRecordLite(this)`
- `0xd2b0a`: `/_imgs/grid/actions_delete_bin_16.png`
- `0xd2b47`: `ToolTip_GridDeleteAction`
- `0xd2be4`: `ToolTip_GridDeleteAction`
- `0xd2b70`: `Remove`
- `0xd2b8c`: `ToolTip_GridRemoveAction`
- `0xd2c67`: `delete_`

## pseudocode

```c

```

## disassembly

```asm
0xd2ac0  newobj   instance void [System.Web]System.Web.UI.WebControls.TableCell::.ctor()
0xd2ac5  stloc.0
0xd2ac6  ldnull
0xd2ac7  stloc.1
0xd2ac8  ldnull
0xd2ac9  stloc.2
0xd2aca  ldnull
0xd2acb  stloc.3
0xd2acc  ldnull
0xd2acd  stloc.s  4
0xd2acf  ldnull
0xd2ad0  stloc.s  5
0xd2ad2  ldnull
0xd2ad3  stloc.s  6
0xd2ad5  ldstr    aGriddelbtn// "gridDelBtn"
0xd2ada  stloc.1
0xd2adb  ldstr    aMsCrmListDelet// "ms-crm-List-DeleteContainer"
0xd2ae0  stloc.2
0xd2ae1  ldstr    aMsCrmListDelet_0// "ms-crm-List-DeleteContainer-Div"
0xd2ae6  stloc.3
0xd2ae7  ldstr    aMsCrmListDelet_1// "ms-crm-List-DeleteButton"
0xd2aec  stloc.s  4
0xd2aee  ldstr    aMscrmGridcontr_6// "Mscrm.GridControlLite.DeleteRecordLite("...
0xd2af3  stloc.s  5
0xd2af5  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xd2afa  ldc.i4.1
0xd2afb  newarr   [mscorlib]System.Char
0xd2b00  dup
0xd2b01  ldc.i4.0
0xd2b02  ldc.i4.s 0x2F
0xd2b04  stelem.i2
0xd2b05  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xd2b0a  ldstr    aImgsGridAction_0// "/_imgs/grid/actions_delete_bin_16.png"
0xd2b0f  call     string [mscorlib]System.String::Concat(string, string)
0xd2b14  stloc.s  6
0xd2b16  ldarg.0
0xd2b17  call     instance class Microsoft.Crm.Application.Controls.Grid.UI.LayoutDescriptor Microsoft.Crm.Application.Controls.Grid.UI.LayoutProvider::get_LayoutDescriptor()
0xd2b1c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Controls.Grid.UI.LayoutDescriptor::get_Parameters()
0xd2b21  ldstr    aDeleteaction// "deleteAction"
0xd2b26  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xd2b2b  ldstr    aDelete_0// "Delete"
0xd2b30  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd2b35  brfalse.s loc_D2B5B
0xd2b37  ldloc.0
0xd2b38  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0xd2b3d  ldstr    aTitle// "title"
0xd2b42  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd2b47  ldstr    aTooltipGriddel// "ToolTip_GridDeleteAction"
0xd2b4c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd2b51  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xd2b56  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0xd2b5b  ldarg.0
0xd2b5c  call     instance class Microsoft.Crm.Application.Controls.Grid.UI.LayoutDescriptor Microsoft.Crm.Application.Controls.Grid.UI.LayoutProvider::get_LayoutDescriptor()
0xd2b61  callvirt instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Controls.Grid.UI.LayoutDescriptor::get_Parameters()
0xd2b66  ldstr    aDeleteaction// "deleteAction"
0xd2b6b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xd2b70  ldstr    aRemove_0// "Remove"
0xd2b75  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd2b7a  brfalse.s loc_D2BA0
0xd2b7c  ldloc.0
0xd2b7d  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.WebControls.WebControl::get_Attributes()
0xd2b82  ldstr    aTitle// "title"
0xd2b87  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd2b8c  ldstr    aTooltipGridrem// "ToolTip_GridRemoveAction"
0xd2b91  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd2b96  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xd2b9b  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0xd2ba0  ldloc.0
0xd2ba1  ldloc.1
0xd2ba2  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xd2ba7  ldloc.0
0xd2ba8  ldloc.2
0xd2ba9  callvirt instance void [System.Web]System.Web.UI.WebControls.WebControl::set_CssClass(string)
0xd2bae  ldstr    aDiv_3// "div"
0xd2bb3  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xd2bb8  stloc.s  7
0xd2bba  ldloc.s  7
0xd2bbc  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd2bc1  ldstr    aClass_0// "class"
0xd2bc6  ldloc.3
0xd2bc7  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0xd2bcc  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::.ctor()
0xd2bd1  stloc.s  8
0xd2bd3  ldloc.s  8
0xd2bd5  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd2bda  ldstr    aTitle// "title"
0xd2bdf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd2be4  ldstr    aTooltipGriddel// "ToolTip_GridDeleteAction"
0xd2be9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd2bee  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0xd2bf3  ldloc.s  8
0xd2bf5  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd2bfa  ldstr    aClass_0// "class"
0xd2bff  ldloc.s  4
0xd2c01  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0xd2c06  ldloc.s  8
0xd2c08  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0xd2c0d  ldstr    aVisibility// "visibility"
0xd2c12  ldstr    aHidden// "hidden"
0xd2c17  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0xd2c1c  ldloc.s  8
0xd2c1e  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd2c23  ldstr    aTabindex// "tabindex"
0xd2c28  ldarg.0
0xd2c29  call     instance class Microsoft.Crm.Application.Controls.Grid.UI.LayoutDescriptor Microsoft.Crm.Application.Controls.Grid.UI.LayoutProvider::get_LayoutDescriptor()
0xd2c2e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Controls.Grid.UI.LayoutDescriptor::get_Parameters()
0xd2c33  ldstr    aTabindex// "tabindex"
0xd2c38  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xd2c3d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd2c42  brfalse.s loc_D2C4B
0xd2c44  ldstr    a0// "0"
0xd2c49  br.s     loc_D2C60
0xd2c4b  ldarg.0
0xd2c4c  call     instance class Microsoft.Crm.Application.Controls.Grid.UI.LayoutDescriptor Microsoft.Crm.Application.Controls.Grid.UI.LayoutProvider::get_LayoutDescriptor()
0xd2c51  callvirt instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Application.Controls.Grid.UI.LayoutDescriptor::get_Parameters()
0xd2c56  ldstr    aTabindex// "tabindex"
0xd2c5b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xd2c60  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0xd2c65  ldloc.s  8
0xd2c67  ldstr    aDelete_1// "delete_"
0xd2c6c  ldarg.2
0xd2c6d  ldstr    aRowid// "RowId"
0xd2c72  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0xd2c77  callvirt instance string [mscorlib]System.Object::ToString()
0xd2c7c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xd2c81  call     string [mscorlib]System.String::Concat(string, string)
0xd2c86  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xd2c8b  ldloc.s  8
0xd2c8d  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd2c92  ldstr    aHref// "href"
0xd2c97  ldstr    aJavascriptVoid_1// "javascript:void(0);"
0xd2c9c  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0xd2ca1  ldloc.s  8
0xd2ca3  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xd2ca8  ldstr    aOnclick// "onclick"
0xd2cad  ldloc.s  5
0xd2caf  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0xd2cb4  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0xd2cb9  ldloc.s  6
0xd2cbb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd2cc0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd2cc5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xd2cca  stloc.s  9
0xd2ccc  ldloc.s  8
0xd2cce  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd2cd3  ldc.i4.5
0xd2cd4  newarr   [mscorlib]System.String
0xd2cd9  dup
0xd2cda  ldc.i4.0
0xd2cdb  ldstr    aImgAltSrc_0// "<img alt=\"\" src=\""
0xd2ce0  stelem.ref
0xd2ce1  dup
0xd2ce2  ldc.i4.1
0xd2ce3  ldloc.s  9
0xd2ce5  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0xd2cea  callvirt instance string [mscorlib]System.Object::ToString()
0xd2cef  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xd2cf4  stelem.ref
0xd2cf5  dup
0xd2cf6  ldc.i4.2
0xd2cf7  ldstr    aClass_2// "\" class=\""
0xd2cfc  stelem.ref
0xd2cfd  dup
0xd2cfe  ldc.i4.3
0xd2cff  ldloc.s  9
0xd2d01  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0xd2d06  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xd2d0b  stelem.ref
0xd2d0c  dup
0xd2d0d  ldc.i4.4
0xd2d0e  ldstr    asc_1221F6// "\" >"
0xd2d13  stelem.ref
0xd2d14  call     string [mscorlib]System.String::Concat(string[])
0xd2d19  newobj   instance void [System.Web]System.Web.UI.LiteralControl::.ctor(string)
0xd2d1e  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd2d23  ldloc.s  7
0xd2d25  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd2d2a  ldloc.s  8
0xd2d2c  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd2d31  leave.s  loc_D2D3F
0xd2d33  ldloc.s  8
0xd2d35  brfalse.s loc_D2D3E
0xd2d37  ldloc.s  8
0xd2d39  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd2d3e  endfinally
0xd2d3f  ldloc.0
0xd2d40  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd2d45  ldloc.s  7
0xd2d47  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd2d4c  leave.s  loc_D2D5A
0xd2d4e  ldloc.s  7
0xd2d50  brfalse.s loc_D2D59
0xd2d52  ldloc.s  7
0xd2d54  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd2d59  endfinally
0xd2d5a  ldarg.1
0xd2d5b  callvirt instance class [System.Web]System.Web.UI.WebControls.TableCellCollection [System.Web]System.Web.UI.WebControls.TableRow::get_Cells()
0xd2d60  ldloc.0
0xd2d61  callvirt instance int32 [System.Web]System.Web.UI.WebControls.TableCellCollection::Add(class [System.Web]System.Web.UI.WebControls.TableCell)
0xd2d66  pop
0xd2d67  leave.s  loc_D2D73
0xd2d69  ldloc.0
0xd2d6a  brfalse.s loc_D2D72
0xd2d6c  ldloc.0
0xd2d6d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd2d72  endfinally
0xd2d73  ret
```
