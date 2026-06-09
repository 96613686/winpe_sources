# Microsoft.Crm.Web.Tools.Solution.AreaPage::ConfigureHeader

- ea: `0x516e0`
- end: `0x51a85`
- name: `Microsoft.Crm.Web.Tools.Solution.AreaPage::ConfigureHeader`
- size: `933`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x516e0`
- `0x536a0`
- `0x537b0`
- `0xd6830`

## string_xrefs

- `0x516ec`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0x51a4a`: `/_grid/cmds/dlg_delete.aspx`
- `0x5189d`: `SystemCustomization.EntityUtil.Messages.CannotDeleteSystemEntity`
- `0x517ac`: `/_static/_common/scripts/RibbonActions.js`
- `0x516fc`: `/_static/_common/scripts/Mscrm.Caching.js`
- `0x5176c`: `/_static/tools/solution/scripts/solutionComponentList.js`
- `0x5179c`: `/_static/_controls/SolutionComponentFilter/SolutionComponentFilter.js`
- `0x5187c`: `Message.SolutionHomePage.CantDelete`
- `0x518b3`: `LOCID_SOLUTIONCOMPONENT_REMOVING`
- `0x518be`: `Solution.SolutionComponent.Messages.Removing`
- `0x518df`: `Solution.SolutionComponent.OptionSet.Messages.PublishingOptionSet`
- `0x518f5`: `LOCID_DELETE_CLIENTEXT`
- `0x51900`: `Solution.SolutionComponent.ClientExtension.Delete`
- `0x51916`: `LOCID_DELETE_DEFAULT_CLIENTEXT`
- `0x51921`: `Solution.SolutionComponent.ClientExtension.Delete.Default`
- `0x51979`: `LOCID_DELETE_SITEMAP`
- `0x519a5`: `SystemCustomization.CustomControlUtil.Messages.CannotDeleteManagedCustomControl`
- `0x51a6a`: `DashboardWebService`

## pseudocode

```c

```

## disassembly

