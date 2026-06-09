# Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::ConfigurePage

- ea: `0x12f0`
- end: `0x16cf`
- name: `Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::ConfigurePage`
- size: `991`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x12f0`
- `0x1710`

## string_xrefs

- `0x132c`: `/_static/_common/styles/AutoToolTip.js`
- `0x1553`: `Dialog_Service_Expression_Security_Error`

## pseudocode

```c

```

## disassembly

```asm
0x12f0  ldarg.0
0x12f1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x12f6  ldarg.0
0x12f7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x12fc  ldstr    aSmResourcespec// "/sm/resourcespecs/resourceruledialog.cs"...
0x1301  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x1306  ldarg.0
0x1307  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x130c  ldstr    aStaticControls_0// "/_static/_controls/util/numberutil.js"
0x1311  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1316  ldarg.0
0x1317  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x131c  ldstr    aStaticSmResour// "/_static/sm/resourcespecs/resourcespecu"...
0x1321  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1326  ldarg.0
0x1327  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x132c  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0x1331  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1336  ldarg.0
0x1337  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x133c  ldstr    aLocidResruleCu// "LOCID_RESRULE_CUSTOM"
0x1341  ldarg.0
0x1342  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1347  ldstr    aResourceSelect// "Resource_Selection_Criteria_Custom"
0x134c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1351  ldc.i4.0
0x1352  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1357  ldarg.0
0x1358  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x135d  ldstr    aLocidResruleAl// "LOCID_RESRULE_ALL"
0x1362  ldarg.0
0x1363  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1368  ldstr    aDialogEditReso// "Dialog_Edit_Resource_Selection_All"
0x136d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1372  ldc.i4.0
0x1373  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1378  ldarg.0
0x1379  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x137e  ldstr    aLocidResruleCa// "LOCID_RESRULE_CAPERR"
0x1383  ldarg.0
0x1384  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1389  ldstr    aWebSmResources// "Web.SM.ResourceSpecs.ResourceRule.aspx_"...
0x138e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1393  ldc.i4.0
0x1394  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1399  ldarg.0
0x139a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x139f  ldstr    aLocidResruleEx// "LOCID_RESRULE_EXPAND"
0x13a4  ldarg.0
0x13a5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x13aa  ldstr    aSmResourcerule// "SM.ResourceRule.Expand.Advanced"
0x13af  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x13b4  ldc.i4.0
0x13b5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x13ba  ldarg.0
0x13bb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13c0  ldstr    aLocidResruleHi// "LOCID_RESRULE_HIDE"
0x13c5  ldarg.0
0x13c6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x13cb  ldstr    aSmResourcerule_0// "SM.ResourceRule.Hide.Advanced"
0x13d0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x13d5  ldc.i4.0
0x13d6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x13db  ldarg.0
0x13dc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x13e1  ldstr    aLocidResruleQu// "LOCID_RESRULE_QUANERR"
0x13e6  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x13eb  ldarg.0
0x13ec  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x13f1  ldstr    aWebSmResources_0// "Web.SM.ResourceSpecs.ResourceRule.aspx_"...
0x13f6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x13fb  ldc.i4.1
0x13fc  newarr   [mscorlib]System.Object
0x1401  dup
0x1402  ldc.i4.0
0x1403  ldc.i4   0x7FFFFFFF
0x1408  box      [mscorlib]System.Int32
0x140d  stelem.ref
0x140e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1413  ldc.i4.0
0x1414  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1419  ldarg.0
0x141a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x141f  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0x1424  ldstr    aQuantityC// "quantity_c"
0x1429  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x142e  ldarg.0
0x142f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1434  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1439  ldstr    aMode// "mode"
0x143e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1443  stloc.0
0x1444  ldloc.0
0x1445  ldstr    aAdd// "add"
0x144a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x144f  brtrue.s loc_145E
0x1451  ldloc.0
0x1452  ldstr    aEditnested// "editnested"
0x1457  call     bool [mscorlib]System.String::op_Equality(string, string)
0x145c  brfalse.s loc_1478
0x145e  ldarg.0
0x145f  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::SiteTd
0x1464  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x1469  ldstr    aDisplay// "display"
0x146e  ldstr    aNone// "none"
0x1473  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x1478  ldarg.0
0x1479  ldloc.0
0x147a  call     instance void Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::SetTitle(string mode)
0x147f  ldarg.0
0x1480  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1485  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x148a  ldstr    aShowadvanced// "showadvanced"
0x148f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1494  ldstr    a1// "1"
0x1499  call     bool [mscorlib]System.String::op_Equality(string, string)
0x149e  stloc.1
0x149f  ldarg.0
0x14a0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x14a5  ldstr    aBshowadvanced// "bShowAdvanced"
0x14aa  ldloc.1
0x14ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x14b0  ldloc.1
0x14b1  brfalse.s loc_14E0
0x14b3  ldarg.0
0x14b4  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::ShowHideImage
0x14b9  ldstr    aImgsUpGif// "/_imgs/up.gif"
0x14be  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x14c3  ldarg.0
0x14c4  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::ShowHideImage
0x14c9  ldarg.0
0x14ca  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x14cf  ldstr    aSmResourcerule_0// "SM.ResourceRule.Hide.Advanced"
0x14d4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x14d9  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Alt(string)
0x14de  br.s     loc_1525
0x14e0  ldarg.0
0x14e1  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::ShowHideImage
0x14e6  ldstr    aImgsDownGif// "/_imgs/down.gif"
0x14eb  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Src(string)
0x14f0  ldarg.0
0x14f1  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlImage Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::ShowHideImage
0x14f6  ldarg.0
0x14f7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x14fc  ldstr    aSmResourcerule// "SM.ResourceRule.Expand.Advanced"
0x1501  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1506  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlImage::set_Alt(string)
0x150b  ldarg.0
0x150c  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::AdvancedTable
0x1511  callvirt instance class [System.Web]System.Web.UI.CssStyleCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Style()
0x1516  ldstr    aDisplay// "display"
0x151b  ldstr    aNone// "none"
0x1520  callvirt instance void [System.Web]System.Web.UI.CssStyleCollection::Add(string, string)
0x1525  ldc.i4   0xFA6
0x152a  ldc.i4.2
0x152b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1530  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1535  brtrue.s loc_157D
0x1537  ldarg.0
0x1538  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x153d  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x1542  ldarg.0
0x1543  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1548  ldstr    aScriptLanguage// "<script language=\"javascript\">alert("...
0x154d  ldarg.0
0x154e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1553  ldstr    aDialogServiceE// "Dialog_Service_Expression_Security_Erro"...
0x1558  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x155d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x1562  ldstr    aClosewindowScr// "\");closeWindow();</script>"
0x1567  call     string [mscorlib]System.String::Concat(string, string, string)
0x156c  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x1571  ldarg.0
0x1572  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x1577  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x157c  ret
0x157d  ldarg.0
0x157e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::quantityPicker
0x1583  ldarg.0
0x1584  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1589  ldstr    aDialogEditReso// "Dialog_Edit_Resource_Selection_All"
0x158e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1593  ldstr    a1_0// "-1"
0x1598  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string, string)
0x159d  ldc.i4.1
0x159e  stloc.2
0x159f  br.s     loc_15C8
0x15a1  ldarg.0
0x15a2  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::quantityPicker
0x15a7  ldloca.s 2
0x15a9  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x15ae  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x15b3  ldloca.s 2
0x15b5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15ba  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x15bf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string, string)
0x15c4  ldloc.2
0x15c5  ldc.i4.1
0x15c6  add
0x15c7  stloc.2
0x15c8  ldloc.2
0x15c9  ldc.i4.s 0x14
0x15cb  ble.s    loc_15A1
0x15cd  ldarg.0
0x15ce  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::quantityPicker
0x15d3  ldc.i4.2
0x15d4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::set_Required(int32)
0x15d9  ldarg.0
0x15da  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::sitePicker
0x15df  ldarg.0
0x15e0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x15e5  ldstr    aResourceSelect_0// "Resource_Selection_Site_Same"
0x15ea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15ef  ldstr    a1// "1"
0x15f4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x15f9  ldarg.0
0x15fa  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::sitePicker
0x15ff  ldarg.0
0x1600  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1605  ldstr    aResourceSelect_1// "Resource_Selection_Site_Any"
0x160a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x160f  ldstr    a0// "0"
0x1614  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x1619  ldarg.0
0x161a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::sitePicker
0x161f  ldstr    a1// "1"
0x1624  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x1629  ldarg.0
0x162a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::criteriaPicker
0x162f  ldarg.0
0x1630  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1635  ldstr    aResourceSelect_2// "Resource_Selection_Criteria_Random"
0x163a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x163f  ldstr    a0// "0"
0x1644  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x1649  ldarg.0
0x164a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::criteriaPicker
0x164f  ldarg.0
0x1650  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1655  ldstr    aResourceSelect_3// "Resource_Selection_Criteria_Least_Busy"
0x165a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x165f  ldstr    a1// "1"
0x1664  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x1669  ldarg.0
0x166a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::criteriaPicker
0x166f  ldarg.0
0x1670  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1675  ldstr    aResourceSelect_4// "Resource_Selection_Criteria_Most_Busy"
0x167a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x167f  ldstr    a2// "2"
0x1684  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x1689  ldarg.0
0x168a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::criteriaPicker
0x168f  ldstr    a0// "0"
0x1694  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x1699  ldarg.0
0x169a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x169f  ldstr    aSdecimalsepara// "sDecimalSeparator"
0x16a4  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x16a9  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0x16ae  callvirt instance string [mscorlib]System.Globalization.NumberFormatInfo::get_NumberDecimalSeparator()
0x16b3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x16b8  ldarg.0
0x16b9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x16be  ldstr    aImaxint// "iMaxInt"
0x16c3  ldc.i4   0x7FFFFFFF
0x16c8  conv.i8
0x16c9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x16ce  ret
```
