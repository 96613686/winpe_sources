# Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::ConfigurePage

- ea: `0x16470`
- end: `0x16776`
- name: `Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::ConfigurePage`
- size: `774`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x16470`
- `0x16780`
- `0x168a0`
- `0x168f0`

## string_xrefs

- `0x16486`: `/_static/_common/scripts/stage.js`

## pseudocode

```c

```

## disassembly

```asm
0x16470  ldarg.0
0x16471  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x16476  ldstr    aNavMenuCssAspx// "/_nav/menu.css.aspx"
0x1647b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x16480  ldarg.0
0x16481  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x16486  ldstr    aStaticCommonSc_0// "/_static/_common/scripts/stage.js"
0x1648b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x16490  ldarg.0
0x16491  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x16496  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0x1649b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x164a0  ldarg.0
0x164a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x164a6  ldstr    aSmApptbookAppt// "/sm/apptbook/apptbook.css.aspx"
0x164ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x164b0  ldarg.0
0x164b1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x164b6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x164bb  ldstr    aRowtype// "rowType"
0x164c0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x164c5  stloc.0
0x164c6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x164cb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x164d0  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x164d5  ldstr    aSmDetailsappoi// "/SM/DetailsAppointmentPane.aspx paramet"...
0x164da  ldc.i4.5
0x164db  newarr   [mscorlib]System.Object
0x164e0  dup
0x164e1  ldc.i4.0
0x164e2  ldarg.0
0x164e3  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x164e8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x164ed  ldstr    aRowid_0// "rowId"
0x164f2  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x164f7  stelem.ref
0x164f8  dup
0x164f9  ldc.i4.1
0x164fa  ldarg.0
0x164fb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16500  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x16505  ldstr    aSubareatype// "subAreaType"
0x1650a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1650f  stelem.ref
0x16510  dup
0x16511  ldc.i4.2
0x16512  ldloc.0
0x16513  stelem.ref
0x16514  dup
0x16515  ldc.i4.3
0x16516  ldarg.0
0x16517  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1651c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x16521  ldstr    aBlockid// "blockId"
0x16526  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1652b  stelem.ref
0x1652c  dup
0x1652d  ldc.i4.4
0x1652e  ldarg.0
0x1652f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16534  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x16539  ldstr    aBlocktype// "blockType"
0x1653e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16543  stelem.ref
0x16544  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16549  ldloc.0
0x1654a  brfalse  loc_16766
0x1654f  ldloc.0
0x16550  callvirt instance int32 [mscorlib]System.String::get_Length()
0x16555  ldc.i4.0
0x16556  ble      loc_16766
0x1655b  ldarg.0
0x1655c  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16561  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x16566  ldstr    aSubareatype// "subAreaType"
0x1656b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16570  stloc.1
0x16571  ldloca.s 2
0x16573  ldarg.0
0x16574  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16579  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1657e  ldstr    aRowid_0// "rowId"
0x16583  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16588  call     instance void [mscorlib]System.Guid::.ctor(string)
0x1658d  ldloc.0
0x1658e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16593  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x16598  stloc.3
0x16599  ldloc.1
0x1659a  ldstr    aApptbook// "apptbook"
0x1659f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x165a4  brtrue.s loc_165BB
0x165a6  ldloc.1
0x165a7  ldstr    aSchedules// "schedules"
0x165ac  call     bool [mscorlib]System.String::op_Equality(string, string)
0x165b1  brtrue   loc_1666F
0x165b6  br       loc_166F6
0x165bb  ldarg.0
0x165bc  ldloc.3
0x165bd  ldloca.s 2
0x165bf  ldstr    aB// "B"
0x165c4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x165c9  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x165ce  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x165d3  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x165d8  call     instance void Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::GetTabNamesForEntity(int32 entityType, string entityID)
0x165dd  ldloc.3
0x165de  ldc.i4   0x1076
0x165e3  bne.un   loc_16706
0x165e8  ldarg.0
0x165e9  ldarg.0
0x165ea  ldfld    string Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::_pagesScript
0x165ef  ldarg.0
0x165f0  call     instance string Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::AddDiv()
0x165f5  call     string [mscorlib]System.String::Concat(string, string)
0x165fa  stfld    string Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::_pagesScript
0x165ff  ldarg.0
0x16600  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0x16605  ldarg.0
0x16606  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1660b  ldstr    aAppointmentboo// "AppointmentBook_Details_Resource_Schedu"...
0x16610  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x16615  ldarg.0
0x16616  ldflda   int32 Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::_pageIndex
0x1661b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16620  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x16625  ldstr    asc_31504// "_"
0x1662a  call     string [mscorlib]System.String::Concat(string, string)
0x1662f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0x16634  ldarg.0
0x16635  ldarg.0
0x16636  ldfld    string Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::_pagesNames
0x1663b  ldstr    aResourceschedu// "\"ResourceSchedules.aspx?id="
0x16640  ldloca.s 2
0x16642  ldstr    aB// "B"
0x16647  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1664c  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x16651  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16656  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x1665b  ldstr    asc_3193C// "\","
0x16660  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x16665  stfld    string Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::_pagesNames
0x1666a  br       loc_16706
0x1666f  ldarg.0
0x16670  ldloc.3
0x16671  ldloca.s 2
0x16673  ldstr    aB// "B"
0x16678  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1667d  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x16682  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16687  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x1668c  call     instance void Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::GetTabNamesForEntity(int32 entityType, string entityID)
0x16691  ldarg.0
0x16692  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x16697  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1669c  ldstr    aBlocktype// "blockType"
0x166a1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x166a6  stloc.s  4
0x166a8  ldarg.0
0x166a9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x166ae  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x166b3  ldstr    aBlockid// "blockId"
0x166b8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x166bd  stloc.s  5
0x166bf  ldloc.s  4
0x166c1  brfalse.s loc_16706
0x166c3  ldloc.s  4
0x166c5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x166ca  ldc.i4.0
0x166cb  ble.s    loc_16706
0x166cd  ldloc.s  5
0x166cf  brfalse.s loc_16706
0x166d1  ldloc.s  5
0x166d3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x166d8  ldc.i4.0
0x166d9  ble.s    loc_16706
0x166db  ldarg.0
0x166dc  ldloc.s  4
0x166de  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x166e3  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x166e8  ldloc.s  5
0x166ea  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetGuid(string)
0x166ef  call     instance void Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::GetTabNamesForEntity(int32 entityType, string entityID)
0x166f4  br.s     loc_16706
0x166f6  ldstr    aThisSubAreaIsN// "This sub area is not supported"
0x166fb  ldc.i4   0x8004023B
0x16700  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x16705  throw
0x16706  ldarg.0
0x16707  ldarg.0
0x16708  ldfld    int32 Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::_pageIndex
0x1670d  ldc.i4.0
0x1670e  blt.s    loc_16735
0x16710  ldarg.0
0x16711  ldfld    string Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::_pagesNames
0x16716  ldc.i4.0
0x16717  ldarg.0
0x16718  ldfld    string Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::_pagesNames
0x1671d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x16722  ldc.i4.1
0x16723  sub
0x16724  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x16729  ldstr    asc_31980// ");"
0x1672e  call     string [mscorlib]System.String::Concat(string, string)
0x16733  br.s     loc_1673A
0x16735  ldsfld   string [mscorlib]System.String::Empty
0x1673a  stfld    string Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::_pagesNames
0x1673f  ldarg.0
0x16740  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x16745  ldstr    aApptbookdetail// "apptBookDetailPages"
0x1674a  ldarg.0
0x1674b  ldfld    string Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::_pagesNames
0x16750  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlock(string, string)
0x16755  ldarg.0
0x16756  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::divGenerator
0x1675b  ldarg.0
0x1675c  ldfld    string Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::_pagesScript
0x16761  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x16766  ldarg.0
0x16767  ldfld    int32 Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::_pageIndex
0x1676c  ldc.i4.0
0x1676d  bge.s    loc_16775
0x1676f  ldarg.0
0x16770  call     instance void Microsoft.Crm.Common.Application.Pages.SM.AppointmentBook.DetailsPane::NoSelectionViewed()
0x16775  ret
```
