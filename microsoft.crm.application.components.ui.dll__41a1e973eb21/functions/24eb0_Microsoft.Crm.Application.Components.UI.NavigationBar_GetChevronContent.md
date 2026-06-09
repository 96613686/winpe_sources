# Microsoft.Crm.Application.Components.UI.NavigationBar::GetChevronContent

- ea: `0x24eb0`
- end: `0x25050`
- name: `Microsoft.Crm.Application.Components.UI.NavigationBar::GetChevronContent`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x24c60`

## callees

- `0x142c0`
- `0x1a0a0`
- `0x1a0d0`
- `0x1a350`
- `0x1a390`
- `0x24eb0`

## pseudocode

```c

```

## disassembly

```asm
0x24eb0  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x24eb5  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x24eba  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x24ebf  stloc.0
0x24ec0  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::.ctor()
0x24ec5  stloc.1
0x24ec6  ldloc.1
0x24ec7  ldstr    aCenter// "center"
0x24ecc  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_Align(string)
0x24ed1  ldloc.1
0x24ed2  ldstr    aTop// "top"
0x24ed7  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_VAlign(string)
0x24edc  ldstr    aSpan_7// "Span"
0x24ee1  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x24ee6  stloc.2
0x24ee7  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::.ctor()
0x24eec  stloc.3
0x24eed  ldloc.3
0x24eee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24ef3  ldstr    a01_3// "{0}_{1}"
0x24ef8  ldc.i4.2
0x24ef9  newarr   [mscorlib]System.Object
0x24efe  dup
0x24eff  ldc.i4.0
0x24f00  ldarg.0
0x24f01  stelem.ref
0x24f02  dup
0x24f03  ldc.i4.1
0x24f04  ldstr    aPaneimage// "paneImage"
0x24f09  stelem.ref
0x24f0a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24f0f  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x24f14  ldloc.0
0x24f15  brfalse.s loc_24F59
0x24f17  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x24f1c  ldc.i4.1
0x24f1d  newarr   [mscorlib]System.Char
0x24f22  dup
0x24f23  ldc.i4.0
0x24f24  ldc.i4.s 0x2F
0x24f26  stelem.i2
0x24f27  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x24f2c  ldstr    aImgsNavleftPng// "/_imgs/navleft.png"
0x24f31  call     string [mscorlib]System.String::Concat(string, string)
0x24f36  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24f3b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x24f40  stloc.s  4
0x24f42  ldloc.3
0x24f43  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x24f48  ldstr    aImgbase// "imgBase"
0x24f4d  ldstr    aImgsNavleft// "/_imgs/navLeft"
0x24f52  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x24f57  br.s     loc_24F99
0x24f59  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x24f5e  ldc.i4.1
0x24f5f  newarr   [mscorlib]System.Char
0x24f64  dup
0x24f65  ldc.i4.0
0x24f66  ldc.i4.s 0x2F
0x24f68  stelem.i2
0x24f69  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x24f6e  ldstr    aImgsNavrightPn// "/_imgs/navright.png"
0x24f73  call     string [mscorlib]System.String::Concat(string, string)
0x24f78  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24f7d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x24f82  stloc.s  4
0x24f84  ldloc.3
0x24f85  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x24f8a  ldstr    aImgbase// "imgBase"
0x24f8f  ldstr    aImgsNavright// "/_imgs/navRight"
0x24f94  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x24f99  call     class Microsoft.Crm.Application.Components.UI.ImageStrip Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x24f9e  ldloc.s  4
0x24fa0  callvirt instance class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri imagePath)
0x24fa5  stloc.s  5
0x24fa7  ldloc.3
0x24fa8  ldloc.s  5
0x24faa  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x24faf  callvirt instance string [mscorlib]System.Object::ToString()
0x24fb4  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x24fb9  ldloc.3
0x24fba  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x24fbf  ldstr    aClass_1// "class"
0x24fc4  ldloc.s  5
0x24fc6  callvirt instance string Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x24fcb  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x24fd0  ldloc.3
0x24fd1  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x24fd6  ldstr    aTitle_2// "title"
0x24fdb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24fe0  ldstr    aNavbarCollapse// "NavBar_Collapsed_ToolTip"
0x24fe5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24fea  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x24fef  ldloc.3
0x24ff0  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x24ff5  ldstr    aAlt// "alt"
0x24ffa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24fff  ldstr    aNavbarCollapse// "NavBar_Collapsed_ToolTip"
0x25004  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x25009  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x2500e  ldloc.2
0x2500f  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x25014  ldloc.3
0x25015  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2501a  leave.s  loc_25026
0x2501c  ldloc.3
0x2501d  brfalse.s loc_25025
0x2501f  ldloc.3
0x25020  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25025  endfinally
0x25026  ldloc.1
0x25027  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x2502c  ldloc.2
0x2502d  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x25032  leave.s  loc_2503E
0x25034  ldloc.2
0x25035  brfalse.s loc_2503D
0x25037  ldloc.2
0x25038  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2503d  endfinally
0x2503e  ldloc.1
0x2503f  stloc.s  6
0x25041  leave.s  loc_2504D
0x25043  ldloc.1
0x25044  brfalse.s loc_2504C
0x25046  ldloc.1
0x25047  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2504c  endfinally
0x2504d  ldloc.s  6
0x2504f  ret
```
