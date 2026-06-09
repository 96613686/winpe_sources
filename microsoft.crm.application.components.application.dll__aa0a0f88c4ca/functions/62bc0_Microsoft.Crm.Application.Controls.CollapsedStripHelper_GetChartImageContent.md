# Microsoft.Crm.Application.Controls.CollapsedStripHelper::GetChartImageContent

- ea: `0x62bc0`
- end: `0x62d8d`
- name: `Microsoft.Crm.Application.Controls.CollapsedStripHelper::GetChartImageContent`
- size: `461`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x62a10`
- `0x62af0`

## callees

- `0x62bc0`

## string_xrefs

- `0x62c33`: `/_imgs/visualization/chartsidelite.png`
- `0x62c78`: `/_imgs/visualization/chartsidelite.png`
- `0x62c3a`: `/_imgs/visualization/chartsidelite_VisualRefresh.png`
- `0x62c7f`: `/_imgs/visualization/chartsidelite_VisualRefresh.png`
- `0x62cda`: `/_imgs/visualization/chartsidelitetopbottom.png`
- `0x62d1f`: `/_imgs/visualization/chartsidelitetopbottom.png`
- `0x62ce1`: `/_imgs/visualization/chartsidelitetopbottom_VisualRefresh.png`
- `0x62d26`: `/_imgs/visualization/chartsidelitetopbottom_VisualRefresh.png`

## pseudocode

```c

```

## disassembly

```asm
0x62bc0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x62bc5  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsWebClientVisualRefreshFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x62bca  stloc.0
0x62bcb  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::.ctor()
0x62bd0  stloc.1
0x62bd1  ldloc.1
0x62bd2  ldstr    aCenter// "center"
0x62bd7  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_Align(string)
0x62bdc  ldarg.0
0x62bdd  brfalse.s loc_62BF7
0x62bdf  ldloc.1
0x62be0  ldstr    a37px// "37px"
0x62be5  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_Width(string)
0x62bea  ldloc.1
0x62beb  ldstr    aTop// "top"
0x62bf0  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_VAlign(string)
0x62bf5  br.s     loc_62C02
0x62bf7  ldloc.1
0x62bf8  ldstr    a70// "70%"
0x62bfd  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_Width(string)
0x62c02  ldstr    aSpan_4// "Span"
0x62c07  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x62c0c  stloc.2
0x62c0d  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::.ctor()
0x62c12  stloc.3
0x62c13  ldarg.0
0x62c14  brfalse.s loc_62C93
0x62c16  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x62c1b  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x62c20  ldc.i4.1
0x62c21  newarr   [mscorlib]System.Char
0x62c26  dup
0x62c27  ldc.i4.0
0x62c28  ldc.i4.s 0x2F
0x62c2a  stelem.i2
0x62c2b  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x62c30  ldloc.0
0x62c31  brtrue.s loc_62C3A
0x62c33  ldstr    aImgsVisualizat_3// "/_imgs/visualization/chartsidelite.png"
0x62c38  br.s     loc_62C3F
0x62c3a  ldstr    aImgsVisualizat_4// "/_imgs/visualization/chartsidelite_Visu"...
0x62c3f  call     string [mscorlib]System.String::Concat(string, string)
0x62c44  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x62c49  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x62c4e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x62c53  stloc.s  4
0x62c55  ldloc.3
0x62c56  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x62c5b  ldstr    aImgbase// "imgBase"
0x62c60  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x62c65  ldc.i4.1
0x62c66  newarr   [mscorlib]System.Char
0x62c6b  dup
0x62c6c  ldc.i4.0
0x62c6d  ldc.i4.s 0x2F
0x62c6f  stelem.i2
0x62c70  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x62c75  ldloc.0
0x62c76  brtrue.s loc_62C7F
0x62c78  ldstr    aImgsVisualizat_3// "/_imgs/visualization/chartsidelite.png"
0x62c7d  br.s     loc_62C84
0x62c7f  ldstr    aImgsVisualizat_4// "/_imgs/visualization/chartsidelite_Visu"...
0x62c84  call     string [mscorlib]System.String::Concat(string, string)
0x62c89  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x62c8e  br       loc_62D35
0x62c93  ldloc.2
0x62c94  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x62c99  ldstr    aPosition// "position"
0x62c9e  ldstr    aAbsolute// "absolute"
0x62ca3  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x62ca8  ldloc.2
0x62ca9  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x62cae  ldstr    aTop// "top"
0x62cb3  ldstr    a0px// "0px"
0x62cb8  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x62cbd  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x62cc2  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x62cc7  ldc.i4.1
0x62cc8  newarr   [mscorlib]System.Char
0x62ccd  dup
0x62cce  ldc.i4.0
0x62ccf  ldc.i4.s 0x2F
0x62cd1  stelem.i2
0x62cd2  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x62cd7  ldloc.0
0x62cd8  brtrue.s loc_62CE1
0x62cda  ldstr    aImgsVisualizat_5// "/_imgs/visualization/chartsidelitetopbo"...
0x62cdf  br.s     loc_62CE6
0x62ce1  ldstr    aImgsVisualizat_6// "/_imgs/visualization/chartsidelitetopbo"...
0x62ce6  call     string [mscorlib]System.String::Concat(string, string)
0x62ceb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x62cf0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x62cf5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x62cfa  stloc.s  4
0x62cfc  ldloc.3
0x62cfd  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x62d02  ldstr    aImgbase// "imgBase"
0x62d07  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x62d0c  ldc.i4.1
0x62d0d  newarr   [mscorlib]System.Char
0x62d12  dup
0x62d13  ldc.i4.0
0x62d14  ldc.i4.s 0x2F
0x62d16  stelem.i2
0x62d17  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x62d1c  ldloc.0
0x62d1d  brtrue.s loc_62D26
0x62d1f  ldstr    aImgsVisualizat_5// "/_imgs/visualization/chartsidelitetopbo"...
0x62d24  br.s     loc_62D2B
0x62d26  ldstr    aImgsVisualizat_6// "/_imgs/visualization/chartsidelitetopbo"...
0x62d2b  call     string [mscorlib]System.String::Concat(string, string)
0x62d30  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x62d35  ldloc.3
0x62d36  ldloc.s  4
0x62d38  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x62d3d  callvirt instance string [mscorlib]System.Object::ToString()
0x62d42  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x62d47  ldloc.3
0x62d48  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x62d4d  ldstr    aClass_0// "class"
0x62d52  ldloc.s  4
0x62d54  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x62d59  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x62d5e  ldloc.3
0x62d5f  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x62d64  ldstr    aAlt// "alt"
0x62d69  ldstr    asc_F537C// ""
0x62d6e  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x62d73  ldloc.2
0x62d74  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x62d79  ldloc.3
0x62d7a  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x62d7f  ldloc.1
0x62d80  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x62d85  ldloc.2
0x62d86  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x62d8b  ldloc.1
0x62d8c  ret
```
