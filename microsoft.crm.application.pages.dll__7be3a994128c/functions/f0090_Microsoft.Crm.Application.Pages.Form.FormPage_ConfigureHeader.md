# Microsoft.Crm.Application.Pages.Form.FormPage::ConfigureHeader

- ea: `0xf0090`
- end: `0xf0898`
- name: `Microsoft.Crm.Application.Pages.Form.FormPage::ConfigureHeader`
- size: `2056`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0xf0090`
- `0xf08a0`
- `0xf0990`
- `0xf0c00`
- `0xf0d10`
- `0xf0e90`
- `0xf0f20`

## string_xrefs

- `0xf0203`: `/_common/styles/miniCal.css.aspx`
- `0xf0303`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0xf0213`: `/_common/styles/select.css.aspx`
- `0xf01a3`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0xf052b`: `/_static/_common/scripts/CommandBarActions.js`
- `0xf0333`: `/_static/_common/scripts/Performance.js`
- `0xf01e3`: `/_static/_common/scripts/es6-shim.js`
- `0xf05ee`: `/_static/_common/scripts/BusinessRulesExecution.js`
- `0xf053b`: `/_static/_common/scripts/RibbonActions.js`
- `0xf0323`: `/_static/_common/scripts/Mscrm.Caching.js`
- `0xf0243`: `/_common/styles/menucore.css.aspx`
- `0xf0263`: `/_controls/CompositeControl/CompositeControl.css.aspx`
- `0xf061e`: `/_static/_common/scripts/InlineEditCommon.js`
- `0xf05de`: `/_static/_controls/GlobalQuickCreate/GlobalQuickCreateBehavior.js`
- `0xf06de`: `/_static/_common/scripts/Wall.Interfaces.js`
- `0xf06ee`: `/_static/_common/scripts/Wall.Control.js`
- `0xf0595`: `/_common/windowinformation/windowinformation.js.aspx`
- `0xf065e`: `/_static/_common/scripts/SalesCommonImported.js`
- `0xf066e`: `/_static/_common/scripts/SalesCommonFramework.js`
- `0xf069e`: `/_static/_common/scripts/SalesCommonFramework.js`
- `0xf06be`: `/_static/_common/scripts/app_portal_shared.js`
- `0xf067e`: `/_static/_common/scripts/SalesCrmSoapProxyService.js`
- `0xf04fb`: `/_static/_controls/ReadForm/ReadFormUtilities.js`
- `0xf01b3`: `/_static/_common/scripts/jqueryplugins.js`
- `0xf01c3`: `/_static/_common/scripts/jquery.jstree.js`
- `0xf01d3`: `/_static/_common/scripts/jquery.hotkeys.js`
- `0xf0253`: `/_forms/styles/read.css.aspx`
- `0xf037d`: `/_static/_Common/scripts/Stage.js`
- `0xf039d`: `/_static/_common/scripts/GlowingImage.js`
- `0xf03ad`: `/_static/_controls/pane/compositecontrol.js`
- `0xf03fd`: `/_static/entities/ServiceRefreshUtilities.js`
- `0xf04cb`: `/_static/_common/scripts/Main.js`
- `0xf04db`: `/_static/_common/scripts/MainControls.js`
- `0xf04eb`: `/_static/_common/scripts/Details.js`
- `0xf064e`: `/_static/_controls/CompositeData/CompositeDataControl.js`
- `0xf06ae`: `/_common/styles/appportal.css.aspx`
- `0xf06ce`: `/_static/_common/scripts/watermarktextbox.js`
- `0xf06fe`: `/_static/_controls/ActivityContainer/ActivityCommandBar.js`
- `0xf072e`: `/_static/_controls/SearchWidget/ExternalInteractionService.js`
- `0xf073e`: `/_static/_controls/BreadCrumbControl/BreadCrumbControl.js`
- `0xf086c`: `window.trackClosures = 1;\n					window.windowObjects = [];\n					window.closureEvents = [];\n					var savedAddHandler=$addHandler;\n					$addHandler=function(a,d,e,g)\n					{\n						var trackRequired = true;\n						if (typeof window.closureEvents !== 'undefined' && window.closureEvents.length > 0)\n						{\n							if (typeof a.uniqueId != "undefined" && typeof window.closureEvents[a.uniqueId.toString()] === "undefined") /* Check if we have valid ClosureEvents index here. */\n							{\`

## pseudocode

```c

```

## disassembly

```asm
0xf0090  ldarg.0
0xf0091  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf0096  ldc.i4.1
0xf0097  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0xf009c  ldarg.0
0xf009d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf00a2  ldc.i4.1
0xf00a3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQueryTemplate(bool)
0xf00a8  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xf00ad  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xf00b2  callvirt instance int32 [mscorlib]System.Globalization.NumberFormatInfo::get_CurrencyPositivePattern()
0xf00b7  stloc.0
0xf00b8  ldarg.0
0xf00b9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf00be  ldstr    aSymbolpoistion// "SYMBOLPOISTION_CURRENCY"
0xf00c3  ldloc.0
0xf00c4  brfalse.s loc_F00CC
0xf00c6  ldloc.0
0xf00c7  ldc.i4.2
0xf00c8  ceq
0xf00ca  br.s     loc_F00CD
0xf00cc  ldc.i4.1
0xf00cd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xf00d2  ldarg.0
0xf00d3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf00d8  ldstr    aIsflatuipage// "_ISFLATUIPAGE"
0xf00dd  ldc.i4.1
0xf00de  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xf00e3  ldarg.0
0xf00e4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf00e9  ldstr    aLocidPageLoadi// "LOCID_PAGE_LOADING"
0xf00ee  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf00f3  ldstr    aPageloadingmes// "PageLoadingMessage"
0xf00f8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf00fd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf0102  ldarg.0
0xf0103  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0108  ldstr    aLocidPageLoadi_0// "LOCID_PAGE_LOADING_REQUEST_DATA"
0xf010d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0112  ldstr    aPageloadingmes_0// "PageLoadingMessage.RequestingData"
0xf0117  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf011c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf0121  ldarg.0
0xf0122  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0127  ldstr    aLocidPageLoadi_1// "LOCID_PAGE_LOADING_PROCESSING_DATA"
0xf012c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0131  ldstr    aPageloadingmes_1// "PageLoadingMessage.ProcessingData"
0xf0136  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf013b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf0140  ldarg.0
0xf0141  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0146  ldstr    aLocidPageLoadi_2// "LOCID_PAGE_LOADING_EXECUTE_ON_LOAD_FROM"...
0xf014b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0150  ldstr    aPageloadingmes_2// "PageLoadingMessage.RequestingDataFromEx"...
0xf0155  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf015a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf015f  ldarg.0
0xf0160  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0165  ldstr    aLocidPageLoadi_3// "LOCID_PAGE_LOADING_EXECUTE_ON_LOAD"
0xf016a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf016f  ldstr    aPageloadingmes_3// "PageLoadingMessage.ExecuteOnload"
0xf0174  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0179  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf017e  ldarg.0
0xf017f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0184  ldstr    aLocidPageLoadi_4// "LOCID_PAGE_LOADING_UPDATING_UI"
0xf0189  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf018e  ldstr    aPageloadingmes_4// "PageLoadingMessage.UpdatingUI"
0xf0193  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0198  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf019d  ldarg.0
0xf019e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf01a3  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/jquery_ui_1.8."...
0xf01a8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf01ad  ldarg.0
0xf01ae  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf01b3  ldstr    aStaticCommonSc_56// "/_static/_common/scripts/jqueryplugins."...
0xf01b8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf01bd  ldarg.0
0xf01be  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf01c3  ldstr    aStaticCommonSc_57// "/_static/_common/scripts/jquery.jstree."...
0xf01c8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf01cd  ldarg.0
0xf01ce  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf01d3  ldstr    aStaticCommonSc_58// "/_static/_common/scripts/jquery.hotkeys"...
0xf01d8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf01dd  ldarg.0
0xf01de  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf01e3  ldstr    aStaticCommonSc_6// "/_static/_common/scripts/es6-shim.js"
0xf01e8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf01ed  ldarg.0
0xf01ee  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf01f3  ldstr    aControlsNotifi_0// "/_controls/notifications/notifications."...
0xf01f8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf01fd  ldarg.0
0xf01fe  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf0203  ldstr    aCommonStylesMi// "/_common/styles/miniCal.css.aspx"
0xf0208  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf020d  ldarg.0
0xf020e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf0213  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0xf0218  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf021d  ldarg.0
0xf021e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf0223  ldstr    aControlsRefres// "/_controls/refreshform/flyoutdialog.css"...
0xf0228  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf022d  ldarg.0
0xf022e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf0233  ldstr    aNavMenuCssAspx// "/_nav/menu.css.aspx"
0xf0238  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf023d  ldarg.0
0xf023e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf0243  ldstr    aCommonStylesMe// "/_common/styles/menucore.css.aspx"
0xf0248  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf024d  ldarg.0
0xf024e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf0253  ldstr    aFormsStylesRea// "/_forms/styles/read.css.aspx"
0xf0258  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf025d  ldarg.0
0xf025e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf0263  ldstr    aControlsCompos// "/_controls/CompositeControl/CompositeCo"...
0xf0268  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf026d  ldarg.0
0xf026e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf0273  ldstr    aControlsHtmlba// "/_controls/htmlbar/htmlbar.css.aspx"
0xf0278  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf027d  ldarg.0
0xf027e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf0283  ldstr    aNavNavCssAspx// "/_nav/nav.css.aspx"
0xf0288  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf028d  ldarg.0
0xf028e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf0293  ldstr    aGridAppgridCss// "/_grid/appgrid.css.aspx"
0xf0298  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf029d  ldarg.0
0xf029e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf02a3  ldstr    aControlsTabsTa// "/_controls/tabs/tabs.css.aspx"
0xf02a8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf02ad  ldarg.0
0xf02ae  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf02b3  ldstr    aStaticControls_39// "/_static/_controls/activitycontainer/ac"...
0xf02b8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf02bd  ldarg.0
0xf02be  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf02c3  ldstr    aStaticWallcont// "/_static/WallControl/ActivitiesWallCont"...
0xf02c8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf02cd  ldarg.0
0xf02ce  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf02d3  ldstr    aStaticWallcont_0// "/_static/WallControl/ActivitiesWallCont"...
0xf02d8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf02dd  ldarg.0
0xf02de  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf02e3  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0xf02e8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf02ed  ldarg.0
0xf02ee  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf02f3  ldstr    aControlsBingma// "/_controls/bingmaps/bingmaps.css.aspx"
0xf02f8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf02fd  ldarg.0
0xf02fe  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf0303  ldstr    aStaticCommonSc// "/_static/_common/scripts/CrmInternalUti"...
0xf0308  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf030d  ldarg.0
0xf030e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf0313  ldstr    aStaticControls_40// "/_static/_controls/NotificationList/Not"...
0xf0318  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf031d  ldarg.0
0xf031e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf0323  ldstr    aStaticCommonSc_13// "/_static/_common/scripts/Mscrm.Caching."...
0xf0328  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf032d  ldarg.0
0xf032e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf0333  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/Performance.js"
0xf0338  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf033d  ldarg.0
0xf033e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf0343  ldstr    aStaticFormForm// "/_static/form/FormControls.js"
0xf0348  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf034d  ldarg.0
0xf034e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf0353  ldstr    aStaticGridGrid// "/_static/_grid/GridControl.js"
0xf0358  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf035d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf0362  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xf0367  ldarg.0
0xf0368  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf036d  ldstr    aStaticGridActi// "/_static/_grid/action.js"
0xf0372  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0377  ldarg.0
0xf0378  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf037d  ldstr    aStaticCommonSc_59// "/_static/_Common/scripts/Stage.js"
0xf0382  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0387  ldarg.0
0xf0388  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf038d  ldstr    aStaticControls_41// "/_static/_controls/HintText/HintText.js"
0xf0392  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0397  ldarg.0
0xf0398  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf039d  ldstr    aStaticCommonSc_60// "/_static/_common/scripts/GlowingImage.j"...
0xf03a2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf03a7  ldarg.0
0xf03a8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf03ad  ldstr    aStaticControls_42// "/_static/_controls/pane/compositecontro"...
0xf03b2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf03b7  ldarg.0
0xf03b8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf03bd  ldstr    aStaticControls_17// "/_static/_controls/MenuSelector/MenuSel"...
0xf03c2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf03c7  ldarg.0
0xf03c8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf03cd  ldstr    aStaticVisualiz_1// "/_static/visualization/visualizationact"...
0xf03d2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf03d7  ldarg.0
0xf03d8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf03dd  ldstr    aStaticControls_43// "/_static/_controls/pane/visualizationpa"...
0xf03e2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf03e7  ldarg.0
0xf03e8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf03ed  ldstr    aStaticToolsDoc_7// "/_static/Tools/DocumentManagement/Scrip"...
0xf03f2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf03f7  ldarg.0
0xf03f8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf03fd  ldstr    aStaticEntities_5// "/_static/entities/ServiceRefreshUtiliti"...
0xf0402  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0407  ldarg.0
0xf0408  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf040d  ldstr    aStaticFormsLoo_0// "/_static/_forms/LookupBehavior.js"
0xf0412  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0417  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0xf041c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_EnableBingMapsIntegration()
0xf0421  brfalse.s loc_F0445
0xf0423  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsMapControlFeatureAvailable()
0xf0428  brfalse.s loc_F0445
0xf042a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf042f  ldc.i4.1
0xf0430  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.BingMapsIntegrationHelper::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, bool)
0xf0435  ldarg.0
0xf0436  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf043b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0440  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.BingMapsIntegrationHelper::AddCommonScriptsAndResources(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager)
0xf0445  ldarg.0
0xf0446  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf044b  ldstr    aStaticFormsFor_0// "/_static/_forms/Form.js"
0xf0450  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0455  ldarg.0
0xf0456  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf045b  ldstr    aStaticControls_44// "/_static/_controls/emailbody/emailbody."...
0xf0460  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0465  ldarg.0
0xf0466  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf046b  ldstr    aStaticControls_45// "/_static/_controls/EmailReciepientActiv"...
0xf0470  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0475  ldarg.0
0xf0476  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf047b  ldstr    aStaticControls_46// "/_static/_controls/EmailEngagementActio"...
0xf0480  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0485  ldarg.0
0xf0486  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf048b  ldstr    aStaticControls_47// "/_static/_controls/DPListControl/dynami"...
0xf0490  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0495  ldarg.0
0xf0496  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf049b  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0xf04a0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf04a5  ldarg.0
0xf04a6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf04ab  ldstr    aStaticFormsNum_0// "/_static/_forms/numberinputbehavior.js"
0xf04b0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf04b5  ldarg.0
0xf04b6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf04bb  ldstr    aStaticFormsTex_0// "/_static/_forms/textinputbehavior.js"
0xf04c0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf04c5  ldarg.0
0xf04c6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf04cb  ldstr    aStaticCommonSc_61// "/_static/_common/scripts/Main.js"
0xf04d0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf04d5  ldarg.0
0xf04d6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf04db  ldstr    aStaticCommonSc_62// "/_static/_common/scripts/MainControls.j"...
0xf04e0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf04e5  ldarg.0
0xf04e6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf04eb  ldstr    aStaticCommonSc_63// "/_static/_common/scripts/Details.js"
0xf04f0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf04f5  ldarg.0
0xf04f6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf04fb  ldstr    aStaticControls_35// "/_static/_controls/ReadForm/ReadFormUti"...
0xf0500  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0505  ldarg.0
0xf0506  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf050b  ldstr    aStaticMaListsL// "/_static/MA/Lists/list.js"
0xf0510  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0515  ldarg.0
0xf0516  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf051b  ldstr    aStaticControls_48// "/_static/_controls/Ribbon/Ribbon.js"
0xf0520  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf0525  ldarg.0
0xf0526  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf052b  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/CommandBarActi"...
0xf0530  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
  ... truncated ...
```
