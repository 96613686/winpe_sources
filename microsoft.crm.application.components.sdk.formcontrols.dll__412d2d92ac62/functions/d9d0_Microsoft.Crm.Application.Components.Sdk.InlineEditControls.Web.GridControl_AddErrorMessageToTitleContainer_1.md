# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddErrorMessageToTitleContainer_1

- ea: `0xd9d0`
- end: `0xdb9e`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddErrorMessageToTitleContainer_1`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xbee0`

## callees

- `0xd9d0`
- `0x17a10`

## string_xrefs

- `0xda55`: `ErrorStatusLink_`

## pseudocode

```c

```

## disassembly

```asm
0xd9d0  ldnull
0xd9d1  stloc.0
0xd9d2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xd9d7  ldstr    aInlineeditWarn// "InlineEdit_WarningIcon_AltText"
0xd9dc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd9e1  stloc.1
0xd9e2  ldarg.0
0xd9e3  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0xd9e8  stloc.s  6
0xd9ea  ldloca.s 6
0xd9ec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd9f1  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xd9f6  stloc.2
0xd9f7  ldarg.0
0xd9f8  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xd9fd  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xda02  stloc.3
0xda03  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0xda08  ldc.i4.1
0xda09  newarr   [mscorlib]System.Char
0xda0e  dup
0xda0f  ldc.i4.0
0xda10  ldc.i4.s 0x2F
0xda12  stelem.i2
0xda13  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xda18  ldstr    aImgsInlineedit_4// "/_imgs/inlineedit/warning.png"
0xda1d  call     string [mscorlib]System.String::Concat(string, string)
0xda22  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xda27  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xda2c  stloc.s  4
0xda2e  call     class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0xda33  ldloc.s  4
0xda35  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xda3a  stloc.s  5
0xda3c  ldstr    aDiv// "div"
0xda41  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xda46  dup
0xda47  stloc.0
0xda48  stloc.s  7
0xda4a  ldloc.0
0xda4b  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xda50  ldstr    aId// "id"
0xda55  ldstr    aErrorstatuslin// "ErrorStatusLink_"
0xda5a  ldloc.3
0xda5b  call     string [mscorlib]System.String::Concat(string, string)
0xda60  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xda65  ldloc.0
0xda66  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xda6b  ldstr    aClass// "class"
0xda70  ldstr    aMsCrmListError// "ms-crm-List-ErrorStatusIcon"
0xda75  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xda7a  ldstr    aA// "a"
0xda7f  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xda84  stloc.s  8
0xda86  ldloc.s  8
0xda88  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xda8d  ldstr    aHref// "href"
0xda92  ldstr    asc_3002A// "#"
0xda97  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xda9c  ldloc.s  8
0xda9e  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdaa3  ldstr    aOnclick// "onclick"
0xdaa8  ldstr    aReturnFalse// "return false;"
0xdaad  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdab2  ldloc.s  8
0xdab4  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdab9  ldstr    aId// "id"
0xdabe  ldstr    aErrorstatusico// "ErrorStatusIcon_"
0xdac3  ldloc.3
0xdac4  call     string [mscorlib]System.String::Concat(string, string)
0xdac9  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdace  ldloc.s  8
0xdad0  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdad5  ldstr    aTabindex// "tabindex"
0xdada  ldloc.2
0xdadb  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdae0  ldstr    aImg// "img"
0xdae5  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xdaea  stloc.s  9
0xdaec  ldloc.s  9
0xdaee  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdaf3  ldstr    aSrc// "src"
0xdaf8  ldloc.s  5
0xdafa  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0xdaff  callvirt instance string [mscorlib]System.Object::ToString()
0xdb04  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xdb09  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdb0e  ldloc.s  9
0xdb10  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdb15  ldstr    aAlt// "alt"
0xdb1a  ldloc.1
0xdb1b  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdb20  ldloc.s  9
0xdb22  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdb27  ldstr    aClass// "class"
0xdb2c  ldloc.s  5
0xdb2e  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0xdb33  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xdb38  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdb3d  ldloc.s  9
0xdb3f  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xdb44  ldstr    aAriaDescribedb// "aria-describedby"
0xdb49  ldstr    aDivErrorflyout// "div_errorFlyout_Container_"
0xdb4e  ldloc.3
0xdb4f  call     string [mscorlib]System.String::Concat(string, string)
0xdb54  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xdb59  ldloc.s  8
0xdb5b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xdb60  ldloc.s  9
0xdb62  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xdb67  leave.s  loc_DB75
0xdb69  ldloc.s  9
0xdb6b  brfalse.s loc_DB74
0xdb6d  ldloc.s  9
0xdb6f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdb74  endfinally
0xdb75  ldloc.0
0xdb76  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xdb7b  ldloc.s  8
0xdb7d  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xdb82  leave.s  loc_DB9C
0xdb84  ldloc.s  8
0xdb86  brfalse.s loc_DB8F
0xdb88  ldloc.s  8
0xdb8a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdb8f  endfinally
0xdb90  ldloc.s  7
0xdb92  brfalse.s loc_DB9B
0xdb94  ldloc.s  7
0xdb96  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdb9b  endfinally
0xdb9c  ldloc.0
0xdb9d  ret
```
