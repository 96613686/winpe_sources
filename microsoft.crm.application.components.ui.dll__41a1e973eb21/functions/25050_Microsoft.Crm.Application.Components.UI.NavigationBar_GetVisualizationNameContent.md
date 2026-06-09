# Microsoft.Crm.Application.Components.UI.NavigationBar::GetVisualizationNameContent

- ea: `0x25050`
- end: `0x2512d`
- name: `Microsoft.Crm.Application.Components.UI.NavigationBar::GetVisualizationNameContent`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x24c60`

## callees

- `0x25050`

## string_xrefs

- `0x250aa`: ` ms-crm-stripNavBarCommon ms-crm-stripNavBarLeftRight ms-crm-stripNavBarLabelLeftRight`
- `0x250b1`: `ms-crm-stripNavBarCommon ms-crm-stripNavBarEA ms-crm-stripNavBarLabelLeftRight`

## pseudocode

```c

```

## disassembly

```asm
0x25050  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::.ctor()
0x25055  stloc.0
0x25056  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::.ctor()
0x2505b  stloc.1
0x2505c  ldloc.1
0x2505d  ldstr    aLabel// "label"
0x25062  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl::set_TagName(string)
0x25067  ldloc.1
0x25068  ldarg.0
0x25069  ldstr    aVisualizationp_1// "_VisualizationPaneStripLabelMessage"
0x2506e  call     string [mscorlib]System.String::Concat(string, string)
0x25073  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x25078  ldloc.0
0x25079  ldstr    aCenter// "center"
0x2507e  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_Align(string)
0x25083  ldloc.0
0x25084  ldstr    aMiddle// "middle"
0x25089  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_VAlign(string)
0x2508e  ldloc.0
0x2508f  ldstr    a100_0// "100%"
0x25094  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableCell::set_Height(string)
0x25099  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x2509e  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x250a3  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::EALanguage(int32)
0x250a8  brtrue.s loc_250B1
0x250aa  ldstr    aMsCrmStripnavb// " ms-crm-stripNavBarCommon ms-crm-stripN"...
0x250af  br.s     loc_250B6
0x250b1  ldstr    aMsCrmStripnavb_0// "ms-crm-stripNavBarCommon ms-crm-stripNa"...
0x250b6  stloc.2
0x250b7  ldloc.1
0x250b8  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x250bd  ldstr    aClass_1// "class"
0x250c2  ldloc.2
0x250c3  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x250c8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x250cd  ldstr    aNavbarCollapse_0// "NavBar_Collapsed_Caption"
0x250d2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x250d7  stloc.3
0x250d8  ldloc.1
0x250d9  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x250de  ldstr    aTitle_2// "title"
0x250e3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x250e8  ldstr    aNavbarCollapse// "NavBar_Collapsed_ToolTip"
0x250ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x250f2  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x250f7  ldloc.1
0x250f8  ldloc.3
0x250f9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x250fe  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x25103  ldloc.0
0x25104  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x25109  ldloc.1
0x2510a  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x2510f  leave.s  loc_2511B
0x25111  ldloc.1
0x25112  brfalse.s loc_2511A
0x25114  ldloc.1
0x25115  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2511a  endfinally
0x2511b  ldloc.0
0x2511c  stloc.s  4
0x2511e  leave.s  loc_2512A
0x25120  ldloc.0
0x25121  brfalse.s loc_25129
0x25123  ldloc.0
0x25124  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25129  endfinally
0x2512a  ldloc.s  4
0x2512c  ret
```
