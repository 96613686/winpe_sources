# Microsoft.Crm.Controls.BasicHeader::ProcessControlType

- ea: `0xdc0`
- end: `0x1de7`
- name: `Microsoft.Crm.Controls.BasicHeader::ProcessControlType`
- size: `4135`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0xdc0`
- `0x2ef0`
- `0x3380`
- `0x38d0`
- `0x39f0`
- `0x40f0`
- `0x4100`
- `0x4120`
- `0x6ff0`

## string_xrefs

- `0x1070`: `LOCID_INCOM_TYPE_CAMP`
- `0x109e`: `LOCID_DELETE_WORKFLOW`
- `0x10a4`: `Grid_Action_Delete_Worflow`
- `0x10cc`: `LOCID_INCOM_TYPE_EMAIL`
- `0x1145`: `EmptyGridMessageBoundSubgridCreate`
- `0x11cf`: `Web.Grid.SelectAllKeyCommand`
- `0x141f`: `Grid.Common.Title.CheckBox.Unchecked`
- `0x1436`: `Grid.Common.Title.CheckBox.Checked`
- `0x1464`: `Grid.Common.Alt.SortedColumn.Down`
- `0x147b`: `Grid.Common.Alt.SortedColumn.Up`
- `0x17e8`: `LOCID_KNOWART_UPDATE_TITLE`
- `0x17ee`: `KnowledgeArticle_Update_Confirmation_DialogTitle`
- `0x17ff`: `LOCID_KNOWART_UPDATE_TEXT`
- `0x1805`: `KnowledgeArticle_Update_Confirmation_DialogText`
- `0x1816`: `LOCID_KNOWART_CREATEMAJOR_TITLE`
- `0x181c`: `KnowledgeArticle_CreateMajor_Confirmation_DialogTitle`
- `0x182d`: `LOCID_KNOWART_CREATEMAJOR_TEXT`
- `0x1833`: `KnowledgeArticle_CreateMajor_Confirmation_DialogText`
- `0x1844`: `LOCID_KNOWART_CREATEMINOR_TITLE`
- `0x184a`: `KnowledgeArticle_CreateMinor_Confirmation_DialogTitle`
- `0x185b`: `LOCID_KNOWART_CREATEMINOR_TEXT`
- `0x1861`: `KnowledgeArticle_CreateMinor_Confirmation_DialogText`
- `0x19b4`: `LOCID_KNOWART_NOTIFY_READONLY`
- `0x19ba`: `KnowledgeArticle_Notification_ReadOnly`
- `0x1b38`: `d:\dbs\sh\dccm2\1101_190851\cmd\4\src\Core\Application\web\Components\ui\BasicHeader.cs`
- `0x1b79`: `d:\dbs\sh\dccm2\1101_190851\cmd\4\src\Core\Application\web\Components\ui\BasicHeader.cs`
- `0x1c6e`: `LOCID_RELATEDINFO_TASKNOTREGOBJ`
- `0x1c74`: `TaskNotRegardingObjectForMiniCamp`
- `0x1c97`: `/_controls/CompositeControl/CompositeControl.css.aspx`
- `0x1cb4`: `/_common/styles/select.css.aspx`
- `0x1d5b`: `/_nav/taskbox.css.aspx`
- `0x1d7a`: `common.scripts.global.js.NotRecognizedObjectType`
- `0x1d8b`: `LOCID_XML_PROCESS_ERROR`
- `0x1d91`: `common.scripts.global.js.XmlProcessingError`
- `0x1da8`: `common.scripts.global.js.PopupBlockerError`

## pseudocode

```c

