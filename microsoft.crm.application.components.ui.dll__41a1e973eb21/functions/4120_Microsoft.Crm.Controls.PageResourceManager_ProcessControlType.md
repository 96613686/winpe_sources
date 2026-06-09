# Microsoft.Crm.Controls.PageResourceManager::ProcessControlType

- ea: `0x4120`
- end: `0x4c1f`
- name: `Microsoft.Crm.Controls.PageResourceManager::ProcessControlType`
- size: `2815`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xdc0`
- `0x3e90`

## callees

- `0x24a0`
- `0x24c0`
- `0x3380`
- `0x35b0`
- `0x38d0`
- `0x39f0`
- `0x40f0`
- `0x4100`
- `0x4120`

## string_xrefs

- `0x4473`: `LOCID_INCOM_TYPE_CAMP`
- `0x4417`: `LOCID_DELETE_WORKFLOW`
- `0x441d`: `Grid_Action_Delete_Worflow`
- `0x448a`: `LOCID_INCOM_TYPE_EMAIL`
- `0x4503`: `EmptyGridMessageBoundSubgridCreate`
- `0x45e9`: `Web.Grid.SelectAllKeyCommand`
- `0x4839`: `Grid.Common.Title.CheckBox.Unchecked`
- `0x4850`: `Grid.Common.Title.CheckBox.Checked`
- `0x487e`: `Grid.Common.Alt.SortedColumn.Down`
- `0x4895`: `Grid.Common.Alt.SortedColumn.Up`
- `0x4a3f`: `LOCID_RELATEDINFO_TASKNOTREGOBJ`
- `0x4a45`: `TaskNotRegardingObjectForMiniCamp`
- `0x4a68`: `/_controls/CompositeControl/CompositeControl.css.aspx`
- `0x4a85`: `/_common/styles/select.css.aspx`
- `0x4b37`: `/_nav/taskbox.css.aspx`
- `0x4b59`: `common.scripts.global.js.NotRecognizedObjectType`
- `0x4b6a`: `LOCID_XML_PROCESS_ERROR`
- `0x4b70`: `common.scripts.global.js.XmlProcessingError`
- `0x4b87`: `common.scripts.global.js.PopupBlockerError`
- `0x4121`: `LOCID_FIELD_SCREENREADER_LABEL`
- `0x412b`: `FormFields_ScreenReader_Label`
- `0x4146`: `Lookup_Search_ScreenReader_Label`
- `0x4161`: `NonEmpty_Lookup_Control_ScreenReader_Label`
- `0x417c`: `Lookup_Control_ScreenReader_Label`
- `0x4197`: `DateTime_Control_ScreenReader_Label`
- `0x4204`: `/_common/styles/KB.css.aspx`
- `0x438d`: `LOCID_DELETE_CONFIRM_ONE`
- `0x4393`: `MenuItem_Delete_Equipment_Confirm_Part1`
- `0x43a4`: `LOCID_DELETE_CONFIRM_TWO`
- `0x43aa`: `MenuItem_Delete_Equipment_Confirm_Part2`
- `0x451a`: `EmptyGridMessageBoundSubgridCreateRefresh`
- `0x4bfc`: `/_static/_common/scripts/RibbonActions.js`

## pseudocode

```c

