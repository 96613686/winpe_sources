# Microsoft.Crm.Service.Application.Pages.SM.GanttControlFrame::ConfigurePage

- ea: `0x11860`
- end: `0x1203c`
- name: `Microsoft.Crm.Service.Application.Pages.SM.GanttControlFrame::ConfigurePage`
- size: `2012`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x11740`
- `0x11760`
- `0x11780`
- `0x117d0`
- `0x11860`

## string_xrefs

- `0x118c1`: `AppointmentBookConfig`
- `0x11906`: `WRPCTOKEN-DEPENDENT`

## pseudocode

```c

```

## disassembly

```asm
0x11860  ldarg.0
0x11861  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x11866  ldstr    aStaticSmApptbo// "/_static/sm/apptbook/gantt.js"
0x1186b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x11870  ldarg.0
0x11871  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x11876  ldstr    aSmGanttStyleGa// "/sm/gantt/style/ganttcontrol.css.aspx"
0x1187b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x11880  ldarg.0
0x11881  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x11886  ldstr    aSmApptbookAppt// "/sm/apptbook/apptbook.css.aspx"
0x1188b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x11890  ldarg.0
0x11891  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x11896  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x1189b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x118a0  ldarg.0
0x118a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x118a6  ldstr    aControlsZoomZo// "/_controls/zoom/zoom.css.aspx"
0x118ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x118b0  ldarg.0
0x118b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x118b6  ldstr    aNavMenuCssAspx// "/_nav/menu.css.aspx"
0x118bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x118c0  ldarg.0
0x118c1  ldstr    aAppointmentboo// "AppointmentBookConfig"
0x118c6  call     instance string Microsoft.Crm.Service.Application.Pages.SM.GanttControlFrame::GetWebResourceName(string wrDisplayName)
0x118cb  stloc.0
0x118cc  ldloc.0
0x118cd  brfalse.s loc_118EA
0x118cf  ldarg.0
0x118d0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x118d5  ldstr    aWebresource_0// "$webresource:"
0x118da  ldloc.0
0x118db  call     string [mscorlib]System.String::Concat(string, string)
0x118e0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string)
0x118e5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x118ea  ldarg.0
0x118eb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x118f0  ldstr    aIchunksize// "_iChunkSize"
0x118f5  call     int32 [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppGantt::get_ValidationChunkSize()
0x118fa  conv.i8
0x118fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x11900  ldarg.0
0x11901  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x11906  ldstr    aWrpctokenDepen// "WRPCTOKEN-DEPENDENT"
0x1190b  ldstr    aGanttjswindowo// "GanttJsWindowOnLoad();"
0x11910  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x11915  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCustomization::.ctor()
0x1191a  stloc.1
0x1191b  ldarg.0
0x1191c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x11921  ldstr    aIsmoothscrolll// "_iSmoothScrollLimit"
0x11926  ldloc.1
0x11927  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppCustomization::get_SmoothScrollLimit()
0x1192c  conv.i8
0x1192d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x11932  ldarg.0
0x11933  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x11938  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1193d  ldstr    aViewid// "viewID"
0x11942  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11947  stloc.2
0x11948  ldarg.0
0x11949  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1194e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11953  ldstr    aViewtype// "viewType"
0x11958  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1195d  stloc.3
0x1195e  ldarg.0
0x1195f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x11964  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11969  ldstr    aStartdate// "startDate"
0x1196e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11973  stloc.s  4
0x11975  ldarg.0
0x11976  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1197b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11980  ldstr    aEnddate// "endDate"
0x11985  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1198a  stloc.s  5
0x1198c  ldarg.0
0x1198d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x11992  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11997  ldstr    aSubareatype// "subareatype"
0x1199c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x119a1  stloc.s  6
0x119a3  ldarg.0
0x119a4  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x119a9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x119ae  ldstr    aZoomlevel// "zoomLevel"
0x119b3  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x119b8  stloc.s  7
0x119ba  ldarg.0
0x119bb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x119c0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x119c5  ldstr    aSelrowid// "selRowID"
0x119ca  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x119cf  stloc.s  8
0x119d1  ldarg.0
0x119d2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x119d7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x119dc  ldstr    aSelblockid// "selBlockID"
0x119e1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x119e6  stloc.s  9
0x119e8  ldarg.0
0x119e9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x119ee  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x119f3  ldstr    aAppointmentid// "appointmentID"
0x119f8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x119fd  stloc.s  0xA
0x119ff  ldarg.0
0x11a00  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x11a05  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11a0a  ldstr    aPagingcookie// "pagingCookie"
0x11a0f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11a14  stloc.s  0xB
0x11a16  ldarg.0
0x11a17  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x11a1c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11a21  ldstr    aHidecontrols// "hideControls"
0x11a26  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11a2b  stloc.s  0xC
0x11a2d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x11a32  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x11a37  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x11a3c  ldstr    aSmGanttcontrol// "/SM/GanttControlFrame parameters:"
0x11a41  ldc.i4.0
0x11a42  newarr   [mscorlib]System.Object
0x11a47  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11a4c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x11a51  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x11a56  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x11a5b  ldstr    aViewid0Viewtyp// "viewID={0};viewType={1};startDate={2};e"...
0x11a60  ldc.i4.s 0x10
0x11a62  newarr   [mscorlib]System.Object
0x11a67  dup
0x11a68  ldc.i4.0
0x11a69  ldloc.2
0x11a6a  stelem.ref
0x11a6b  dup
0x11a6c  ldc.i4.1
0x11a6d  ldloc.3
0x11a6e  stelem.ref
0x11a6f  dup
0x11a70  ldc.i4.2
0x11a71  ldloc.s  4
0x11a73  stelem.ref
0x11a74  dup
0x11a75  ldc.i4.3
0x11a76  ldloc.s  5
0x11a78  stelem.ref
0x11a79  dup
0x11a7a  ldc.i4.4
0x11a7b  ldloc.s  6
0x11a7d  stelem.ref
0x11a7e  dup
0x11a7f  ldc.i4.5
0x11a80  ldloc.s  7
0x11a82  stelem.ref
0x11a83  dup
0x11a84  ldc.i4.6
0x11a85  ldloc.s  8
0x11a87  stelem.ref
0x11a88  dup
0x11a89  ldc.i4.7
0x11a8a  ldloc.s  9
0x11a8c  stelem.ref
0x11a8d  dup
0x11a8e  ldc.i4.8
0x11a8f  ldloc.s  0xA
0x11a91  stelem.ref
0x11a92  dup
0x11a93  ldc.i4.s 9
0x11a95  ldloc.s  0xB
0x11a97  stelem.ref
0x11a98  dup
0x11a99  ldc.i4.s 0xA
0x11a9b  ldloc.s  0xC
0x11a9d  stelem.ref
0x11a9e  dup
0x11a9f  ldc.i4.s 0xB
0x11aa1  ldloc.s  8
0x11aa3  stelem.ref
0x11aa4  dup
0x11aa5  ldc.i4.s 0xC
0x11aa7  ldloc.s  9
0x11aa9  stelem.ref
0x11aaa  dup
0x11aab  ldc.i4.s 0xD
0x11aad  ldloc.s  0xA
0x11aaf  stelem.ref
0x11ab0  dup
0x11ab1  ldc.i4.s 0xE
0x11ab3  ldloc.s  0xB
0x11ab5  stelem.ref
0x11ab6  dup
0x11ab7  ldc.i4.s 0xF
0x11ab9  ldloc.s  0xC
0x11abb  stelem.ref
0x11abc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11ac1  ldarg.0
0x11ac2  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.SM.GanttControlFrame::crmGrid
0x11ac7  ldstr    aCrmgrid// "crmGrid"
0x11acc  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x11ad1  ldarg.0
0x11ad2  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.SM.GanttControlFrame::crmGrid
0x11ad7  ldloc.s  0xC
0x11ad9  brfalse.s loc_11AE7
0x11adb  ldloc.s  0xC
0x11add  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11ae2  ldc.i4.0
0x11ae3  ceq
0x11ae5  br.s     loc_11AE8
0x11ae7  ldc.i4.1
0x11ae8  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ShowJumpBar(bool)
0x11aed  ldarg.0
0x11aee  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.SM.GanttControlFrame::crmGrid
0x11af3  ldc.i4.1
0x11af4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_MaximumSelectableItems(int32)
0x11af9  ldarg.0
0x11afa  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.SM.GanttControlFrame::crmGrid
0x11aff  ldloc.s  0xB
0x11b01  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_PagingCookie(string)
0x11b06  ldarg.0
0x11b07  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.SM.GanttControlFrame::crmGrid
0x11b0c  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::.ctor()
0x11b11  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_DataProvider(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.IGridDataProvider)
0x11b16  ldarg.0
0x11b17  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.SM.GanttControlFrame::crmGrid
0x11b1c  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.CustomGridProviderFactory::.ctor()
0x11b21  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.GridUIProvider::.ctor(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ICustomGridProviderFactory)
0x11b26  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_UIProvider(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.IGridUIProvider)
0x11b2b  ldarg.0
0x11b2c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.SM.GanttControlFrame::crmGrid
0x11b31  ldarg.0
0x11b32  ldftn    instance void Microsoft.Crm.Service.Application.Pages.SM.GanttControlFrame::DataIsReady(object sender, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.GridUIProviderEventArgs e)
0x11b38  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid/DataReadyEventHandler::.ctor(object, native int)
0x11b3d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::add_OnDataReady(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid/DataReadyEventHandler)
0x11b42  ldloc.s  6
0x11b44  brfalse.s loc_11B4F
0x11b46  ldloc.s  6
0x11b48  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11b4d  brtrue.s loc_11B56
0x11b4f  ldstr    aApptbook// "apptbook"
0x11b54  stloc.s  6
0x11b56  ldloc.2
0x11b57  brfalse.s loc_11B61
0x11b59  ldloc.2
0x11b5a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11b5f  brtrue.s loc_11B7C
0x11b61  ldloc.s  6
0x11b63  ldstr    aApptbook// "apptbook"
0x11b68  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11b6d  brtrue.s loc_11B76
0x11b6f  ldstr    a7738c997268143// "{7738C997-2681-43BE-BFCF-DB1D159B5C5A}"
0x11b74  br.s     loc_11B7B
0x11b76  ldstr    aAc0be63a14014f// "{AC0BE63A-1401-4F71-89AD-9D0A10E61A90}"
0x11b7b  stloc.2
0x11b7c  ldloc.3
0x11b7d  brfalse.s loc_11B9D
0x11b7f  ldloc.3
0x11b80  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11b85  brfalse.s loc_11B9D
0x11b87  ldarg.0
0x11b88  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Service.Application.Pages.SM.GanttControlFrame::crmGrid
0x11b8d  ldloc.3
0x11b8e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11b93  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x11b98  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ViewType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0x11b9d  ldloc.s  4
0x11b9f  brfalse.s loc_11BAB
0x11ba1  ldloc.s  4
0x11ba3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11ba8  ldc.i4.0
0x11ba9  bgt.s    loc_11BBB
0x11bab  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_LocalDateTime()
0x11bb0  stloc.s  0x16
0x11bb2  ldloca.s 0x16
0x11bb4  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x11bb9  br.s     loc_11BC7
0x11bbb  ldloc.s  4
0x11bbd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11bc2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.Convert::ToDateTime(string, class [mscorlib]System.IFormatProvider)
0x11bc7  stloc.s  0xD
0x11bc9  ldloc.s  5
0x11bcb  brfalse.s loc_11BD7
0x11bcd  ldloc.s  5
0x11bcf  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11bd4  ldc.i4.0
0x11bd5  bgt.s    loc_11BDB
0x11bd7  ldloc.s  0xD
0x11bd9  br.s     loc_11BE7
0x11bdb  ldloc.s  5
0x11bdd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11be2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.Convert::ToDateTime(string, class [mscorlib]System.IFormatProvider)
0x11be7  stloc.s  0xE
0x11be9  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x11bee  stloc.s  0xF
0x11bf0  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
  ... truncated ...
```