```

## disassembly

```asm
0xdc0  ldarg.0
0xdc1  call     instance void Microsoft.Crm.Controls.PageResourceManager::ProcessControlType()
0xdc6  ldarg.0
0xdc7  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType Microsoft.Crm.Controls.Header::get_Type()
0xdcc  ldc.i4   0x4000
0xdd1  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0xdd6  brfalse.s loc_DFA
0xdd8  ldarg.0
0xdd9  ldstr    aControlsContra// "/_controls/contractcal/contractcal.css."...
0xdde  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0xde3  ldarg.0
0xde4  ldstr    aLocidNoSelecti// "LOCID_NO_SELECTION"
0xde9  ldarg.0
0xdea  ldstr    aContractcalend// "ContractCalendar_No_Selection"
0xdef  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0xdf4  ldc.i4.0
0xdf5  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0xdfa  ldarg.0
0xdfb  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType Microsoft.Crm.Controls.Header::get_Type()
0xe00  ldc.i4   0x2000
0xe05  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0xe0a  brfalse.s loc_E50
0xe0c  ldarg.0
0xe0d  ldstr    aStaticControls_0// "/_static/_controls/articlefind/articlef"...
0xe12  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0xe17  ldarg.0
0xe18  ldstr    aTreeTreeCssAsp// "/_tree/tree.css.aspx"
0xe1d  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0xe22  ldarg.0
0xe23  ldstr    aLocidTreePlus// "LOCID_TREE_PLUS"
0xe28  ldarg.0
0xe29  ldstr    aTreeAltExpand// "Tree.Alt.Expand"
0xe2e  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0xe33  ldc.i4.0
0xe34  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0xe39  ldarg.0
0xe3a  ldstr    aLocidTreeMinus// "LOCID_TREE_MINUS"
0xe3f  ldarg.0
0xe40  ldstr    aTreeAltCollaps// "Tree.Alt.Collapse"
0xe45  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0xe4a  ldc.i4.0
0xe4b  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0xe50  ldarg.0
0xe51  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType Microsoft.Crm.Controls.Header::get_Type()
0xe56  ldc.i4.s 0x20
0xe58  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0xe5d  brfalse.s loc_EAB
0xe5f  ldarg.0
0xe60  ldstr    aStaticControls_1// "/_static/_controls/lookup/lookup.js"
0xe65  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0xe6a  ldarg.0
0xe6b  ldstr    aStaticControls_2// "/_static/_controls/popupmenu/popupmenu."...
0xe70  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0xe75  ldarg.0
0xe76  ldstr    aLocidCloseButt// "LOCID_CLOSE_BUTTON_LABEL"
0xe7b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe80  ldstr    aButtonLabelClo// "Button_Label_Close"
0xe85  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe8a  ldc.i4.0
0xe8b  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0xe90  ldarg.0
0xe91  ldstr    aLocidPopupMenu// "LOCID_POPUP_MENU_LABEL"
0xe96  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe9b  ldstr    aPopupMenuTitle// "Popup_Menu_Title_Format"
0xea0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xea5  ldc.i4.0
0xea6  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0xeab  ldarg.0
0xeac  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType Microsoft.Crm.Controls.Header::get_Type()
0xeb1  ldc.i4.s 0x40
0xeb3  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0xeb8  brfalse.s loc_ED0
0xeba  ldarg.0
0xebb  ldstr    aStaticControls_3// "/_static/_controls/datetime/date.js"
0xec0  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0xec5  ldarg.0
0xec6  ldstr    aStaticControls_4// "/_static/_controls/datetime/time.js"
0xecb  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0xed0  ldarg.0
0xed1  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType Microsoft.Crm.Controls.Header::get_Type()
0xed6  ldc.i4.2
0xed7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0xedc  brfalse.s loc_EE9
0xede  ldarg.0
0xedf  ldstr    aNavTabsCssAspx// "/_nav/tabs.css.aspx"
0xee4  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0xee9  ldarg.0
0xeea  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType Microsoft.Crm.Controls.Header::get_Type()
0xeef  ldc.i4   0x100
0xef4  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0xef9  brfalse.s loc_F06
0xefb  ldarg.0
0xefc  ldstr    aStaticFormsFor// "/_static/_forms/form.js"
0xf01  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0xf06  ldarg.0
0xf07  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType Microsoft.Crm.Controls.Header::get_Type()
0xf0c  ldc.i4.s 0x10
0xf0e  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0xf13  brfalse  loc_1B96
0xf18  ldarg.0
0xf19  ldstr    aStaticControls_1// "/_static/_controls/lookup/lookup.js"
0xf1e  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0xf23  ldarg.0
0xf24  ldstr    aStaticGridActi// "/_static/_grid/action.js"
0xf29  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0xf2e  ldarg.0
0xf2f  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0xf34  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0xf39  ldarg.0
0xf3a  ldstr    aGridAppgridCss// "/_grid/appgrid.css.aspx"
0xf3f  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0xf44  ldarg.0
0xf45  ldstr    aLocidCustmsgTo// "LOCID_CUSTMSG_TOOMANY_REC"
0xf4a  ldarg.0
0xf4b  ldstr    aGridActionTooM// "Grid_Action_Too_Many_Custom_Messages_Se"...
0xf50  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0xf55  ldc.i4.0
0xf56  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0xf5b  ldarg.0
0xf5c  ldstr    aLocidMergeToom// "LOCID_MERGE_TOOMANY_RECORDS"
0xf61  ldarg.0
0xf62  ldstr    aWebGridMergeAc// "Web._grid.merge.action.js_359"
0xf67  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0xf6c  ldc.i4.0
0xf6d  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0xf72  ldarg.0
0xf73  ldstr    aLocidMergeCase// "LOCID_MERGE_CASE_TOOMANY_RECORDS"
0xf78  ldarg.0
0xf79  ldstr    aMergerecordsCa// "MergeRecords_Cases_Maxlimit"
0xf7e  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0xf83  ldc.i4.0
0xf84  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0xf89  ldarg.0
0xf8a  ldstr    aLocidAsscoToom// "LOCID_ASSCO_TOOMANY_RECORDS"
0xf8f  ldarg.0
0xf90  ldstr    aErrorMessage0x// "Error_Message_0x8003f454"
0xf95  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0xf9a  ldc.i4.0
0xf9b  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0xfa0  ldarg.0
0xfa1  ldstr    aLocidMergeLess// "LOCID_MERGE_LESS_RECORDS"
0xfa6  ldarg.0
0xfa7  ldstr    aWebGridMergeAc_0// "Web._grid.merge.action.js_360"
0xfac  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0xfb1  ldc.i4.0
0xfb2  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0xfb7  ldarg.0
0xfb8  ldstr    aLocidAsscoLess// "LOCID_ASSCO_LESS_RECORDS"
0xfbd  ldarg.0
0xfbe  ldstr    aWebGridAsscoAc// "Web._grid.assco.action.js_360"
0xfc3  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0xfc8  ldc.i4.0
0xfc9  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0xfce  ldarg.0
0xfcf  ldstr    aLocidMrgeDupsT// "LOCID_MRGE_DUPS_TOOMANY_RCRDS"
0xfd4  ldarg.0
0xfd5  ldstr    aWebGridMergedu// "Web._grid.mergeduplicates.action.js"
0xfda  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0xfdf  ldc.i4.0
0xfe0  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0xfe5  ldarg.0
0xfe6  ldstr    aLocidActionNoi// "LOCID_ACTION_NOITEMSELECTED"
0xfeb  ldarg.0
0xfec  ldstr    aErrorMessageAc// "Error_Message_Action_NoItemSelected"
0xff1  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0xff6  ldc.i4.0
0xff7  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0xffc  ldarg.0
0xffd  ldstr    aLocidEmailNore// "LOCID_EMAIL_NORECORDS_MSG"
0x1002  ldarg.0
0x1003  ldstr    aWebGridActionJ// "Web._grid.action.js_451"
0x1008  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x100d  ldc.i4.0
0x100e  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1013  ldarg.0
0x1014  ldstr    aLocidRelations// "LOCID_RELATIONSHIPS_TOO_MANY"
0x1019  ldarg.0
0x101a  ldstr    aGridActionRela// "Grid_Action_Relationship_Too_Many_Recor"...
0x101f  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1024  ldc.i4.0
0x1025  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x102a  ldarg.0
0x102b  ldstr    aLocidUsersTooM// "LOCID_USERS_TOO_MANY"
0x1030  ldarg.0
0x1031  ldstr    aGridActionUser// "Grid_Action_User_Too_Many_Records_Selec"...
0x1036  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x103b  ldc.i4.0
0x103c  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1041  ldarg.0
0x1042  ldstr    aLocidRolesTooM// "LOCID_ROLES_TOO_MANY"
0x1047  ldarg.0
0x1048  ldstr    aGridActionRole// "Grid_Action_Role_Too_Many_Records_Selec"...
0x104d  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1052  ldc.i4.0
0x1053  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1058  ldarg.0
0x1059  ldstr    aLocidHeterogen// "LOCID_HETEROGENOUS_TYPES"
0x105e  ldarg.0
0x105f  ldstr    aGridApplyRuleH// "Grid_Apply_Rule_Heterogenous_Type_Recor"...
0x1064  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1069  ldc.i4.0
0x106a  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x106f  ldarg.0
0x1070  ldstr    aLocidIncomType// "LOCID_INCOM_TYPE_CAMP"
0x1075  ldarg.0
0x1076  ldstr    aGridApplyRuleS// "Grid_Apply_Rule_Selected_Records"
0x107b  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1080  ldc.i4.0
0x1081  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1086  ldarg.0
0x1087  ldstr    aLocidDeactivat// "LOCID_DEACTIVATE_WORKFLOW"
0x108c  ldarg.0
0x108d  ldstr    aGridActionDeac// "Grid_Action_Deactivate_Worflow"
0x1092  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1097  ldc.i4.0
0x1098  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x109d  ldarg.0
0x109e  ldstr    aLocidDeleteWor// "LOCID_DELETE_WORKFLOW"
0x10a3  ldarg.0
0x10a4  ldstr    aGridActionDele// "Grid_Action_Delete_Worflow"
0x10a9  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x10ae  ldc.i4.0
0x10af  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x10b4  ldarg.0
0x10b5  ldstr    aLocidActivateW// "LOCID_ACTIVATE_WORKFLOW"
0x10ba  ldarg.0
0x10bb  ldstr    aGridActionActi// "Grid_Action_Activate_Worflow"
0x10c0  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x10c5  ldc.i4.0
0x10c6  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x10cb  ldarg.0
0x10cc  ldstr    aLocidIncomType_0// "LOCID_INCOM_TYPE_EMAIL"
0x10d1  ldarg.0
0x10d2  ldstr    aGridApplyRuleS_0// "Grid_Apply_Rule_Selected_Emails"
0x10d7  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x10dc  ldc.i4.0
0x10dd  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x10e2  ldarg.0
0x10e3  ldstr    aLocidSocialAct// "LOCID_SOCIAL_ACTIVITY_ACTIONERR"
0x10e8  ldarg.0
0x10e9  ldstr    aGridApplyRuleS_1// "Grid_Apply_Rule_Social_Activity_Type_Re"...
0x10ee  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x10f3  ldc.i4.0
0x10f4  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x10f9  ldarg.0
0x10fa  ldstr    aLocidHetrogene// "LOCID_HETROGENEOUS_ACTIVITY"
0x10ff  ldarg.0
0x1100  ldstr    aGridApplyRuleH_0// "Grid_Apply_Rule_Heterogenous_Activity_T"...
0x1105  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x110a  ldc.i4.0
0x110b  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1110  ldarg.0
0x1111  ldstr    aLocidHetrogene_0// "LOCID_HETROGENEOUS_DATASOURCE"
0x1116  ldarg.0
0x1117  ldstr    aGridApplyRuleH_1// "Grid_Apply_Rule_Heterogenous_DataSource"...
0x111c  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1121  ldc.i4.0
0x1122  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1127  ldarg.0
0x1128  ldstr    aLocidRefreshGr// "LOCID_REFRESH_GRID_CANCELLED"
0x112d  ldarg.0
0x112e  ldstr    aGridRefreshDat// "Grid.Refresh.Data.Cancelled"
0x1133  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1138  ldc.i4.0
0x1139  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x113e  ldarg.0
0x113f  ldstr    aLocidEmptyGrid// "LOCID_EMPTY_GRID_MESSAGE"
0x1144  ldarg.0
0x1145  ldstr    aEmptygridmessa// "EmptyGridMessageBoundSubgridCreate"
0x114a  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x114f  ldc.i4.0
0x1150  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1155  ldarg.0
0x1156  ldstr    aLocidLoadingGr// "LOCID_LOADING_GRID_FAILED"
0x115b  ldarg.0
0x115c  ldstr    aGridLoadingDat// "Grid.Loading.Data.Failed"
0x1161  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1166  ldc.i4.0
0x1167  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x116c  ldarg.0
0x116d  ldstr    aLocidWindowTit// "LOCID_WINDOW_TITLE_FORMAT"
0x1172  ldarg.0
0x1173  ldstr    aGridSearchView// "Grid.Search.ViewTitle.Format"
0x1178  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x117d  ldc.i4.0
0x117e  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x1183  ldarg.0
0x1184  ldstr    aLocidGridTooMa// "LOCID_GRID_TOO_MANY_RECORDS"
0x1189  ldarg.0
0x118a  ldstr    aLocidGridTooMa// "LOCID_GRID_TOO_MANY_RECORDS"
0x118f  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x1194  ldc.i4.0
0x1195  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x119a  ldarg.0
0x119b  ldstr    aLocidGridTooMa_0// "LOCID_GRID_TOO_MANY_RECORDS_1"
0x11a0  ldarg.0
0x11a1  ldstr    aLocidGridTooMa_0// "LOCID_GRID_TOO_MANY_RECORDS_1"
0x11a6  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x11ab  ldc.i4.0
0x11ac  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
  ... truncated ...
```
