# Microsoft.Crm.Application.Controls.VisualizationCompositeControl::InsertGridLoadingScript

- ea: `0x62280`
- end: `0x62743`
- name: `Microsoft.Crm.Application.Controls.VisualizationCompositeControl::InsertGridLoadingScript`
- size: `1219`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x617e0`

## callees

- `0x47270`
- `0x55e40`
- `0x55eb0`
- `0x55ed0`
- `0x56060`
- `0x56360`
- `0x61110`
- `0x61130`
- `0x612e0`
- `0x62280`

## string_xrefs

- `0x62686`: `teamTemplateId`
- `0x62349`: `deleteAction`
- `0x62359`: `deleteAction`

## pseudocode

```c

```

## disassembly

```asm
0x62280  ldarg.0
0x62281  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x62286  ldc.i4.1
0x62287  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_SuppressClientAjaxComponents(bool)
0x6228c  ldarg.0
0x6228d  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62292  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x62297  ldarg.0
0x62298  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x6229d  ldc.i4.0
0x6229e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_SuppressClientAjaxComponents(bool)
0x622a3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x622a8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x622ad  stloc.0
0x622ae  ldstr    aGridRendergrid// "/_grid/RenderGridView.aspx"
0x622b3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string)
0x622b8  stloc.1
0x622b9  ldloc.1
0x622ba  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x622bf  ldstr    aId_1// "id"
0x622c4  ldarg.0
0x622c5  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x622ca  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x622cf  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x622d4  ldloc.1
0x622d5  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x622da  ldstr    aViewtype_1// "viewtype"
0x622df  ldarg.0
0x622e0  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x622e5  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType Microsoft.Crm.Application.Controls.AppGrid::get_ViewType()
0x622ea  stloc.3
0x622eb  ldloca.s 3
0x622ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x622f2  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x622f7  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x622fc  ldloc.1
0x622fd  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x62302  ldstr    aViewid_1// "viewid"
0x62307  ldarg.0
0x62308  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x6230d  callvirt instance string Microsoft.Crm.Application.Controls.AppGrid::get_ViewId()
0x62312  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x62317  ldloc.1
0x62318  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x6231d  ldstr    aIssubgridlite// "isSubGridLite"
0x62322  ldarg.0
0x62323  ldfld    bool Microsoft.Crm.Application.Controls.VisualizationCompositeControl::_isSubGridLite
0x62328  brtrue.s loc_62331
0x6232a  ldstr    a0// "0"
0x6232f  br.s     loc_62336
0x62331  ldstr    a1_0// "1"
0x62336  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x6233b  ldarg.0
0x6233c  ldfld    bool Microsoft.Crm.Application.Controls.VisualizationCompositeControl::_isSubGridLite
0x62341  brfalse.s loc_62368
0x62343  ldloc.1
0x62344  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x62349  ldstr    aDeleteaction// "deleteAction"
0x6234e  ldarg.0
0x6234f  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62354  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x62359  ldstr    aDeleteaction// "deleteAction"
0x6235e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x62363  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x62368  ldloc.1
0x62369  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x6236e  ldstr    aEnablecontextu// "enableContextualActions"
0x62373  ldarg.0
0x62374  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62379  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x6237e  ldstr    aEnablecontextu// "enableContextualActions"
0x62383  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x62388  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x6238d  ldloc.1
0x6238e  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x62393  ldstr    aEm// "em"
0x62398  ldarg.0
0x62399  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x6239e  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_IsHostedOnFlatUIPage()
0x623a3  brtrue.s loc_623B4
0x623a5  ldarg.0
0x623a6  ldfld    bool Microsoft.Crm.Application.Controls.VisualizationCompositeControl::_isSubGridLite
0x623ab  brtrue.s loc_623B4
0x623ad  ldstr    a0// "0"
0x623b2  br.s     loc_623B9
0x623b4  ldstr    a1_0// "1"
0x623b9  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x623be  ldloc.1
0x623bf  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x623c4  ldstr    aExpandable// "expandable"
0x623c9  ldarg.0
0x623ca  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x623cf  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Expandable()
0x623d4  brtrue.s loc_623DD
0x623d6  ldstr    a0// "0"
0x623db  br.s     loc_623E2
0x623dd  ldstr    a1_0// "1"
0x623e2  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x623e7  ldloc.1
0x623e8  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x623ed  ldstr    aAutoexpand// "autoExpand"
0x623f2  ldarg.0
0x623f3  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x623f8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x623fd  ldstr    aSubgridautoexp// "subgridAutoExpand"
0x62402  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x62407  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x6240c  ldloc.1
0x6240d  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x62412  ldstr    aJumpbar// "jumpbar"
0x62417  ldarg.0
0x62418  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x6241d  callvirt instance bool Microsoft.Crm.Application.Controls.AppGrid::get_ShowJumpBar()
0x62422  brtrue.s loc_6242B
0x62424  ldstr    a0// "0"
0x62429  br.s     loc_62430
0x6242b  ldstr    a1_0// "1"
0x62430  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x62435  ldloc.1
0x62436  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x6243b  ldstr    aRecsperpage// "recsPerPage"
0x62440  ldarg.0
0x62441  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62446  callvirt instance unsigned int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_RecordsPerPage()
0x6244b  stloc.s  4
0x6244d  ldloca.s 4
0x6244f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x62454  call     instance string [mscorlib]System.UInt32::ToString(class [mscorlib]System.IFormatProvider)
0x62459  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x6245e  ldloc.1
0x6245f  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x62464  ldstr    aMaxrows// "maxRows"
0x62469  ldarg.0
0x6246a  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x6246f  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_MaxRowsBeforeScroll()
0x62474  stloc.3
0x62475  ldloca.s 3
0x62477  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6247c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x62481  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x62486  ldloc.1
0x62487  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x6248c  ldstr    aTabindex_0// "tabIndex"
0x62491  ldarg.0
0x62492  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62497  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_TabIndex()
0x6249c  stloc.3
0x6249d  ldloca.s 3
0x6249f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x624a4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x624a9  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x624ae  ldloc.1
0x624af  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x624b4  ldstr    aRelationshipty// "relationshipType"
0x624b9  ldarg.0
0x624ba  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x624bf  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x624c4  ldstr    aRelationshipty// "relationshipType"
0x624c9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x624ce  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x624d3  ldloc.1
0x624d4  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x624d9  ldstr    aRibboncontext_0// "ribbonContext"
0x624de  ldarg.0
0x624df  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x624e4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x624e9  ldstr    aRibboncontext_0// "ribbonContext"
0x624ee  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x624f3  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x624f8  ldloc.1
0x624f9  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x624fe  ldstr    aGridtype_1// "gridType"
0x62503  ldarg.0
0x62504  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62509  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x6250e  ldstr    aGridtype// "GridType"
0x62513  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x62518  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x6251d  ldloc.1
0x6251e  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x62523  ldstr    aRelname// "relName"
0x62528  ldarg.0
0x62529  call     instance string Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_RelationshipName()
0x6252e  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x62533  ldloc.1
0x62534  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x62539  ldstr    aRoleord// "roleOrd"
0x6253e  ldarg.0
0x6253f  call     instance int32 Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_RelationshipRoleOrdinal()
0x62544  stloc.3
0x62545  ldloca.s 3
0x62547  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6254c  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x62551  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x62556  ldloc.1
0x62557  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x6255c  ldstr    aOtype_1// "oType"
0x62561  ldarg.0
0x62562  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62567  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x6256c  ldstr    aOtype_1// "oType"
0x62571  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x62576  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x6257b  ldloc.1
0x6257c  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x62581  ldstr    aEventmanagerid// "eventManagerId"
0x62586  ldarg.0
0x62587  ldfld    bool Microsoft.Crm.Application.Controls.VisualizationCompositeControl::_isSubGridLite
0x6258c  brfalse.s loc_62596
0x6258e  ldarg.0
0x6258f  call     instance bool Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_IsDashboardComponent()
0x62594  brfalse.s loc_6259E
0x62596  ldarg.0
0x62597  call     string Microsoft.Crm.Application.Utility.WebUtility::GetRootEventManagerId(class [System.Web]System.Web.UI.Control ctrl)
0x6259c  br.s     loc_625A3
0x6259e  ldstr    aPageCrmeventma// "__Page_crmEventManager"
0x625a3  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x625a8  ldloc.1
0x625a9  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x625ae  ldstr    aLoadondemand_0// "loadOnDemand"
0x625b3  ldarg.0
0x625b4  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x625b9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x625be  ldstr    aLoadondemand// "LoadOnDemand"
0x625c3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x625c8  ldstr    a1_0// "1"
0x625cd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x625d2  brtrue.s loc_625DB
0x625d4  ldstr    a0// "0"
0x625d9  br.s     loc_625E0
0x625db  ldstr    a1_0// "1"
0x625e0  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x625e5  ldloc.1
0x625e6  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x625eb  ldstr    aIsgridhidden// "isGridHidden"
0x625f0  ldarg.0
0x625f1  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x625f6  callvirt instance bool Microsoft.Crm.Application.Controls.AppGrid::get_IsGridHidden()
0x625fb  brtrue.s loc_62604
0x625fd  ldstr    aFalse// "false"
0x62602  br.s     loc_62609
0x62604  ldstr    aTrue// "true"
0x62609  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x6260e  ldloc.1
0x6260f  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x62614  ldstr    aViewts// "viewts"
0x62619  ldarg.0
0x6261a  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x6261f  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View Microsoft.Crm.Application.Controls.AppGrid::get_View()
0x62624  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::get_Timestamp()
0x62629  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x6262e  ldloc.1
0x6262f  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x62634  ldstr    aMdts// "mdts"
0x62639  ldloc.0
0x6263a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_TimeStamp()
0x6263f  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x62644  ldloc.1
0x62645  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x6264a  ldstr    aLcid// "lcid"
0x6264f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x62654  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserUICulture()
0x62659  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x6265e  stloc.3
0x6265f  ldloca.s 3
0x62661  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x62666  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x6266b  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x62670  ldloc.1
0x62671  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x62676  ldstr    aTeamtmplid// "teamTmplId"
0x6267b  ldarg.0
0x6267c  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x62681  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::get_Parameters()
0x62686  ldstr    aTeamtemplateid// "teamTemplateId"
0x6268b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x62690  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x62695  ldloc.1
0x62696  ldc.i4.1
0x62697  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_UseVersionStamp(bool)
0x6269c  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x626a1  stloc.2
0x626a2  ldloc.2
0x626a3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x626a8  ldstr    aMscrmGridcontr_0// "Mscrm.GridControl.loadGridView({0}, {1}"...
0x626ad  ldc.i4.5
0x626ae  newarr   [mscorlib]System.Object
0x626b3  dup
0x626b4  ldc.i4.0
0x626b5  ldarg.1
0x626b6  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x626bb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x626c0  stelem.ref
0x626c1  dup
0x626c2  ldc.i4.1
0x626c3  ldarg.0
0x626c4  ldfld    class Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0x626c9  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x626ce  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x626d3  stelem.ref
  ... truncated ...
```
