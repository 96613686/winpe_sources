# Microsoft.Crm.Application.Pages.Dialog.DialogPage::ConfigureHeader

- ea: `0xf1040`
- end: `0xf146f`
- name: `Microsoft.Crm.Application.Pages.Dialog.DialogPage::ConfigureHeader`
- size: `1071`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xf1040`
- `0xf1470`

## string_xrefs

- `0xf1248`: `/_common/styles/dialogs.css.aspx`
- `0xf1228`: `/_common/styles/miniCal.css.aspx`
- `0xf1288`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0xf1238`: `/_common/styles/select.css.aspx`
- `0xf1188`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0xf1308`: `/_static/_common/scripts/CommandBarActions.js`
- `0xf12a8`: `/_static/_common/scripts/Performance.js`
- `0xf11c8`: `/_static/_common/scripts/es6-shim.js`
- `0xf1318`: `/_static/_common/scripts/RibbonActions.js`
- `0xf1298`: `/_static/_common/scripts/Mscrm.Caching.js`
- `0xf11d8`: `/_static/_common/scripts/react.js`
- `0xf13ae`: `/_common/windowinformation/windowinformation.js.aspx`
- `0xf136c`: `cc_MscrmControls.ActionCards.ActionCardCommands/RelationshipAssistantCommands.js`
- `0xf1198`: `/_static/_common/scripts/jqueryplugins.js`
- `0xf11a8`: `/_static/_common/scripts/jquery.jstree.js`
- `0xf11b8`: `/_static/_common/scripts/jquery.hotkeys.js`
- `0xf1258`: `/_forms/styles/read.css.aspx`
- `0xf12e8`: `/_static/_common/scripts/Main.js`
- `0xf12f8`: `/_static/_common/scripts/MainControls.js`
- `0xf1148`: `ProcessControl.Configurator.NewField`
- `0xf11e8`: `/_static/_common/scripts/fela.js`
- `0xf11f8`: `/_static/_common/scripts/react-fela.js`
- `0xf1208`: `/_static/_common/scripts/CustomControls.js`
- `0xf1218`: `/_static/_common/scripts/CustomControlsCommon.js`
- `0xf1457`: `window.trackClosures = 1;\n					window.windowObjects = [];\n					window.closureEvents = [];\n					var savedAddHandler=$addHandler;\n					$addHandler=function(a,d,e,g)\n					{\n						var trackRequired = true;\n						if (typeof window.closureEvents !== 'undefined' && window.closureEvents.length > 0) /* tracking is not required if closureEvent collection is empty */\n						{\n							if (typeof a.uniqueId != "undefined" && typeof window.closureEvents[a.uniqueId.toString()] === "undefined") `

## pseudocode

```c

```

## disassembly

```asm
0xf1040  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0xf1045  brfalse.s loc_F1061
0xf1047  ldarg.0
0xf1048  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf104d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf1052  ldstr    aBrandCrmOutloo// "Brand_CRM_Outlook_Short"
0xf1057  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf105c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0xf1061  ldarg.0
0xf1062  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1067  ldstr    aIsflatuipage// "_ISFLATUIPAGE"
0xf106c  ldc.i4.1
0xf106d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xf1072  ldarg.0
0xf1073  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1078  ldc.i4.1
0xf1079  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0xf107e  ldarg.0
0xf107f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1084  ldstr    aLocidPageLoadi// "LOCID_PAGE_LOADING"
0xf1089  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf108e  ldstr    aPageloadingmes// "PageLoadingMessage"
0xf1093  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf1098  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf109d  ldarg.0
0xf109e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf10a3  ldstr    aLocidPageLoadi_0// "LOCID_PAGE_LOADING_REQUEST_DATA"
0xf10a8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf10ad  ldstr    aPageloadingmes_0// "PageLoadingMessage.RequestingData"
0xf10b2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf10b7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf10bc  ldarg.0
0xf10bd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf10c2  ldstr    aLocidPageLoadi_1// "LOCID_PAGE_LOADING_PROCESSING_DATA"
0xf10c7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf10cc  ldstr    aPageloadingmes_1// "PageLoadingMessage.ProcessingData"
0xf10d1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf10d6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf10db  ldarg.0
0xf10dc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf10e1  ldstr    aLocidPageLoadi_2// "LOCID_PAGE_LOADING_EXECUTE_ON_LOAD_FROM"...
0xf10e6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf10eb  ldstr    aPageloadingmes_2// "PageLoadingMessage.RequestingDataFromEx"...
0xf10f0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf10f5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf10fa  ldarg.0
0xf10fb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1100  ldstr    aLocidPageLoadi_3// "LOCID_PAGE_LOADING_EXECUTE_ON_LOAD"
0xf1105  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf110a  ldstr    aPageloadingmes_3// "PageLoadingMessage.ExecuteOnload"
0xf110f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf1114  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf1119  ldarg.0
0xf111a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf111f  ldstr    aLocidPageLoadi_4// "LOCID_PAGE_LOADING_UPDATING_UI"
0xf1124  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf1129  ldstr    aPageloadingmes_4// "PageLoadingMessage.UpdatingUI"
0xf112e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf1133  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf1138  ldarg.0
0xf1139  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf113e  ldstr    aLocidIecSelect// "LOCID_IEC_SELECTTOENTER"
0xf1143  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf1148  ldstr    aProcesscontrol_50// "ProcessControl.Configurator.NewField"
0xf114d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf1152  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf1157  ldarg.0
0xf1158  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf115d  ldstr    aSymbolpoistion// "SYMBOLPOISTION_CURRENCY"
0xf1162  ldc.i4.1
0xf1163  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xf1168  ldarg.0
0xf1169  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf116e  ldstr    aBasecurrencysy// "BaseCurrencySymbol"
0xf1173  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf1178  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Formatting.CrmFormatter::GetBaseCurrencySymbol(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf117d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xf1182  ldarg.0
0xf1183  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1188  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/jquery_ui_1.8."...
0xf118d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf1192  ldarg.0
0xf1193  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1198  ldstr    aStaticCommonSc_56// "/_static/_common/scripts/jqueryplugins."...
0xf119d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf11a2  ldarg.0
0xf11a3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf11a8  ldstr    aStaticCommonSc_57// "/_static/_common/scripts/jquery.jstree."...
0xf11ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf11b2  ldarg.0
0xf11b3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf11b8  ldstr    aStaticCommonSc_58// "/_static/_common/scripts/jquery.hotkeys"...
0xf11bd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf11c2  ldarg.0
0xf11c3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf11c8  ldstr    aStaticCommonSc_6// "/_static/_common/scripts/es6-shim.js"
0xf11cd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf11d2  ldarg.0
0xf11d3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf11d8  ldstr    aStaticCommonSc_28// "/_static/_common/scripts/react.js"
0xf11dd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf11e2  ldarg.0
0xf11e3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf11e8  ldstr    aStaticCommonSc_65// "/_static/_common/scripts/fela.js"
0xf11ed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf11f2  ldarg.0
0xf11f3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf11f8  ldstr    aStaticCommonSc_66// "/_static/_common/scripts/react-fela.js"
0xf11fd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf1202  ldarg.0
0xf1203  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1208  ldstr    aStaticCommonSc_67// "/_static/_common/scripts/CustomControls"...
0xf120d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf1212  ldarg.0
0xf1213  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1218  ldstr    aStaticCommonSc_68// "/_static/_common/scripts/CustomControls"...
0xf121d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf1222  ldarg.0
0xf1223  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf1228  ldstr    aCommonStylesMi// "/_common/styles/miniCal.css.aspx"
0xf122d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf1232  ldarg.0
0xf1233  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf1238  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0xf123d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf1242  ldarg.0
0xf1243  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf1248  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0xf124d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf1252  ldarg.0
0xf1253  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf1258  ldstr    aFormsStylesRea// "/_forms/styles/read.css.aspx"
0xf125d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf1262  ldarg.0
0xf1263  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf1268  ldstr    aControlsTabsTa// "/_controls/tabs/tabs.css.aspx"
0xf126d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf1272  ldarg.0
0xf1273  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf1278  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0xf127d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf1282  ldarg.0
0xf1283  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf1288  ldstr    aStaticCommonSc// "/_static/_common/scripts/CrmInternalUti"...
0xf128d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf1292  ldarg.0
0xf1293  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf1298  ldstr    aStaticCommonSc_13// "/_static/_common/scripts/Mscrm.Caching."...
0xf129d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf12a2  ldarg.0
0xf12a3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf12a8  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/Performance.js"
0xf12ad  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf12b2  ldarg.0
0xf12b3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xf12b8  ldstr    aStaticFormForm// "/_static/form/FormControls.js"
0xf12bd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf12c2  ldarg.0
0xf12c3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf12c8  ldstr    aStaticGridActi// "/_static/_grid/action.js"
0xf12cd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf12d2  ldarg.0
0xf12d3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf12d8  ldstr    aStaticGridData// "/_static/_grid/DataSetControl.js"
0xf12dd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf12e2  ldarg.0
0xf12e3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf12e8  ldstr    aStaticCommonSc_61// "/_static/_common/scripts/Main.js"
0xf12ed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf12f2  ldarg.0
0xf12f3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf12f8  ldstr    aStaticCommonSc_62// "/_static/_common/scripts/MainControls.j"...
0xf12fd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf1302  ldarg.0
0xf1303  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1308  ldstr    aStaticCommonSc_2// "/_static/_common/scripts/CommandBarActi"...
0xf130d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf1312  ldarg.0
0xf1313  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1318  ldstr    aStaticCommonSc_8// "/_static/_common/scripts/RibbonActions."...
0xf131d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf1322  ldarg.0
0xf1323  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1328  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0xf132d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf1332  ldarg.0
0xf1333  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1338  ldstr    aStaticOobwebre// "/_static/oobwebresource/Ribbon_main_sys"...
0xf133d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf1342  ldarg.0
0xf1343  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1348  ldstr    aStaticOobwebre_1// "/_static/oobwebresource/Email_main_syst"...
0xf134d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf1352  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf1357  ldstr    a01_3// "{0}{1}"
0xf135c  ldc.i4.2
0xf135d  newarr   [mscorlib]System.Object
0xf1362  dup
0xf1363  ldc.i4.0
0xf1364  ldstr    aWebresource_0// "$webresource:"
0xf1369  stelem.ref
0xf136a  dup
0xf136b  ldc.i4.1
0xf136c  ldstr    aCcMscrmcontrol// "cc_MscrmControls.ActionCards.ActionCard"...
0xf1371  stelem.ref
0xf1372  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf1377  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf137c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf1381  stloc.0
0xf1382  ldarg.0
0xf1383  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1388  ldloc.0
0xf1389  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xf138e  ldarg.0
0xf138f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1394  ldstr    aStaticControls_0// "/_static/_controls/datetime/time.js"
0xf1399  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf139e  ldarg.0
0xf139f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf13a4  ldstr    aStaticControls// "/_static/_controls/datetime/date.js"
0xf13a9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf13ae  ldstr    aCommonWindowin_0// "/_common/windowinformation/windowinform"...
0xf13b3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf13b8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf13bd  stloc.1
0xf13be  ldloc.1
0xf13bf  ldc.i4.1
0xf13c0  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_UseCssLcid(bool)
0xf13c5  ldarg.0
0xf13c6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf13cb  ldloc.1
0xf13cc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0xf13d1  ldarg.0
0xf13d2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf13d7  ldstr    aStaticControls_1// "/_static/_controls/lookup/lookup.js"
0xf13dc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf13e1  ldarg.0
0xf13e2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf13e7  ldstr    aStaticFormsLoo_1// "/_static/_forms/lookupaddress.js"
0xf13ec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf13f1  ldarg.0
0xf13f2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf13f7  ldstr    aStaticControls_7// "/_static/_controls/FlyoutDialog/FlyoutD"...
0xf13fc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf1401  ldarg.0
0xf1402  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1407  ldstr    aControlsDplist// "/_controls/DPListControl/dynamicpropert"...
0xf140c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf1411  ldarg.0
0xf1412  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1417  ldstr    aControlsRefres_0// "/_controls/RefreshForm/flyoutdialog.css"...
0xf141c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf1421  ldarg.0
0xf1422  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1427  ldstr    aStaticGridGrid// "/_static/_grid/GridControl.js"
0xf142c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf1431  ldarg.0
0xf1432  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1437  ldstr    aStaticControls_58// "/_static/_controls/Pane/VisualizationPa"...
0xf143c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf1441  ldarg.0
0xf1442  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1447  ldstr    aStaticFormsHid// "/_static/_forms/hiddeninputbehavior.js"
0xf144c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xf1451  ldarg.0
0xf1452  call     instance void Microsoft.Crm.Application.Pages.Dialog.DialogPage::LoadCustomControlPropertyBagData()
0xf1457  ldstr    aWindowTrackclo_0// "window.trackClosures = 1;\r\n\t\t\t\t\t"...
0xf145c  stloc.2
0xf145d  ldarg.0
0xf145e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf1463  ldstr    aTrackclosures// "TrackClosures"
0xf1468  ldloc.2
0xf1469  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlock(string, string)
0xf146e  ret
```
