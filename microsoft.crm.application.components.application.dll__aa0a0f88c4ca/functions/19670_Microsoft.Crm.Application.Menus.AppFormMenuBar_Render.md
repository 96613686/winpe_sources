# Microsoft.Crm.Application.Menus.AppFormMenuBar::Render

- ea: `0x19670`
- end: `0x19a05`
- name: `Microsoft.Crm.Application.Menus.AppFormMenuBar::Render`
- size: `917`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x17c80`
- `0x17cc0`
- `0x19650`
- `0x19670`
- `0x24210`
- `0x242a0`
- `0x242f0`
- `0x24360`
- `0x26540`
- `0x26560`
- `0x472c0`
- `0x8d1a0`
- `0x8d790`

## string_xrefs

- `0x1976c`: `<span class="ms-crm-FormMenuBarBreadcrumb">`
- `0x19798`: `leftNavBreadcrumbImg`
- `0x197a3`: `ms-crm-Form-Breadcrumb-Nav`
- `0x197f6`: `<span id="leftNavBreadcrumbText">`
- `0x198c4`: `<div id = "crmForm_CurrentViewTitle" class="ms-crm-Form-Breadcrumb">`

## pseudocode

```c

```

## disassembly

```asm
0x19670  ldarg.0
0x19671  ldarg.1
0x19672  call     instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::Render(class [System.Web]System.Web.UI.HtmlTextWriter)
0x19677  ldarg.0
0x19678  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::get_ShowFormHeader()
0x1967d  brfalse  loc_19A04
0x19682  ldarg.0
0x19683  call     instance bool Microsoft.Crm.Application.Menus.AppFormMenuBar::get_HasNavigation()
0x19688  brfalse  loc_19826
0x1968d  ldarg.1
0x1968e  ldstr    aTableClassMsCr// "<table class=\"ms-crm-Form-Title\" cell"...
0x19693  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19698  ldarg.0
0x19699  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Menus.AppFormMenuBar::get_CustomIconPath()
0x1969e  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x196a3  brfalse.s loc_1970F
0x196a5  ldarg.1
0x196a6  ldstr    aTdClassMsCrmFo// "<td class=\"ms-crm-Form-LargeIcon-defau"...
0x196ab  ldarg.0
0x196ac  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x196b1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x196b6  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x196bb  ldc.i4.7
0x196bc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x196c1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x196c6  callvirt instance string [mscorlib]System.Object::ToString()
0x196cb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x196d0  ldarg.0
0x196d1  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x196d6  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x196db  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x196e0  ldc.i4.7
0x196e1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::IsIconFlipped(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType)
0x196e6  brtrue.s loc_196EF
0x196e8  ldsfld   string [mscorlib]System.String::Empty
0x196ed  br.s     loc_19708
0x196ef  ldstr    aStyle_1// "style=\""
0x196f4  ldstr    aH// "h"
0x196f9  call     string Microsoft.Crm.Application.Utility.WebUtility::FlipImage(string direction)
0x196fe  ldstr    asc_116D5E// "\" "
0x19703  call     string [mscorlib]System.String::Concat(string, string, string)
0x19708  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x1970d  br.s     loc_1972A
0x1970f  ldarg.1
0x19710  ldstr    aTdClassMsCrmFo_0// "<td class=\"ms-crm-Form-LargeIcon-defau"...
0x19715  ldarg.0
0x19716  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Menus.AppFormMenuBar::get_CustomIconPath()
0x1971b  callvirt instance string [mscorlib]System.Object::ToString()
0x19720  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x19725  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x1972a  ldarg.0
0x1972b  callvirt instance string Microsoft.Crm.Application.Menus.AppMenuBar::get_Title()
0x19730  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19735  brtrue.s loc_19760
0x19737  ldarg.1
0x19738  ldstr    aSpanIdFormTitl// "<span id=\"form_title_span\" class=\"ms"...
0x1973d  ldstr    aHeaderidappfor// "headerIdAppFormMenuBar"
0x19742  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x19747  ldarg.0
0x19748  callvirt instance string Microsoft.Crm.Application.Menus.AppMenuBar::get_Title()
0x1974d  ldarg.1
0x1974e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x19753  ldarg.1
0x19754  ldstr    aH1Span// "</H1></span>"
0x19759  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1975e  br.s     loc_1976B
0x19760  ldarg.1
0x19761  ldstr    aNbsp// "&nbsp;"
0x19766  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1976b  ldarg.1
0x1976c  ldstr    aSpanClassMsCrm// "<span class=\"ms-crm-FormMenuBarBreadcr"...
0x19771  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19776  ldarg.0
0x19777  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x1977c  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x19781  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x19786  ldc.i4.2
0x19787  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1978c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19791  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImage::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x19796  stloc.0
0x19797  ldloc.0
0x19798  ldstr    aLeftnavbreadcr// "leftNavBreadcrumbImg"
0x1979d  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x197a2  ldloc.0
0x197a3  ldstr    aMsCrmFormBread// "ms-crm-Form-Breadcrumb-Nav"
0x197a8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImage::set_CssClass(string)
0x197ad  ldloc.0
0x197ae  ldstr    aWidth// "width"
0x197b3  ldstr    a16px// "16px"
0x197b8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x197bd  ldloc.0
0x197be  ldstr    aHeight// "height"
0x197c3  ldstr    a16px// "16px"
0x197c8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x197cd  ldloc.0
0x197ce  ldstr    aAlt// "alt"
0x197d3  ldstr    asc_F537C// ""
0x197d8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x197dd  ldarg.1
0x197de  ldloc.0
0x197df  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.ImageStripImage::get_OuterHtml()
0x197e4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x197e9  leave.s  loc_197F5
0x197eb  ldloc.0
0x197ec  brfalse.s loc_197F4
0x197ee  ldloc.0
0x197ef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x197f4  endfinally
0x197f5  ldarg.1
0x197f6  ldstr    aSpanIdLeftnavb// "<span id=\"leftNavBreadcrumbText\">"
0x197fb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19800  ldarg.0
0x19801  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x19806  ldstr    aAreaLabelInfo// "Area_Label_Info"
0x1980b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19810  ldarg.1
0x19811  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x19816  ldarg.1
0x19817  ldstr    aSpan// "</span>"
0x1981c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19821  br       loc_1997F
0x19826  ldarg.1
0x19827  ldstr    aTableClassMsCr_0// "<table class=\"ms-crm-Form-Title-NoNav"...
0x1982c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19831  ldarg.0
0x19832  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Menus.AppFormMenuBar::get_CustomIconPath()
0x19837  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x1983c  brfalse.s loc_198A8
0x1983e  ldarg.1
0x1983f  ldstr    aTdClassMsCrmFo// "<td class=\"ms-crm-Form-LargeIcon-defau"...
0x19844  ldarg.0
0x19845  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x1984a  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x1984f  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x19854  ldc.i4.7
0x19855  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1985a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1985f  callvirt instance string [mscorlib]System.Object::ToString()
0x19864  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x19869  ldarg.0
0x1986a  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x1986f  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x19874  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x19879  ldc.i4.7
0x1987a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::IsIconFlipped(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType)
0x1987f  brtrue.s loc_19888
0x19881  ldsfld   string [mscorlib]System.String::Empty
0x19886  br.s     loc_198A1
0x19888  ldstr    aStyle_1// "style=\""
0x1988d  ldstr    aH// "h"
0x19892  call     string Microsoft.Crm.Application.Utility.WebUtility::FlipImage(string direction)
0x19897  ldstr    asc_F6B30// "\""
0x1989c  call     string [mscorlib]System.String::Concat(string, string, string)
0x198a1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x198a6  br.s     loc_198C3
0x198a8  ldarg.1
0x198a9  ldstr    aTdClassMsCrmFo_0// "<td class=\"ms-crm-Form-LargeIcon-defau"...
0x198ae  ldarg.0
0x198af  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Menus.AppFormMenuBar::get_CustomIconPath()
0x198b4  callvirt instance string [mscorlib]System.Object::ToString()
0x198b9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x198be  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x198c3  ldarg.1
0x198c4  ldstr    aDivIdCrmformCu// "<div id = \"crmForm_CurrentViewTitle\" "...
0x198c9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x198ce  ldarg.1
0x198cf  ldstr    aH1ClassMsCrmFo// "<h1 class=\"ms-crm-Form ms-crm-TextAuto"...
0x198d4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x198d9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x198de  ldstr    aSpanClassMsCrm_0// " <span class=\"ms-crm-Form-Entity-Name"...
0x198e3  ldc.i4.1
0x198e4  newarr   [mscorlib]System.Object
0x198e9  dup
0x198ea  ldc.i4.0
0x198eb  ldarg.0
0x198ec  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x198f1  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x198f6  callvirt instance string Microsoft.Crm.Application.Forms.AppForm::get_EntityDisplayName()
0x198fb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x19900  stelem.ref
0x19901  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19906  stloc.1
0x19907  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1990c  ldstr    aSpanClassMsCrm_1// " <span class=\"ms-crm-Form-Entity-Title"...
0x19911  ldc.i4.1
0x19912  newarr   [mscorlib]System.Object
0x19917  dup
0x19918  ldc.i4.0
0x19919  ldarg.0
0x1991a  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x1991f  callvirt instance class Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x19924  callvirt instance string Microsoft.Crm.Application.Forms.AppForm::get_EntityTitle()
0x19929  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x1992e  stelem.ref
0x1992f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19934  stloc.2
0x19935  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1993a  ldstr    aFormTitleMask// "Form_Title_Mask"
0x1993f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19944  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncodeForFormatString(string)
0x19949  stloc.3
0x1994a  ldarg.1
0x1994b  ldstr    aSpanClassMsCrm_2// "<span class= \"ms-crm-Form-NoNav-Title"...
0x19950  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19955  ldarg.1
0x19956  ldloc.3
0x19957  ldloc.1
0x19958  ldloc.2
0x19959  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x1995e  ldarg.1
0x1995f  ldstr    aSpan// "</span>"
0x19964  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19969  ldarg.1
0x1996a  ldstr    aH1// "</h1>"
0x1996f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19974  ldarg.1
0x19975  ldstr    aDiv_1// "</div>"
0x1997a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1997f  ldarg.1
0x19980  ldstr    aTd// "</td>"
0x19985  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1998a  ldarg.0
0x1998b  call     instance bool Microsoft.Crm.Application.Menus.AppMenuBar::get_HideSolutionTitle()
0x19990  brtrue.s loc_199F9
0x19992  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x19997  brfalse.s loc_199F9
0x19999  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1999e  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x199a3  ldstr    aAppsolutionid// "appSolutionId"
0x199a8  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x199ad  brfalse.s loc_199F9
0x199af  ldarg.0
0x199b0  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x199b5  brfalse.s loc_199F9
0x199b7  ldarg.0
0x199b8  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x199bd  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x199c2  ldnull
0x199c3  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::op_Inequality(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x199c8  brfalse.s loc_199F9
0x199ca  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x199cf  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x199d4  ldstr    aAppsolutionid// "appSolutionId"
0x199d9  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x199de  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext
0x199e3  ldarg.1
0x199e4  ldarg.0
0x199e5  call     instance class Microsoft.Crm.Application.Controls.AppPage Microsoft.Crm.Application.Menus.AppMenuBar::get_ApplicationPage()
0x199ea  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0x199ef  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x199f4  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::RenderSolutionTitle(class [mscorlib]System.IO.TextWriter, int32)
0x199f9  ldarg.1
0x199fa  ldstr    aTrTable// "</tr></table>"
0x199ff  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19a04  ret
```
