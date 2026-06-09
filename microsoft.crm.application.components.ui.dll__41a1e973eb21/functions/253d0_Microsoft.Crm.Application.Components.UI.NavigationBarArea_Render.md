# Microsoft.Crm.Application.Components.UI.NavigationBarArea::Render

- ea: `0x253d0`
- end: `0x25610`
- name: `Microsoft.Crm.Application.Components.UI.NavigationBarArea::Render`
- size: `576`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1a0a0`
- `0x1a0d0`
- `0x1a350`
- `0x1a390`
- `0x251e0`
- `0x25230`
- `0x25240`
- `0x25260`
- `0x253d0`
- `0x25610`
- `0x25630`

## pseudocode

```c

```

## disassembly

```asm
0x253d0  ldarg.0
0x253d1  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x253d6  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Clear()
0x253db  ldarg.0
0x253dc  callvirt instance bool Microsoft.Crm.Application.Components.UI.NavigationBarArea::AddChildNavigationBarItems()
0x253e1  stloc.0
0x253e2  ldarg.0
0x253e3  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x253e8  callvirt instance int32 [System.Web]System.Web.UI.ControlCollection::get_Count()
0x253ed  ldc.i4.0
0x253ee  cgt
0x253f0  ldloc.0
0x253f1  and
0x253f2  brfalse  loc_2560F
0x253f7  ldarg.1
0x253f8  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x253fd  stloc.1
0x253fe  ldloc.1
0x253ff  ldstr    aLi_2// "<li "
0x25404  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25409  ldarg.1
0x2540a  ldstr    aClass_1// "class"
0x2540f  ldarg.0
0x25410  call     instance bool Microsoft.Crm.Application.Components.UI.NavigationBarArea::get_ShowHeader()
0x25415  brtrue.s loc_2541E
0x25417  ldstr    aMsCrmNavGroupH// "ms-crm-Nav-Group-Hidden"
0x2541c  br.s     loc_25423
0x2541e  ldstr    aMsCrmNavGroup// "ms-crm-Nav-Group"
0x25423  ldc.i4.0
0x25424  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x25429  ldloc.1
0x2542a  ldstr    aAOnclickReturn_1// "><a onclick=\"return false;\" href=\"ja"...
0x2542f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25434  ldarg.0
0x25435  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2543a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2543f  brtrue.s loc_25452
0x25441  ldstr    aId// "id"
0x25446  ldarg.0
0x25447  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x2544c  ldarg.1
0x2544d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x25452  ldarg.1
0x25453  ldstr    aClass_1// "class"
0x25458  ldarg.0
0x25459  call     instance bool Microsoft.Crm.Application.Components.UI.NavigationBarArea::get_ShowHeader()
0x2545e  brtrue.s loc_25476
0x25460  ldarg.0
0x25461  call     instance bool Microsoft.Crm.Application.Components.UI.NavigationBarArea::get_IsFirst()
0x25466  brtrue.s loc_2546F
0x25468  ldstr    aMsCrmNavGroupH_0// "ms-crm-Nav-Group-Heading-Hidden"
0x2546d  br.s     loc_2547B
0x2546f  ldstr    aMsCrmNavGroupH_1// "ms-crm-Nav-Group-Heading-HiddenFirst"
0x25474  br.s     loc_2547B
0x25476  ldstr    aMsCrmNavGroupH_2// "ms-crm-Nav-Group-Heading"
0x2547b  ldc.i4.0
0x2547c  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x25481  ldarg.0
0x25482  call     instance bool Microsoft.Crm.Application.Components.UI.NavigationBarArea::get_ShowHeader()
0x25487  brfalse  loc_25595
0x2548c  ldarg.0
0x2548d  ldarg.1
0x2548e  callvirt instance void Microsoft.Crm.Application.Components.UI.NavigationBarArea::ModifyAreaHeaderAnchorAttributes(class [System.Web]System.Web.UI.HtmlTextWriter output)
0x25493  ldarg.0
0x25494  ldfld    string Microsoft.Crm.Application.Components.UI.NavigationBarArea::_toolTip
0x25499  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2549e  brtrue.s loc_254B1
0x254a0  ldstr    aTitle_2// "title"
0x254a5  ldarg.0
0x254a6  ldfld    string Microsoft.Crm.Application.Components.UI.NavigationBarArea::_toolTip
0x254ab  ldarg.1
0x254ac  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x254b1  ldloc.1
0x254b2  ldstr    asc_2B7B6// ">"
0x254b7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x254bc  call     class Microsoft.Crm.Application.Components.UI.ImageStrip Microsoft.Crm.Application.Components.UI.ImageStrip::get_Default()
0x254c1  ldarg.0
0x254c2  call     instance bool Microsoft.Crm.Application.Components.UI.NavigationBarArea::get_Expanded()
0x254c7  brtrue.s loc_254D0
0x254c9  ldstr    aImgsNavdownPng// "/_imgs/navdown.png"
0x254ce  br.s     loc_254D5
0x254d0  ldstr    aImgsNavupPng// "/_imgs/navup.png"
0x254d5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x254da  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x254df  callvirt instance class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo Microsoft.Crm.Application.Components.UI.ImageStrip::GetImageStripImageInfo(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri imagePath)
0x254e4  stloc.2
0x254e5  ldloc.1
0x254e6  ldstr    aImgClassMsCrmN// "<img class=\"ms-crm-Nav-Group-RightIcon"...
0x254eb  ldloc.2
0x254ec  callvirt instance string Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_CssClass()
0x254f1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x254f6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object)
0x254fb  ldstr    aAlt// "alt"
0x25500  ldarg.0
0x25501  call     instance bool Microsoft.Crm.Application.Components.UI.NavigationBarArea::get_Expanded()
0x25506  brtrue.s loc_25519
0x25508  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2550d  ldstr    aTreeAltExpand// "Tree.Alt.Expand"
0x25512  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x25517  br.s     loc_25528
0x25519  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2551e  ldstr    aTreeAltCollaps// "Tree.Alt.Collapse"
0x25523  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x25528  ldarg.1
0x25529  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2552e  ldarg.1
0x2552f  ldstr    aSrc_0// "src"
0x25534  ldloc.2
0x25535  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::get_ImageStripUrl()
0x2553a  callvirt instance string [mscorlib]System.Object::ToString()
0x2553f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x25544  ldc.i4.0
0x25545  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x2554a  ldloc.1
0x2554b  ldstr    asc_52770// "/>"
0x25550  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25555  ldloc.1
0x25556  ldstr    aNobrClassMsCrm_0// "<nobr class=\"ms-crm-Nav-Group-Title\" "
0x2555b  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25560  ldstr    aId// "id"
0x25565  ldarg.0
0x25566  call     instance string Microsoft.Crm.Application.Components.UI.NavigationBarArea::get_RenderId()
0x2556b  ldarg.1
0x2556c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x25571  ldloc.1
0x25572  ldstr    asc_2B7B6// ">"
0x25577  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2557c  ldarg.0
0x2557d  ldfld    string Microsoft.Crm.Application.Components.UI.NavigationBarArea::_title
0x25582  ldloc.1
0x25583  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x25588  ldloc.1
0x25589  ldstr    aNobr_0// "</nobr>"
0x2558e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x25593  br.s     loc_255B1
0x25595  ldarg.1
0x25596  ldstr    aTabindex// "tabindex"
0x2559b  ldstr    a1_0// "-1"
0x255a0  ldc.i4.0
0x255a1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x255a6  ldloc.1
0x255a7  ldstr    asc_52770// "/>"
0x255ac  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x255b1  ldloc.1
0x255b2  ldstr    aA// "</a>"
0x255b7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x255bc  ldloc.1
0x255bd  ldstr    aUlClassMsCrmNa_0// "<ul class=\"ms-crm-Nav-Group-Subareas\""
0x255c2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x255c7  ldarg.0
0x255c8  ldfld    bool Microsoft.Crm.Application.Components.UI.NavigationBarArea::_isExpanded
0x255cd  brtrue.s loc_255EA
0x255cf  ldarg.0
0x255d0  ldfld    bool Microsoft.Crm.Application.Components.UI.NavigationBarArea::_isSelected
0x255d5  brtrue.s loc_255EA
0x255d7  ldarg.0
0x255d8  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.Control::get_Parent()
0x255dd  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x255e2  callvirt instance int32 [System.Web]System.Web.UI.ControlCollection::get_Count()
0x255e7  ldc.i4.1
0x255e8  bne.un.s loc_255F5
0x255ea  ldloc.1
0x255eb  ldstr    aStyleDisplayIn// "style=\"display:inline;\""
0x255f0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x255f5  ldloc.1
0x255f6  ldc.i4.s 0x3E
0x255f8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x255fd  ldarg.0
0x255fe  ldarg.1
0x255ff  callvirt instance void [System.Web]System.Web.UI.Control::RenderChildren(class [System.Web]System.Web.UI.HtmlTextWriter)
0x25604  ldloc.1
0x25605  ldstr    aUlLi// "</ul></li>"
0x2560a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2560f  ret
```