```asm
0x516e0  ldarg.0
0x516e1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAreaPage::ConfigureHeader()
0x516e6  ldarg.0
0x516e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x516ec  ldstr    aStaticCommonSc// "/_static/_common/scripts/CrmInternalUti"...
0x516f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x516f6  ldarg.0
0x516f7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x516fc  ldstr    aStaticCommonSc_13// "/_static/_common/scripts/Mscrm.Caching."...
0x51701  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x51706  ldarg.0
0x51707  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5170c  ldstr    aStaticGridCmds// "/_static/_grid/cmds/util.js"
0x51711  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x51716  ldarg.0
0x51717  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5171c  ldstr    aStaticControls_1// "/_static/_controls/lookup/lookup.js"
0x51721  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x51726  ldarg.0
0x51727  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5172c  ldstr    aStaticControls_14// "/_static/_controls/lookup/lookupdialogs"...
0x51731  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x51736  ldarg.0
0x51737  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5173c  ldstr    aStaticFormsLoo// "/_static/_forms/lookupbehavior.js"
0x51741  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x51746  ldarg.0
0x51747  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5174c  ldstr    aStaticToolsSys_0// "/_static/tools/systemcustomization/scri"...
0x51751  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x51756  ldarg.0
0x51757  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5175c  ldstr    aStaticToolsDep// "/_static/tools/dependency/scripts/depen"...
0x51761  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x51766  ldarg.0
0x51767  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5176c  ldstr    aStaticToolsSol_0// "/_static/tools/solution/scripts/solutio"...
0x51771  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x51776  ldarg.0
0x51777  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5177c  ldstr    aStaticToolsSol// "/_static/tools/solution/scripts/Managed"...
0x51781  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x51786  ldarg.0
0x51787  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5178c  ldstr    aStaticControls_18// "/_static/_controls/TreeNav/treenavcontr"...
0x51791  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x51796  ldarg.0
0x51797  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5179c  ldstr    aStaticControls_19// "/_static/_controls/SolutionComponentFil"...
0x517a1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x517a6  ldarg.0
0x517a7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x517ac  ldstr    aStaticCommonSc_8// "/_static/_common/scripts/RibbonActions."...
0x517b1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x517b6  ldarg.0
0x517b7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x517bc  ldstr    aToolsSolutionA// "/tools/solution/area.css.aspx"
0x517c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x517c6  ldarg.0
0x517c7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x517cc  ldstr    aLocidOnlyselec// "LOCID_ONLYSELECTONE_WARN"
0x517d1  ldarg.0
0x517d2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x517d7  ldstr    aMessageSolutio// "Message.SolutionHomePage.OnlySelectOne"
0x517dc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x517e1  ldc.i4.0
0x517e2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x517e7  ldarg.0
0x517e8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x517ed  ldstr    aLocidSelectone// "LOCID_SELECTONE_WARN"
0x517f2  ldarg.0
0x517f3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x517f8  ldstr    aMessageSolutio_0// "Message.SolutionHomePage.SelectOne"
0x517fd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x51802  ldc.i4.0
0x51803  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x51808  ldarg.0
0x51809  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5180e  ldstr    aLocidSelectone_0// "LOCID_SELECTONEORMORE_WARN"
0x51813  ldarg.0
0x51814  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x51819  ldstr    aMessageSolutio_1// "Message.SolutionHomePage.SelectOneOrMor"...
0x5181e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x51823  ldc.i4.0
0x51824  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x51829  ldarg.0
0x5182a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5182f  ldstr    aLocidEntutlPub// "LOCID_ENTUTL_PUBLISHINGENT"
0x51834  ldarg.0
0x51835  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5183a  ldstr    aSystemcustomiz_10// "SystemCustomization.EntityUtil.Messages"...
0x5183f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x51844  ldc.i4.0
0x51845  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x5184a  ldarg.0
0x5184b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x51850  ldstr    aLocidEntutlCan_1// "LOCID_ENTUTL_CANTPUBLISHENT"
0x51855  ldarg.0
0x51856  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5185b  ldstr    aSystemcustomiz_6// "SystemCustomization.EntityUtil.Messages"...
0x51860  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x51865  ldc.i4.0
0x51866  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x5186b  ldarg.0
0x5186c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x51871  ldstr    aLocidSalesDash// "LOCID_SALES_DASHBOARD"
0x51876  ldarg.0
0x51877  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5187c  ldstr    aMessageSolutio_2// "Message.SolutionHomePage.CantDelete"
0x51881  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x51886  ldc.i4.0
0x51887  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x5188c  ldarg.0
0x5188d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x51892  ldstr    aLocidEntutlCan_0// "LOCID_ENTUTL_CANTDELSYSENT"
0x51897  ldarg.0
0x51898  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5189d  ldstr    aSystemcustomiz_5// "SystemCustomization.EntityUtil.Messages"...
0x518a2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x518a7  ldc.i4.0
0x518a8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x518ad  ldarg.0
0x518ae  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x518b3  ldstr    aLocidSolutionc// "LOCID_SOLUTIONCOMPONENT_REMOVING"
0x518b8  ldarg.0
0x518b9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x518be  ldstr    aSolutionSoluti// "Solution.SolutionComponent.Messages.Rem"...
0x518c3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x518c8  ldc.i4.0
0x518c9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x518ce  ldarg.0
0x518cf  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x518d4  ldstr    aLocidOptionset// "LOCID_OPTIONSET_PUBLISHING"
0x518d9  ldarg.0
0x518da  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x518df  ldstr    aSolutionSoluti_0// "Solution.SolutionComponent.OptionSet.Me"...
0x518e4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x518e9  ldc.i4.0
0x518ea  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x518ef  ldarg.0
0x518f0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x518f5  ldstr    aLocidDeleteCli// "LOCID_DELETE_CLIENTEXT"
0x518fa  ldarg.0
0x518fb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x51900  ldstr    aSolutionSoluti_1// "Solution.SolutionComponent.ClientExtens"...
0x51905  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5190a  ldc.i4.0
0x5190b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x51910  ldarg.0
0x51911  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x51916  ldstr    aLocidDeleteDef// "LOCID_DELETE_DEFAULT_CLIENTEXT"
0x5191b  ldarg.0
0x5191c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x51921  ldstr    aSolutionSoluti_2// "Solution.SolutionComponent.ClientExtens"...
0x51926  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5192b  ldc.i4.0
0x5192c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x51931  ldarg.0
0x51932  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x51937  ldstr    aLocidSetDefaul// "LOCID_SET_DEFAULT_DASHBOARD"
0x5193c  ldarg.0
0x5193d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x51942  ldstr    aSetdefaultDash// "SetDefault_Dashboard_Defaulting"
0x51947  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5194c  ldc.i4.0
0x5194d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x51952  ldarg.0
0x51953  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x51958  ldstr    aLocidSaveasDas// "LOCID_SAVEAS_DASHBOARD"
0x5195d  ldarg.0
0x5195e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x51963  ldstr    aSaveasDashboar// "SaveAs_Dashboard"
0x51968  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5196d  ldc.i4.0
0x5196e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x51973  ldarg.0
0x51974  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x51979  ldstr    aLocidDeleteSit// "LOCID_DELETE_SITEMAP"
0x5197e  ldarg.0
0x5197f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x51984  ldstr    aErrorMessage0x_4// "Error_Message_0x80048070"
0x51989  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5198e  ldc.i4.0
0x5198f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x51994  ldarg.0
0x51995  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5199a  ldstr    aLocidCustctrlu// "LOCID_CUSTCTRLUTL_CANTDELMANAGED"
0x5199f  ldarg.0
0x519a0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x519a5  ldstr    aSystemcustomiz_17// "SystemCustomization.CustomControlUtil.M"...
0x519aa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x519af  ldc.i4.0
0x519b0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x519b5  ldarg.0
0x519b6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x519bb  ldstr    aBisdefaultsolu// "_bIsDefaultSolution"
0x519c0  ldarg.0
0x519c1  call     instance bool Microsoft.Crm.Web.Tools.Solution.AreaPage::IsDefaultSolution()
0x519c6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x519cb  ldarg.0
0x519cc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x519d1  ldarg.0
0x519d2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x519d7  ldc.i4.0
0x519d8  call     void Microsoft.Crm.Application.Pages.tools.SystemCustomization.Common.SegmentationUtility::SetSegmentationHeaders(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header currentHeader, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager currentResourceManager, [opt] bool skipSubcomponentTypes)
0x519dd  ldarg.0
0x519de  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x519e3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x519e8  ldstr    aObjecttypecode// "objecttypecode"
0x519ed  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x519f2  brfalse.s loc_51A39
0x519f4  ldarg.0
0x519f5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x519fa  ldstr    aLocidObjecttyp// "LOCID_OBJECTTYPECODE"
0x519ff  ldarg.0
0x51a00  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x51a05  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x51a0a  ldstr    aObjecttypecode_0// "objectTypeCode"
0x51a0f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51a14  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x51a19  ldarg.0
0x51a1a  ldarg.0
0x51a1b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x51a20  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x51a25  ldstr    aObjecttypecode// "objecttypecode"
0x51a2a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x51a2f  call     int32 [mscorlib]System.Convert::ToInt32(string)
0x51a34  stfld    int32 Microsoft.Crm.Web.Tools.Solution.AreaPage::entityTypeCode
0x51a39  ldarg.0
0x51a3a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x51a3f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath()
0x51a44  ldarg.0
0x51a45  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x51a4a  ldstr    aGridCmdsDlgDel// "/_grid/cmds/dlg_delete.aspx"
0x51a4f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x51a54  ldarg.0
0x51a55  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x51a5a  ldstr    aGridCmdsDlgAct// "/_grid/cmds/dlg_activate.aspx"
0x51a5f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x51a64  ldarg.0
0x51a65  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x51a6a  ldstr    aDashboardwebse// "DashboardWebService"
0x51a6f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x51a74  ldarg.0
0x51a75  call     instance void Microsoft.Crm.Web.Tools.Solution.AreaPage::SetSolutionVariable()
0x51a7a  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::.ctor()
0x51a7f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x51a84  ret
```