```

## disassembly

```asm
0x4120  ldarg.0
0x4121  ldstr    aLocidFieldScre// "LOCID_FIELD_SCREENREADER_LABEL"
0x4126  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x412b  ldstr    aFormfieldsScre// "FormFields_ScreenReader_Label"
0x4130  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4135  ldc.i4.0
0x4136  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x413b  ldarg.0
0x413c  ldstr    aLocidLookupSea// "LOCID_LOOKUP_SEARCH_LABEL"
0x4141  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4146  ldstr    aLookupSearchSc// "Lookup_Search_ScreenReader_Label"
0x414b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4150  ldc.i4.0
0x4151  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x4156  ldarg.0
0x4157  ldstr    aLocidNonemptyL// "LOCID_NONEMPTY_LOOKUP_LABEL"
0x415c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4161  ldstr    aNonemptyLookup// "NonEmpty_Lookup_Control_ScreenReader_La"...
0x4166  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x416b  ldc.i4.0
0x416c  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x4171  ldarg.0
0x4172  ldstr    aLocidLookupCon// "LOCID_LOOKUP_CONTROL_LABEL"
0x4177  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x417c  ldstr    aLookupControlS// "Lookup_Control_ScreenReader_Label"
0x4181  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4186  ldc.i4.0
0x4187  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x418c  ldarg.0
0x418d  ldstr    aLocidDatetimeC// "LOCID_DATETIME_CONTROL_FORMAT"
0x4192  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4197  ldstr    aDatetimeContro// "DateTime_Control_ScreenReader_Label"
0x419c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x41a1  ldc.i4.0
0x41a2  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x41a7  ldarg.0
0x41a8  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType Microsoft.Crm.Controls.PageResourceManager::_type
0x41ad  ldc.i4   0x4000
0x41b2  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x41b7  brfalse.s loc_41DB
0x41b9  ldarg.0
0x41ba  ldstr    aControlsContra// "/_controls/contractcal/contractcal.css."...
0x41bf  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x41c4  ldarg.0
0x41c5  ldstr    aLocidNoSelecti// "LOCID_NO_SELECTION"
0x41ca  ldarg.0
0x41cb  ldstr    aContractcalend// "ContractCalendar_No_Selection"
0x41d0  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x41d5  ldc.i4.0
0x41d6  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x41db  ldarg.0
0x41dc  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType Microsoft.Crm.Controls.PageResourceManager::_type
0x41e1  ldc.i4   0x2000
0x41e6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x41eb  brfalse.s loc_423C
0x41ed  ldarg.0
0x41ee  ldstr    aStaticControls_0// "/_static/_controls/articlefind/articlef"...
0x41f3  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x41f8  ldarg.0
0x41f9  ldstr    aTreeTreeCssAsp// "/_tree/tree.css.aspx"
0x41fe  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x4203  ldarg.0
0x4204  ldstr    aCommonStylesKb// "/_common/styles/KB.css.aspx"
0x4209  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x420e  ldarg.0
0x420f  ldstr    aLocidTreePlus// "LOCID_TREE_PLUS"
0x4214  ldarg.0
0x4215  ldstr    aTreeAltExpand// "Tree.Alt.Expand"
0x421a  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x421f  ldc.i4.0
0x4220  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x4225  ldarg.0
0x4226  ldstr    aLocidTreeMinus// "LOCID_TREE_MINUS"
0x422b  ldarg.0
0x422c  ldstr    aTreeAltCollaps// "Tree.Alt.Collapse"
0x4231  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x4236  ldc.i4.0
0x4237  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x423c  ldarg.0
0x423d  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType Microsoft.Crm.Controls.PageResourceManager::_type
0x4242  ldc.i4.s 0x20
0x4244  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x4249  brfalse.s loc_4297
0x424b  ldarg.0
0x424c  ldstr    aStaticControls_1// "/_static/_controls/lookup/lookup.js"
0x4251  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x4256  ldarg.0
0x4257  ldstr    aStaticControls_2// "/_static/_controls/popupmenu/popupmenu."...
0x425c  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x4261  ldarg.0
0x4262  ldstr    aLocidCloseButt// "LOCID_CLOSE_BUTTON_LABEL"
0x4267  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x426c  ldstr    aButtonLabelClo// "Button_Label_Close"
0x4271  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4276  ldc.i4.0
0x4277  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x427c  ldarg.0
0x427d  ldstr    aLocidPopupMenu// "LOCID_POPUP_MENU_LABEL"
0x4282  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4287  ldstr    aPopupMenuTitle// "Popup_Menu_Title_Format"
0x428c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4291  ldc.i4.0
0x4292  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x4297  ldarg.0
0x4298  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType Microsoft.Crm.Controls.PageResourceManager::_type
0x429d  ldc.i4.s 0x40
0x429f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x42a4  brfalse.s loc_42BC
0x42a6  ldarg.0
0x42a7  ldstr    aStaticControls_3// "/_static/_controls/datetime/date.js"
0x42ac  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x42b1  ldarg.0
0x42b2  ldstr    aStaticControls_4// "/_static/_controls/datetime/time.js"
0x42b7  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x42bc  ldarg.0
0x42bd  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType Microsoft.Crm.Controls.PageResourceManager::_type
0x42c2  ldc.i4.2
0x42c3  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x42c8  brfalse.s loc_42D5
0x42ca  ldarg.0
0x42cb  ldstr    aNavTabsCssAspx// "/_nav/tabs.css.aspx"
0x42d0  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x42d5  ldarg.0
0x42d6  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType Microsoft.Crm.Controls.PageResourceManager::_type
0x42db  ldc.i4   0x100
0x42e0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x42e5  brfalse.s loc_42F2
0x42e7  ldarg.0
0x42e8  ldstr    aStaticFormsFor// "/_static/_forms/form.js"
0x42ed  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x42f2  ldarg.0
0x42f3  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.ControlType Microsoft.Crm.Controls.PageResourceManager::_type
0x42f8  ldc.i4.s 0x10
0x42fa  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.General::CheckBit(unsigned int32, unsigned int32)
0x42ff  brfalse  loc_4967
0x4304  ldarg.0
0x4305  ldstr    aStaticControls_1// "/_static/_controls/lookup/lookup.js"
0x430a  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x430f  ldarg.0
0x4310  ldstr    aStaticGridActi// "/_static/_grid/action.js"
0x4315  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x431a  ldarg.0
0x431b  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0x4320  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x4325  ldarg.0
0x4326  ldstr    aGridAppgridCss// "/_grid/appgrid.css.aspx"
0x432b  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string file)
0x4330  ldarg.0
0x4331  ldstr    aLocidCustmsgTo// "LOCID_CUSTMSG_TOOMANY_REC"
0x4336  ldarg.0
0x4337  ldstr    aGridActionTooM// "Grid_Action_Too_Many_Custom_Messages_Se"...
0x433c  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x4341  ldc.i4.0
0x4342  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x4347  ldarg.0
0x4348  ldstr    aLocidMergeToom// "LOCID_MERGE_TOOMANY_RECORDS"
0x434d  ldarg.0
0x434e  ldstr    aWebGridMergeAc// "Web._grid.merge.action.js_359"
0x4353  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x4358  ldc.i4.0
0x4359  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x435e  ldarg.0
0x435f  ldstr    aLocidMrgeDupsT// "LOCID_MRGE_DUPS_TOOMANY_RCRDS"
0x4364  ldarg.0
0x4365  ldstr    aWebGridMergedu// "Web._grid.mergeduplicates.action.js"
0x436a  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x436f  ldc.i4.0
0x4370  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x4375  ldarg.0
0x4376  ldstr    aLocidActionNoi// "LOCID_ACTION_NOITEMSELECTED"
0x437b  ldarg.0
0x437c  ldstr    aErrorMessageAc// "Error_Message_Action_NoItemSelected"
0x4381  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x4386  ldc.i4.0
0x4387  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x438c  ldarg.0
0x438d  ldstr    aLocidDeleteCon// "LOCID_DELETE_CONFIRM_ONE"
0x4392  ldarg.0
0x4393  ldstr    aMenuitemDelete// "MenuItem_Delete_Equipment_Confirm_Part1"
0x4398  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x439d  ldc.i4.0
0x439e  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x43a3  ldarg.0
0x43a4  ldstr    aLocidDeleteCon_0// "LOCID_DELETE_CONFIRM_TWO"
0x43a9  ldarg.0
0x43aa  ldstr    aMenuitemDelete_0// "MenuItem_Delete_Equipment_Confirm_Part2"
0x43af  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x43b4  ldc.i4.0
0x43b5  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x43ba  ldarg.0
0x43bb  ldstr    aLocidEmailNore// "LOCID_EMAIL_NORECORDS_MSG"
0x43c0  ldarg.0
0x43c1  ldstr    aWebGridActionJ// "Web._grid.action.js_451"
0x43c6  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x43cb  ldc.i4.0
0x43cc  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x43d1  ldarg.0
0x43d2  ldstr    aLocidRelations// "LOCID_RELATIONSHIPS_TOO_MANY"
0x43d7  ldarg.0
0x43d8  ldstr    aGridActionRela// "Grid_Action_Relationship_Too_Many_Recor"...
0x43dd  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x43e2  ldc.i4.0
0x43e3  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x43e8  ldarg.0
0x43e9  ldstr    aLocidUsersTooM// "LOCID_USERS_TOO_MANY"
0x43ee  ldarg.0
0x43ef  ldstr    aGridActionUser// "Grid_Action_User_Too_Many_Records_Selec"...
0x43f4  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x43f9  ldc.i4.0
0x43fa  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x43ff  ldarg.0
0x4400  ldstr    aLocidDeactivat// "LOCID_DEACTIVATE_WORKFLOW"
0x4405  ldarg.0
0x4406  ldstr    aGridActionDeac// "Grid_Action_Deactivate_Worflow"
0x440b  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x4410  ldc.i4.0
0x4411  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x4416  ldarg.0
0x4417  ldstr    aLocidDeleteWor// "LOCID_DELETE_WORKFLOW"
0x441c  ldarg.0
0x441d  ldstr    aGridActionDele// "Grid_Action_Delete_Worflow"
0x4422  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x4427  ldc.i4.0
0x4428  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x442d  ldarg.0
0x442e  ldstr    aLocidActivateW// "LOCID_ACTIVATE_WORKFLOW"
0x4433  ldarg.0
0x4434  ldstr    aGridActionActi// "Grid_Action_Activate_Worflow"
0x4439  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x443e  ldc.i4.0
0x443f  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x4444  ldarg.0
0x4445  ldstr    aLocidRolesTooM// "LOCID_ROLES_TOO_MANY"
0x444a  ldarg.0
0x444b  ldstr    aGridActionRole// "Grid_Action_Role_Too_Many_Records_Selec"...
0x4450  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x4455  ldc.i4.0
0x4456  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x445b  ldarg.0
0x445c  ldstr    aLocidHeterogen// "LOCID_HETEROGENOUS_TYPES"
0x4461  ldarg.0
0x4462  ldstr    aGridApplyRuleH// "Grid_Apply_Rule_Heterogenous_Type_Recor"...
0x4467  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x446c  ldc.i4.0
0x446d  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x4472  ldarg.0
0x4473  ldstr    aLocidIncomType// "LOCID_INCOM_TYPE_CAMP"
0x4478  ldarg.0
0x4479  ldstr    aGridApplyRuleS// "Grid_Apply_Rule_Selected_Records"
0x447e  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x4483  ldc.i4.0
0x4484  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x4489  ldarg.0
0x448a  ldstr    aLocidIncomType_0// "LOCID_INCOM_TYPE_EMAIL"
0x448f  ldarg.0
0x4490  ldstr    aGridApplyRuleS_0// "Grid_Apply_Rule_Selected_Emails"
0x4495  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x449a  ldc.i4.0
0x449b  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x44a0  ldarg.0
0x44a1  ldstr    aLocidSocialAct// "LOCID_SOCIAL_ACTIVITY_ACTIONERR"
0x44a6  ldarg.0
0x44a7  ldstr    aGridApplyRuleS_1// "Grid_Apply_Rule_Social_Activity_Type_Re"...
0x44ac  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x44b1  ldc.i4.0
0x44b2  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x44b7  ldarg.0
0x44b8  ldstr    aLocidHetrogene// "LOCID_HETROGENEOUS_ACTIVITY"
0x44bd  ldarg.0
0x44be  ldstr    aGridApplyRuleH_0// "Grid_Apply_Rule_Heterogenous_Activity_T"...
0x44c3  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x44c8  ldc.i4.0
0x44c9  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x44ce  ldarg.0
0x44cf  ldstr    aLocidHetrogene_0// "LOCID_HETROGENEOUS_DATASOURCE"
0x44d4  ldarg.0
0x44d5  ldstr    aGridApplyRuleH_1// "Grid_Apply_Rule_Heterogenous_DataSource"...
0x44da  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x44df  ldc.i4.0
0x44e0  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x44e5  ldarg.0
0x44e6  ldstr    aLocidRefreshGr// "LOCID_REFRESH_GRID_CANCELLED"
0x44eb  ldarg.0
0x44ec  ldstr    aGridRefreshDat// "Grid.Refresh.Data.Cancelled"
0x44f1  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x44f6  ldc.i4.0
0x44f7  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x44fc  ldarg.0
0x44fd  ldstr    aLocidEmptyGrid// "LOCID_EMPTY_GRID_MESSAGE"
0x4502  ldarg.0
0x4503  ldstr    aEmptygridmessa// "EmptyGridMessageBoundSubgridCreate"
0x4508  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x450d  ldc.i4.0
0x450e  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x4513  ldarg.0
0x4514  ldstr    aLocidEmptyGrid_0// "LOCID_EMPTY_GRID_MESSAGE_REFRESH"
0x4519  ldarg.0
0x451a  ldstr    aEmptygridmessa_0// "EmptyGridMessageBoundSubgridCreateRefre"...
0x451f  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x4524  ldc.i4.0
  ... truncated ...
```
