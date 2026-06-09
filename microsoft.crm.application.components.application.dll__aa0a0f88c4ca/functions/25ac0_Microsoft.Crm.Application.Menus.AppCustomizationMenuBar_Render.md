# Microsoft.Crm.Application.Menus.AppCustomizationMenuBar::Render

- ea: `0x25ac0`
- end: `0x25c5d`
- name: `Microsoft.Crm.Application.Menus.AppCustomizationMenuBar::Render`
- size: `413`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x24210`
- `0x242f0`
- `0x25990`
- `0x259b0`
- `0x259d0`
- `0x25ac0`
- `0x472c0`

## string_xrefs

- `0x25bbb`: `<span class="ms-crm-FormMenuBarBreadcrumb">`
- `0x25bd1`: `<span id="leftNavBreadcrumbText">`
- `0x25aeb`: `<td class="ms-crm-Form-LargeIcon-default" ><img id="BreadcrumbLargeIconImg" width="32px" height="32px" alt="" src="{0}" {1}/></td><td class="ms-crm-Form-Title" nowrap>`
- `0x25b4b`: `<td class="ms-crm-Form-LargeIcon-default" ><img id="BreadcrumbLargeIconImg" width="32px" height="32px" alt="" src="{0}" {1}/></td><td class="ms-crm-Form-Title" nowrap>`
- `0x25bc6`: `<img id="leftNavBreadcrumbImg" width="16px" height="16px" alt="" src="/_imgs/ico_18_entityinfo.gif" class="ms-crm-Form-Breadcrumb-Nav"/>`

## pseudocode

```c

```

## disassembly

```asm
0x25ac0  ldarg.0
0x25ac1  ldarg.1
0x25ac2  call     instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::Render(class [System.Web]System.Web.UI.HtmlTextWriter)
0x25ac7  ldarg.0
0x25ac8  call     instance string Microsoft.Crm.Application.Menus.AppCustomizationMenuBar::get_TitleName()
0x25acd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25ad2  brtrue   loc_25C5C
0x25ad7  ldarg.1
0x25ad8  ldstr    aTableClassMsCr// "<table class=\"ms-crm-Form-Title\" cell"...
0x25add  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25ae2  ldarg.0
0x25ae3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Menus.AppCustomizationMenuBar::get_CustomIconPath()
0x25ae8  brtrue.s loc_25B4A
0x25aea  ldarg.1
0x25aeb  ldstr    aTdClassMsCrmFo_2// "<td class=\"ms-crm-Form-LargeIcon-defau"...
0x25af0  ldarg.0
0x25af1  call     instance int32 Microsoft.Crm.Application.Menus.AppCustomizationMenuBar::get_EntityIconType()
0x25af6  ldc.i4.7
0x25af7  ldc.i4.1
0x25af8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x25afd  ldloca.s 0
0x25aff  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x25b05  ldloc.0
0x25b06  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, valuetype [mscorlib]System.Nullable`1<int32>)
0x25b0b  callvirt instance string [mscorlib]System.Object::ToString()
0x25b10  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x25b15  ldarg.0
0x25b16  call     instance int32 Microsoft.Crm.Application.Menus.AppCustomizationMenuBar::get_EntityIconType()
0x25b1b  ldc.i4.7
0x25b1c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::IsIconFlipped(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType)
0x25b21  brtrue.s loc_25B2A
0x25b23  ldsfld   string [mscorlib]System.String::Empty
0x25b28  br.s     loc_25B43
0x25b2a  ldstr    aStyle_1// "style=\""
0x25b2f  ldstr    aH// "h"
0x25b34  call     string Microsoft.Crm.Application.Utility.WebUtility::FlipImage(string direction)
0x25b39  ldstr    asc_116D5E// "\" "
0x25b3e  call     string [mscorlib]System.String::Concat(string, string, string)
0x25b43  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x25b48  br.s     loc_25B93
0x25b4a  ldarg.1
0x25b4b  ldstr    aTdClassMsCrmFo_2// "<td class=\"ms-crm-Form-LargeIcon-defau"...
0x25b50  ldarg.0
0x25b51  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Menus.AppCustomizationMenuBar::get_CustomIconPath()
0x25b56  callvirt instance string [mscorlib]System.Object::ToString()
0x25b5b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x25b60  ldarg.0
0x25b61  call     instance int32 Microsoft.Crm.Application.Menus.AppCustomizationMenuBar::get_EntityIconType()
0x25b66  ldc.i4.7
0x25b67  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::IsIconFlipped(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType)
0x25b6c  brtrue.s loc_25B75
0x25b6e  ldsfld   string [mscorlib]System.String::Empty
0x25b73  br.s     loc_25B8E
0x25b75  ldstr    aStyle_1// "style=\""
0x25b7a  ldstr    aH// "h"
0x25b7f  call     string Microsoft.Crm.Application.Utility.WebUtility::FlipImage(string direction)
0x25b84  ldstr    asc_116D5E// "\" "
0x25b89  call     string [mscorlib]System.String::Concat(string, string, string)
0x25b8e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object)
0x25b93  ldarg.1
0x25b94  ldstr    aSpanIdFormTitl// "<span id=\"form_title_span\" class=\"ms"...
0x25b99  ldstr    aHeaderidappcus// "headerIdAppCustomizationMenuBar"
0x25b9e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x25ba3  ldarg.0
0x25ba4  call     instance string Microsoft.Crm.Application.Menus.AppCustomizationMenuBar::get_TitleName()
0x25ba9  ldarg.1
0x25baa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x25baf  ldarg.1
0x25bb0  ldstr    aH1Span// "</H1></span>"
0x25bb5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25bba  ldarg.1
0x25bbb  ldstr    aSpanClassMsCrm// "<span class=\"ms-crm-FormMenuBarBreadcr"...
0x25bc0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25bc5  ldarg.1
0x25bc6  ldstr    aImgIdLeftnavbr// "<img id=\"leftNavBreadcrumbImg\" width="...
0x25bcb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25bd0  ldarg.1
0x25bd1  ldstr    aSpanIdLeftnavb// "<span id=\"leftNavBreadcrumbText\">"
0x25bd6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25bdb  ldarg.0
0x25bdc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x25be1  ldstr    aAreaLabelInfo// "Area_Label_Info"
0x25be6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x25beb  ldarg.1
0x25bec  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x25bf1  ldarg.1
0x25bf2  ldstr    aSpan// "</span>"
0x25bf7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25bfc  ldarg.1
0x25bfd  ldstr    aTd// "</td>"
0x25c02  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25c07  ldarg.0
0x25c08  call     instance bool Microsoft.Crm.Application.Menus.AppMenuBar::get_HideSolutionTitle()
0x25c0d  brtrue.s loc_25C51
0x25c0f  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x25c14  brfalse.s loc_25C51
0x25c16  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x25c1b  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x25c20  ldstr    aAppsolutionid// "appSolutionId"
0x25c25  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x25c2a  brfalse.s loc_25C51
0x25c2c  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x25c31  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x25c36  ldstr    aAppsolutionid// "appSolutionId"
0x25c3b  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x25c40  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext
0x25c45  ldarg.1
0x25c46  ldarg.0
0x25c47  call     instance int32 Microsoft.Crm.Application.Menus.AppCustomizationMenuBar::get_EntityIconType()
0x25c4c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext::RenderSolutionTitle(class [mscorlib]System.IO.TextWriter, int32)
0x25c51  ldarg.1
0x25c52  ldstr    aTrTable// "</tr></table>"
0x25c57  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25c5c  ret
```
