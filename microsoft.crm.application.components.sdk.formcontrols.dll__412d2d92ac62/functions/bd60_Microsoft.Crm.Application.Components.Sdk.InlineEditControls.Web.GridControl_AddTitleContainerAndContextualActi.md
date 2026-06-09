# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddTitleContainerAndContextualActionsToPage

- ea: `0xbd60`
- end: `0xbed4`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddTitleContainerAndContextualActionsToPage`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0xbcf0`

## callees

- `0xbd60`
- `0xbee0`
- `0xe480`
- `0x17a10`
- `0x1c790`
- `0x1c7f0`
- `0x1cc10`
- `0x1cde0`
- `0x1cf40`

## pseudocode

```c

```

## disassembly

```asm
0xbd60  ldnull
0xbd61  stloc.0
0xbd62  ldarg.0
0xbd63  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_ViewTitle()
0xbd68  stloc.1
0xbd69  ldarg.0
0xbd6a  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0xbd6f  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::get_ViewEntityTypeCode()
0xbd74  ldc.i4   0x11D7
0xbd79  bne.un.s loc_BD93
0xbd7b  ldarg.0
0xbd7c  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::IsAssociatedGrid()
0xbd81  brfalse.s loc_BD93
0xbd83  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xbd88  ldstr    aAuditIncontext// "Audit.Incontext.AreaTitle"
0xbd8d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbd92  stloc.1
0xbd93  ldloc.1
0xbd94  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbd99  brfalse.s loc_BDAD
0xbd9b  ldarg.0
0xbd9c  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_EnableContextualActions()
0xbda1  brtrue.s loc_BDAD
0xbda3  ldarg.0
0xbda4  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_EnableViewPicker()
0xbda9  brtrue.s loc_BDAD
0xbdab  ldnull
0xbdac  ret
0xbdad  ldstr    aDiv// "div"
0xbdb2  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xbdb7  stloc.2
0xbdb8  ldstr    aDiv// "div"
0xbdbd  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor(string)
0xbdc2  dup
0xbdc3  stloc.0
0xbdc4  stloc.3
0xbdc5  ldloc.0
0xbdc6  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xbdcb  ldstr    aClass// "class"
0xbdd0  ldstr    aMsCrmGridTitle// "ms-crm-Grid-TitleText"
0xbdd5  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xbdda  ldloc.0
0xbddb  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xbde0  ldstr    aTabindex// "tabindex"
0xbde5  ldarg.0
0xbde6  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0xbdeb  stloc.s  4
0xbded  ldloca.s 4
0xbdef  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbdf4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbdf9  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xbdfe  ldarg.0
0xbdff  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::IsAssociatedGrid()
0xbe04  brfalse.s loc_BE1B
0xbe06  ldloc.0
0xbe07  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xbe0c  ldstr    aStyle// "style"
0xbe11  ldstr    aWidth100// "width: 100%"
0xbe16  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xbe1b  ldarg.0
0xbe1c  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_InnerGrid()
0xbe21  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::get_ViewEntityTypeCode()
0xbe26  ldc.i4   0x11D7
0xbe2b  bne.un.s loc_BE4A
0xbe2d  ldarg.0
0xbe2e  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::IsAssociatedGrid()
0xbe33  brfalse.s loc_BE4A
0xbe35  ldloc.0
0xbe36  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xbe3b  ldstr    aStyle// "style"
0xbe40  ldstr    aFontFamilySego// "font-family:'Segoe UI', Arial, sans-ser"...
0xbe45  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xbe4a  ldloc.0
0xbe4b  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xbe50  ldstr    aId// "id"
0xbe55  ldarg.0
0xbe56  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xbe5b  ldstr    aTitletext// "_titleText"
0xbe60  call     string [mscorlib]System.String::Concat(string, string)
0xbe65  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xbe6a  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xbe6f  ldloc.0
0xbe70  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0xbe75  ldstr    aTitle// "title"
0xbe7a  ldloc.1
0xbe7b  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0xbe80  ldarg.0
0xbe81  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_EnableViewPicker()
0xbe86  brfalse.s loc_BEA0
0xbe88  ldloc.0
0xbe89  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xbe8e  ldarg.0
0xbe8f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGridQueryFilter Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_QueryFilter()
0xbe94  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppViewSelector [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGridQueryFilter::get_CurrentViewSelector()
0xbe99  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xbe9e  leave.s  loc_BEBB
0xbea0  ldloc.1
0xbea1  brfalse.s loc_BEAF
0xbea3  ldloc.0
0xbea4  ldloc.1
0xbea5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0xbeaa  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0xbeaf  leave.s  loc_BEBB
0xbeb1  ldloc.3
0xbeb2  brfalse.s loc_BEBA
0xbeb4  ldloc.3
0xbeb5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbeba  endfinally
0xbebb  ldarg.0
0xbebc  ldloc.1
0xbebd  ldloc.0
0xbebe  ldloc.2
0xbebf  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddTitleAndActions(string gridTitle, class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl titleDiv, class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl titleContainer)
0xbec4  ldloc.2
0xbec5  stloc.3
0xbec6  leave.s  loc_BED2
0xbec8  ldloc.2
0xbec9  brfalse.s loc_BED1
0xbecb  ldloc.2
0xbecc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbed1  endfinally
0xbed2  ldloc.3
0xbed3  ret
```
