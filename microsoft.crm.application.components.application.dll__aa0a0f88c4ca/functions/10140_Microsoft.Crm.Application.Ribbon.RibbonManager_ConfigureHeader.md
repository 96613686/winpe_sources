# Microsoft.Crm.Application.Ribbon.RibbonManager::ConfigureHeader

- ea: `0x10140`
- end: `0x1040a`
- name: `Microsoft.Crm.Application.Ribbon.RibbonManager::ConfigureHeader`
- size: `714`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x10010`
- `0x10030`
- `0x10140`

## string_xrefs

- `0x101d1`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0x10253`: `LOCID_MORECOMMANDS_TOOLTIP`
- `0x1025d`: `RefreshCommandBar.MoreCommands.ToolTip`
- `0x10273`: `LOCID_MORECOMMANDS_RESIZEDLABEL`
- `0x1027d`: `RefreshCommandBar.MoreCommands.ResizedLabel`
- `0x1029d`: `RefreshCommandBar.DummyControl.Label`
- `0x102e0`: `isOnAssociatedGridCommandBar`

## pseudocode

```c

```

## disassembly

```asm
0x10140  ldc.i4.0
0x10141  stloc.0
0x10142  ldarg.0
0x10143  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x10148  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1014d  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x10152  ldstr    aUserdefinedAre// "userdefined/areas.aspx"
0x10157  ldc.i4.5
0x10158  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x1015d  brtrue.s loc_1017C
0x1015f  ldarg.0
0x10160  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x10165  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1016a  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x1016f  ldstr    aDocumentmanage// "documentmanagement/areas.aspx"
0x10174  ldc.i4.5
0x10175  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x1017a  brfalse.s loc_101AD
0x1017c  ldarg.0
0x1017d  call     instance bool Microsoft.Crm.Application.Ribbon.RibbonManager::get_IsRibbonManagerEnabledForRefresh()
0x10182  brfalse.s loc_101AA
0x10184  ldarg.0
0x10185  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1018a  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1018f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x10194  ldstr    aRof// "rof"
0x10199  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1019e  ldstr    aTrue// "true"
0x101a3  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x101a8  brfalse.s loc_101AB
0x101aa  ret
0x101ab  ldc.i4.1
0x101ac  stloc.0
0x101ad  ldarg.0
0x101ae  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0x101b3  ldarg.0
0x101b4  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x101b9  ldc.i4.1
0x101ba  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0x101bf  ldarg.0
0x101c0  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x101c5  ldc.i4.1
0x101c6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQueryTemplate(bool)
0x101cb  ldarg.0
0x101cc  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x101d1  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/jquery_ui_1.8."...
0x101d6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x101db  ldarg.0
0x101dc  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x101e1  ldstr    aStaticFormsDat// "/_static/_forms/DateTime.js"
0x101e6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x101eb  ldarg.0
0x101ec  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x101f1  ldstr    aStaticControls_1// "/_static/_controls/FlyoutDialog/FlyoutD"...
0x101f6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x101fb  ldarg.0
0x101fc  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x10201  ldstr    aStaticControls_0// "/_static/_controls/ribbon/ribbon.js"
0x10206  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1020b  ldarg.0
0x1020c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x10211  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10216  ldstr    aStaticCss0CuiC// "/_static/css/{0}/cui.css"
0x1021b  ldc.i4.1
0x1021c  newarr   [mscorlib]System.Object
0x10221  dup
0x10222  ldc.i4.0
0x10223  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x10228  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x1022d  box      [mscorlib]System.Int32
0x10232  stelem.ref
0x10233  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10238  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x1023d  ldarg.0
0x1023e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x10243  ldstr    aControlsRefres// "/_controls/refreshform/flyoutdialog.css"...
0x10248  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x1024d  ldarg.0
0x1024e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x10253  ldstr    aLocidMorecomma// "LOCID_MORECOMMANDS_TOOLTIP"
0x10258  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1025d  ldstr    aRefreshcommand// "RefreshCommandBar.MoreCommands.ToolTip"
0x10262  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10267  ldc.i4.0
0x10268  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1026d  ldarg.0
0x1026e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x10273  ldstr    aLocidMorecomma_0// "LOCID_MORECOMMANDS_RESIZEDLABEL"
0x10278  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1027d  ldstr    aRefreshcommand_0// "RefreshCommandBar.MoreCommands.ResizedL"...
0x10282  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10287  ldc.i4.0
0x10288  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1028d  ldarg.0
0x1028e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x10293  ldstr    aLocidDummycont// "LOCID_DUMMYCONTROL_LABEL"
0x10298  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1029d  ldstr    aRefreshcommand_1// "RefreshCommandBar.DummyControl.Label"
0x102a2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x102a7  ldc.i4.0
0x102a8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x102ad  ldarg.0
0x102ae  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x102b3  ldstr    aPrerenderall// "PreRenderAll"
0x102b8  ldarg.0
0x102b9  call     instance bool Microsoft.Crm.Application.Ribbon.RibbonManager::get_PreRenderAll()
0x102be  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x102c3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x102c8  stloc.1
0x102c9  ldloc.1
0x102ca  ldstr    aIsonoutlooksta// "isOnOutlookStage"
0x102cf  ldarg.0
0x102d0  ldfld    bool Microsoft.Crm.Application.Ribbon.RibbonManager::_isOnOutlookStage
0x102d5  box      [mscorlib]System.Boolean
0x102da  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x102df  ldloc.1
0x102e0  ldstr    aIsonassociated// "isOnAssociatedGridCommandBar"
0x102e5  ldloc.0
0x102e6  box      [mscorlib]System.Boolean
0x102eb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x102f0  ldstr    aTrue// "true"
0x102f5  stloc.2
0x102f6  ldstr    aCmdbar// "cmdbar"
0x102fb  stloc.3
0x102fc  ldarg.0
0x102fd  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x10302  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10307  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1030c  ldloc.3
0x1030d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10312  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10317  brtrue.s loc_10335
0x10319  ldarg.0
0x1031a  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1031f  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10324  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x10329  ldloc.3
0x1032a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1032f  stloc.2
0x10330  br       loc_103E9
0x10335  ldarg.0
0x10336  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1033b  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10340  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x10345  ldstr    aExtraqs// "extraqs"
0x1034a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1034f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10354  brtrue   loc_103E9
0x10359  ldarg.0
0x1035a  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1035f  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10364  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x10369  ldstr    aExtraqs// "extraqs"
0x1036e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10373  ldstr    asc_113718// "?"
0x10378  ldc.i4.5
0x10379  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x1037e  brtrue.s loc_103A6
0x10380  ldstr    asc_113718// "?"
0x10385  ldarg.0
0x10386  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x1038b  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10390  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x10395  ldstr    aExtraqs// "extraqs"
0x1039a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1039f  call     string [mscorlib]System.String::Concat(string, string)
0x103a4  br.s     loc_103C0
0x103a6  ldarg.0
0x103a7  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0x103ac  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x103b1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x103b6  ldstr    aExtraqs// "extraqs"
0x103bb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x103c0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x103c5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x103ca  stloc.s  4
0x103cc  ldloc.s  4
0x103ce  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x103d3  ldloc.3
0x103d4  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, string>::ContainsKey(var<u1>)
0x103d9  brfalse.s loc_103E9
0x103db  ldloc.s  4
0x103dd  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x103e2  ldloc.3
0x103e3  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Item(void)
0x103e8  stloc.2
0x103e9  ldloc.1
0x103ea  ldstr    aCmdbarstatus// "cmdBarStatus"
0x103ef  ldloc.2
0x103f0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x103f5  ldarg.0
0x103f6  ldstr    aMscrmRibbonman// "Mscrm.RibbonManager"
0x103fb  ldloc.1
0x103fc  ldnull
0x103fd  ldnull
0x103fe  ldarg.0
0x103ff  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x10404  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0x10409  ret
```
