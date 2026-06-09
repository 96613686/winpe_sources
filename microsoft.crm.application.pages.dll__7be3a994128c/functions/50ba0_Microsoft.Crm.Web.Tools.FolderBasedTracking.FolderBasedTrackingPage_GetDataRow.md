# Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::GetDataRow

- ea: `0x50ba0`
- end: `0x5111c`
- name: `Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::GetDataRow`
- size: `1404`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x505c0`

## callees

- `0x50ba0`
- `0x51120`
- `0x511e0`

## string_xrefs

- `0x50de2`: `' class='ms-crm-Input ms-crm-Text ms-crm-Exchangefolder' type='text' readonly='' value='`
- `0x50e3e`: `' class='ms-crm-Input ms-crm-Text ms-crm-Exchangefolder' type='text' readonly='' value='`
- `0x50fb6`: `/_imgs/ribbon/delete_16.png`
- `0x50fe2`: `delete_`
- `0x51008`: `fnDeleteRow(this)`
- `0x51014`: `ms-crm-folderbasedtracking-table-deleteimage hidden`
- `0x51025`: `FolderBasedTracking.Delete.Tooltip`
- `0x510d5`: `ms-crm-folderbasedtracking-table-deleteimage-column`

## pseudocode

```c

```

## disassembly

```asm
0x50ba0  ldnull
0x50ba1  stloc.0
0x50ba2  ldc.i4.0
0x50ba3  stloc.1
0x50ba4  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRow::.ctor()
0x50ba9  stloc.2
0x50baa  ldloc.2
0x50bab  ldstr    aRow_0// "row_"
0x50bb0  ldarg.3
0x50bb1  box      [mscorlib]System.Int32
0x50bb6  call     string [mscorlib]System.String::Concat(object, object)
0x50bbb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x50bc0  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x50bc5  ldarg.3
0x50bc6  brfalse.s loc_50BCF
0x50bc8  ldstr    aTd_1// "td"
0x50bcd  br.s     loc_50BD4
0x50bcf  ldstr    aTh// "th"
0x50bd4  stloc.3
0x50bd5  ldc.i4.0
0x50bd6  stloc.s  4
0x50bd8  br       loc_51100
0x50bdd  ldloc.3
0x50bde  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::.ctor(string)
0x50be3  stloc.s  5
0x50be5  ldloc.s  5
0x50be7  ldloc.2
0x50be8  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x50bed  ldarg.2
0x50bee  ldloc.s  4
0x50bf0  ldelem.ref
0x50bf1  call     string [mscorlib]System.String::Concat(string, string)
0x50bf6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x50bfb  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x50c00  ldarg.3
0x50c01  brtrue.s loc_50C43
0x50c03  ldloc.2
0x50c04  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x50c09  ldstr    aClass// "class"
0x50c0e  ldstr    aMsCrmFolderbas// "ms-crm-folderbasedtracking-table-header"...
0x50c13  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x50c18  ldloc.s  5
0x50c1a  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x50c1f  ldstr    aClass// "class"
0x50c24  ldstr    aMsCrmFolderbas_0// "ms-crm-folderbasedtracking-table-header"...
0x50c29  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x50c2e  ldloc.s  5
0x50c30  ldarg.1
0x50c31  ldloc.s  4
0x50c33  ldelem.ref
0x50c34  castclass [mscorlib]System.String
0x50c39  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerText(string)
0x50c3e  br       loc_510DF
0x50c43  ldarg.3
0x50c44  ldc.i4.1
0x50c45  sub
0x50c46  ldarg.0
0x50c47  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.MailboxTrackingFolderMappingCollection Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::retrievedFolderMappings
0x50c4c  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.MailboxTrackingFolderMapping>::get_Count()
0x50c51  bge.s    loc_50C62
0x50c53  ldarg.0
0x50c54  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.MailboxTrackingFolderMappingCollection Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::retrievedFolderMappings
0x50c59  ldarg.3
0x50c5a  ldc.i4.1
0x50c5b  sub
0x50c5c  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.MailboxTrackingFolderMapping>::get_Item(!!T0)
0x50c61  stloc.0
0x50c62  ldloc.2
0x50c63  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x50c68  ldstr    aClass// "class"
0x50c6d  ldloc.0
0x50c6e  brfalse.s loc_50C77
0x50c70  ldstr    aMsCrmFolderbas_1// "ms-crm-folderbasedtracking-table-row"
0x50c75  br.s     loc_50C7C
0x50c77  ldstr    aMsCrmFolderbas_2// "ms-crm-folderbasedtracking-table-row hi"...
0x50c7c  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x50c81  ldloc.2
0x50c82  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x50c87  ldstr    aOnmouseover// "onmouseover"
0x50c8c  ldstr    aFnrowhoverinTh// "fnRowHoverIn(this)"
0x50c91  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x50c96  ldloc.2
0x50c97  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x50c9c  ldstr    aOnmouseout// "onmouseout"
0x50ca1  ldstr    aFnrowhoveroutT// "fnRowHoverOut(this)"
0x50ca6  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x50cab  ldloc.s  4
0x50cad  brtrue   loc_50E9B
0x50cb2  ldloc.s  5
0x50cb4  dup
0x50cb5  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::get_InnerHtml()
0x50cba  ldstr    aDivClassMsCrmI// "<div class='ms-crm-Input-Container' id="...
0x50cbf  ldstr    aTxtexchangefol// "txtExchangefolder_"
0x50cc4  ldarg.3
0x50cc5  box      [mscorlib]System.Int32
0x50cca  ldstr    aContainer// "_container"
0x50ccf  call     string [mscorlib]System.String::Concat(object, object, object)
0x50cd4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x50cd9  ldstr    asc_144456// "'>"
0x50cde  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x50ce3  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x50ce8  ldstr    asc_11EF2A// ""
0x50ced  stloc.s  6
0x50cef  ldloc.0
0x50cf0  brfalse  loc_50D8A
0x50cf5  ldloc.0
0x50cf6  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.MailboxTrackingFolderMapping::get_ExchangeFolderId()
0x50cfb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x50d00  brtrue   loc_50D8A
0x50d05  ldarg.0
0x50d06  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::TrackedFolderIds
0x50d0b  dup
0x50d0c  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::get_Value()
0x50d11  ldc.i4.4
0x50d12  newarr   [mscorlib]System.Object
0x50d17  dup
0x50d18  ldc.i4.0
0x50d19  ldloc.0
0x50d1a  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.MailboxTrackingFolderMapping::get_ExchangeFolderId()
0x50d1f  stelem.ref
0x50d20  dup
0x50d21  ldc.i4.1
0x50d22  ldstr    asc_113A60// ";"
0x50d27  stelem.ref
0x50d28  dup
0x50d29  ldc.i4.2
0x50d2a  ldarg.3
0x50d2b  box      [mscorlib]System.Int32
0x50d30  stelem.ref
0x50d31  dup
0x50d32  ldc.i4.3
0x50d33  ldstr    asc_1391FE// "|"
0x50d38  stelem.ref
0x50d39  call     string [mscorlib]System.String::Concat(object[])
0x50d3e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0x50d43  call     string [mscorlib]System.String::Concat(string, string)
0x50d48  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x50d4d  ldarg.0
0x50d4e  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::folderHierarchyIds
0x50d53  ldloc.0
0x50d54  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.MailboxTrackingFolderMapping::get_ExchangeFolderId()
0x50d59  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x50d5e  brtrue.s loc_50D8A
0x50d60  ldloc.0
0x50d61  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.MailboxTrackingFolderMapping::get_ExchangeFolderName()
0x50d66  ldstr    asc_11E6FC// " "
0x50d6b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x50d70  ldstr    aFolderbasedtra_2// "FolderBasedTracking.InvalidFolders.Erro"...
0x50d75  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x50d7a  call     string [mscorlib]System.String::Concat(string, string, string)
0x50d7f  stloc.s  6
0x50d81  ldc.i4.1
0x50d82  stloc.1
0x50d83  ldloc.2
0x50d84  ldc.i4.1
0x50d85  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlControl::set_Disabled(bool)
0x50d8a  ldloc.1
0x50d8b  brfalse.s loc_50E06
0x50d8d  ldloc.s  5
0x50d8f  stloc.s  7
0x50d91  ldloc.s  7
0x50d93  ldc.i4.6
0x50d94  newarr   [mscorlib]System.String
0x50d99  dup
0x50d9a  ldc.i4.0
0x50d9b  ldloc.s  7
0x50d9d  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::get_InnerHtml()
0x50da2  stelem.ref
0x50da3  dup
0x50da4  ldc.i4.1
0x50da5  ldstr    aInputDisabledT// "<input disabled=true id='"
0x50daa  stelem.ref
0x50dab  dup
0x50dac  ldc.i4.2
0x50dad  ldc.i4.4
0x50dae  newarr   [mscorlib]System.Object
0x50db3  dup
0x50db4  ldc.i4.0
0x50db5  ldstr    aTxtinvalidexch// "txtInvalidExchangefolder_"
0x50dba  stelem.ref
0x50dbb  dup
0x50dbc  ldc.i4.1
0x50dbd  ldloc.0
0x50dbe  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.MailboxTrackingFolderMapping::get_ExchangeFolderId()
0x50dc3  stelem.ref
0x50dc4  dup
0x50dc5  ldc.i4.2
0x50dc6  ldstr    asc_113A60// ";"
0x50dcb  stelem.ref
0x50dcc  dup
0x50dcd  ldc.i4.3
0x50dce  ldarg.3
0x50dcf  box      [mscorlib]System.Int32
0x50dd4  stelem.ref
0x50dd5  call     string [mscorlib]System.String::Concat(object[])
0x50dda  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x50ddf  stelem.ref
0x50de0  dup
0x50de1  ldc.i4.3
0x50de2  ldstr    aClassMsCrmInpu// "' class='ms-crm-Input ms-crm-Text ms-cr"...
0x50de7  stelem.ref
0x50de8  dup
0x50de9  ldc.i4.4
0x50dea  ldloc.s  6
0x50dec  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x50df1  stelem.ref
0x50df2  dup
0x50df3  ldc.i4.5
0x50df4  ldstr    asc_15A648// "'/>"
0x50df9  stelem.ref
0x50dfa  call     string [mscorlib]System.String::Concat(string[])
0x50dff  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x50e04  br.s     loc_50E60
0x50e06  ldloc.s  5
0x50e08  stloc.s  7
0x50e0a  ldloc.s  7
0x50e0c  ldc.i4.6
0x50e0d  newarr   [mscorlib]System.String
0x50e12  dup
0x50e13  ldc.i4.0
0x50e14  ldloc.s  7
0x50e16  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::get_InnerHtml()
0x50e1b  stelem.ref
0x50e1c  dup
0x50e1d  ldc.i4.1
0x50e1e  ldstr    aInputId// "<input id='"
0x50e23  stelem.ref
0x50e24  dup
0x50e25  ldc.i4.2
0x50e26  ldstr    aTxtexchangefol// "txtExchangefolder_"
0x50e2b  ldarg.3
0x50e2c  box      [mscorlib]System.Int32
0x50e31  call     string [mscorlib]System.String::Concat(object, object)
0x50e36  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x50e3b  stelem.ref
0x50e3c  dup
0x50e3d  ldc.i4.3
0x50e3e  ldstr    aClassMsCrmInpu// "' class='ms-crm-Input ms-crm-Text ms-cr"...
0x50e43  stelem.ref
0x50e44  dup
0x50e45  ldc.i4.4
0x50e46  ldloc.s  6
0x50e48  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x50e4d  stelem.ref
0x50e4e  dup
0x50e4f  ldc.i4.5
0x50e50  ldstr    aOnclickShowtre// "' onclick='ShowTreeview(this)' onkeyup="...
0x50e55  stelem.ref
0x50e56  call     string [mscorlib]System.String::Concat(string[])
0x50e5b  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x50e60  ldloc.s  5
0x50e62  dup
0x50e63  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::get_InnerHtml()
0x50e68  ldstr    aDiv_1// "</div>"
0x50e6d  call     string [mscorlib]System.String::Concat(string, string)
0x50e72  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x50e77  ldloc.1
0x50e78  brtrue   loc_51068
0x50e7d  ldloc.s  5
0x50e7f  dup
0x50e80  callvirt instance string [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::get_InnerHtml()
0x50e85  ldarg.0
0x50e86  ldarg.3
0x50e87  call     instance string Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::RenderFolderBasedTree(int32 rowId)
0x50e8c  call     string [mscorlib]System.String::Concat(string, string)
0x50e91  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x50e96  br       loc_51068
0x50e9b  ldloc.s  4
0x50e9d  ldc.i4.1
0x50e9e  bne.un   loc_50F5C
0x50ea3  newobj   instance void [System.Web]System.Web.UI.WebControls.Image::.ctor()
0x50ea8  stloc.s  8
0x50eaa  ldloc.1
0x50eab  brfalse.s loc_50EE4
0x50ead  ldloc.s  8
0x50eaf  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x50eb4  ldc.i4.1
0x50eb5  newarr   [mscorlib]System.Char
0x50eba  dup
0x50ebb  ldc.i4.0
0x50ebc  ldc.i4.s 0x2F
0x50ebe  stelem.i2
0x50ebf  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x50ec4  ldstr    aImgsRightDisab// "/_imgs/right_disabled_arrow.png"
0x50ec9  call     string [mscorlib]System.String::Concat(string, string)
0x50ece  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x50ed3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x50ed8  callvirt instance string [mscorlib]System.Object::ToString()
0x50edd  callvirt instance void [System.Web]System.Web.UI.WebControls.Image::set_ImageUrl(string)
0x50ee2  br.s     loc_50F19
0x50ee4  ldloc.s  8
0x50ee6  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x50eeb  ldc.i4.1
0x50eec  newarr   [mscorlib]System.Char
0x50ef1  dup
0x50ef2  ldc.i4.0
0x50ef3  ldc.i4.s 0x2F
0x50ef5  stelem.i2
0x50ef6  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x50efb  ldstr    aImgsOutlookCrm// "/_imgs/outlook_crm.png"
  ... truncated ...
```
