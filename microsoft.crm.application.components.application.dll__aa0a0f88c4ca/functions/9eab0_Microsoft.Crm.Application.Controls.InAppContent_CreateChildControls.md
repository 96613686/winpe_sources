# Microsoft.Crm.Application.Controls.InAppContent::CreateChildControls

- ea: `0x9eab0`
- end: `0x9edf3`
- name: `Microsoft.Crm.Application.Controls.InAppContent::CreateChildControls`
- size: `835`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x6890`
- `0x9e6d0`
- `0x9e720`
- `0x9e750`
- `0x9ea20`
- `0x9eab0`

## string_xrefs

- `0x9ebb3`: `SECURITY`
- `0x9ebe1`: `inPageHelpCollapseLink`
- `0x9ec8c`: `/_imgs/helpvisor/visoropen.png`

## pseudocode

```c

```

## disassembly

```asm
0x9eab0  ldarg.0
0x9eab1  ldfld    bool Microsoft.Crm.Application.Controls.InAppContent::getStartedPaneContentEnabled
0x9eab6  brfalse  loc_9EDF2
0x9eabb  ldarg.0
0x9eabc  call     instance string Microsoft.Crm.Application.Controls.InAppContent::get_ContentPath()
0x9eac1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9eac6  brfalse.s loc_9EAD3
0x9eac8  ldarg.0
0x9eac9  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea Microsoft.Crm.Application.Controls.InAppContent::subArea
0x9eace  brfalse  loc_9EDF2
0x9ead3  ldarg.0
0x9ead4  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x9ead9  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Clear()
0x9eade  ldarg.0
0x9eadf  call     instance string Microsoft.Crm.Application.Controls.InAppContent::get_ContentPath()
0x9eae4  dup
0x9eae5  brtrue.s loc_9EAF3
0x9eae7  pop
0x9eae8  ldarg.0
0x9eae9  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea Microsoft.Crm.Application.Controls.InAppContent::subArea
0x9eaee  call     string Microsoft.Crm.Utility.HelpUtility::GetHelpPathFromSiteMapSubArea(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea subArea)
0x9eaf3  stloc.0
0x9eaf4  ldloc.0
0x9eaf5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9eafa  brfalse.s loc_9EAFD
0x9eafc  ret
0x9eafd  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsLive()
0x9eb02  stloc.1
0x9eb03  ldloc.0
0x9eb04  ldarg.0
0x9eb05  ldfld    string Microsoft.Crm.Application.Controls.InAppContent::siteMapPath
0x9eb0a  ldloca.s 1
0x9eb0c  call     string Microsoft.Crm.Application.Controls.InAppContent::GetHelpPath(string path, string siteMapPath, bool& setRestricted)
0x9eb11  stloc.0
0x9eb12  ldstr    aIframe// "iframe"
0x9eb17  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x9eb1c  stloc.2
0x9eb1d  ldloc.2
0x9eb1e  ldstr    aInpagehelpifra// "inPageHelpIframe"
0x9eb23  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x9eb28  ldloc.2
0x9eb29  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x9eb2e  ldstr    aName// "name"
0x9eb33  ldstr    aInpagehelpifra// "inPageHelpIframe"
0x9eb38  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x9eb3d  ldloc.2
0x9eb3e  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x9eb43  ldstr    aTitle// "title"
0x9eb48  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9eb4d  ldstr    aWebInpagehelpA// "Web.InPageHelp.AltText"
0x9eb52  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9eb57  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x9eb5c  ldloc.2
0x9eb5d  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x9eb62  ldstr    aFrameborder_0// "frameBorder"
0x9eb67  ldstr    a0// "0"
0x9eb6c  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x9eb71  ldloc.2
0x9eb72  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x9eb77  ldstr    aScrolling// "scrolling"
0x9eb7c  ldstr    aNo_0// "no"
0x9eb81  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x9eb86  ldloc.2
0x9eb87  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x9eb8c  ldstr    aSrc// "src"
0x9eb91  ldstr    aStaticBlankHtm// "/_static/blank.htm"
0x9eb96  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9eb9b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9eba0  callvirt instance string [mscorlib]System.Object::ToString()
0x9eba5  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x9ebaa  ldloc.1
0x9ebab  brfalse.s loc_9EBC2
0x9ebad  ldloc.2
0x9ebae  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x9ebb3  ldstr    aSecurity_0// "SECURITY"
0x9ebb8  ldstr    aRestricted// "restricted"
0x9ebbd  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x9ebc2  ldstr    aDiv_3// "div"
0x9ebc7  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0x9ebcc  stloc.3
0x9ebcd  ldloc.3
0x9ebce  ldstr    aInpagehelpcoll_0// "inPageHelpCollapseDiv"
0x9ebd3  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x9ebd8  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::.ctor()
0x9ebdd  stloc.s  4
0x9ebdf  ldloc.s  4
0x9ebe1  ldstr    aInpagehelpcoll_1// "inPageHelpCollapseLink"
0x9ebe6  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x9ebeb  ldloc.s  4
0x9ebed  ldstr    aJavascript// "javascript:;"
0x9ebf2  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlAnchor::set_HRef(string)
0x9ebf7  ldloc.s  4
0x9ebf9  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x9ebfe  ldstr    aOnclick// "onclick"
0x9ec03  ldstr    aReturnFalse_1// "return false;"
0x9ec08  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x9ec0d  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::.ctor()
0x9ec12  stloc.s  5
0x9ec14  ldloc.s  5
0x9ec16  ldstr    aInpagehelpcoll_2// "inPageHelpCollapseImage"
0x9ec1b  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x9ec20  ldarg.0
0x9ec21  call     instance bool Microsoft.Crm.Application.Controls.InAppContent::get_IsVisible()
0x9ec26  brfalse  loc_9ECC4
0x9ec2b  ldarg.0
0x9ec2c  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x9ec31  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x9ec36  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsIosDevice(class [System.Web]System.Web.HttpRequest)
0x9ec3b  brtrue   loc_9ECC4
0x9ec40  ldstr    a1_0// "1"
0x9ec45  stloc.s  6
0x9ec47  ldloc.3
0x9ec48  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x9ec4d  ldstr    aClass_0// "class"
0x9ec52  ldstr    aVisorSliverUp// "visor-sliver-up"
0x9ec57  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x9ec5c  ldloc.3
0x9ec5d  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x9ec62  ldstr    aTitle// "title"
0x9ec67  ldarg.0
0x9ec68  ldfld    string Microsoft.Crm.Application.Controls.InAppContent::clickToCollapse
0x9ec6d  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x9ec72  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x9ec77  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x9ec7c  ldc.i4.1
0x9ec7d  newarr   [mscorlib]System.Char
0x9ec82  dup
0x9ec83  ldc.i4.0
0x9ec84  ldc.i4.s 0x2F
0x9ec86  stelem.i2
0x9ec87  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x9ec8c  ldstr    aImgsHelpvisorV// "/_imgs/helpvisor/visoropen.png"
0x9ec91  call     string [mscorlib]System.String::Concat(string, string)
0x9ec96  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9ec9b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9eca0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x9eca5  stloc.s  7
0x9eca7  ldloc.s  5
0x9eca9  ldarg.0
0x9ecaa  ldfld    string Microsoft.Crm.Application.Controls.InAppContent::clickToCollapse
0x9ecaf  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Alt(string)
0x9ecb4  ldarg.0
0x9ecb5  ldc.i4   0x97
0x9ecba  call     instance void Microsoft.Crm.Application.Controls.InAppContent::set_RenderedHeight(int32 value)
0x9ecbf  br       loc_9ED6A
0x9ecc4  ldloc.2
0x9ecc5  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x9ecca  ldstr    aDisplay// "display"
0x9eccf  ldstr    aNone// "none"
0x9ecd4  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::set_Item(string, string)
0x9ecd9  ldstr    a0// "0"
0x9ecde  stloc.s  6
0x9ece0  ldloc.3
0x9ece1  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x9ece6  ldstr    aClass_0// "class"
0x9eceb  ldstr    aVisorSliverDn// "visor-sliver-dn"
0x9ecf0  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x9ecf5  ldloc.3
0x9ecf6  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x9ecfb  ldstr    aTitle// "title"
0x9ed00  ldarg.0
0x9ed01  ldfld    string Microsoft.Crm.Application.Controls.InAppContent::clickToExpand
0x9ed06  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x9ed0b  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x9ed10  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x9ed15  ldc.i4.1
0x9ed16  newarr   [mscorlib]System.Char
0x9ed1b  dup
0x9ed1c  ldc.i4.0
0x9ed1d  ldc.i4.s 0x2F
0x9ed1f  stelem.i2
0x9ed20  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x9ed25  ldstr    aImgsHelpvisorV_0// "/_imgs/helpvisor/visorclose.png"
0x9ed2a  call     string [mscorlib]System.String::Concat(string, string)
0x9ed2f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x9ed34  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9ed39  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x9ed3e  stloc.s  7
0x9ed40  ldloc.s  5
0x9ed42  ldarg.0
0x9ed43  ldfld    string Microsoft.Crm.Application.Controls.InAppContent::clickToExpand
0x9ed48  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Alt(string)
0x9ed4d  ldarg.0
0x9ed4e  ldc.i4.s 0xC
0x9ed50  call     instance void Microsoft.Crm.Application.Controls.InAppContent::set_RenderedHeight(int32 value)
0x9ed55  ldarg.0
0x9ed56  call     instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x9ed5b  ldstr    aStyle_0// "style"
0x9ed60  ldstr    aBorderWidth0px// "border-width: 0px"
0x9ed65  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x9ed6a  ldloc.s  5
0x9ed6c  ldloc.s  7
0x9ed6e  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x9ed73  callvirt instance string [mscorlib]System.Object::ToString()
0x9ed78  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x9ed7d  ldloc.s  5
0x9ed7f  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x9ed84  ldstr    aClass_0// "class"
0x9ed89  ldloc.s  7
0x9ed8b  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x9ed90  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x9ed95  ldloc.s  4
0x9ed97  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x9ed9c  ldloc.s  5
0x9ed9e  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x9eda3  ldloc.3
0x9eda4  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x9eda9  ldloc.s  4
0x9edab  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x9edb0  ldarg.0
0x9edb1  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x9edb6  ldloc.2
0x9edb7  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x9edbc  ldarg.0
0x9edbd  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x9edc2  ldloc.3
0x9edc3  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x9edc8  ldarg.0
0x9edc9  call     instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x9edce  ldstr    aExpanded// "expanded"
0x9edd3  ldloc.s  6
0x9edd5  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x9edda  ldarg.0
0x9eddb  call     instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x9ede0  ldstr    aSrc// "src"
0x9ede5  ldloc.0
0x9ede6  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::set_Item(string, string)
0x9edeb  ldarg.0
0x9edec  ldc.i4.1
0x9eded  stfld    bool Microsoft.Crm.Application.Controls.InAppContent::isRendered
0x9edf2  ret
```
