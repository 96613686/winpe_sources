# Microsoft.Crm.Application.ProcessControl.Configuration.BpfConfigurator::SetResourceVars

- ea: `0x4b100`
- end: `0x4b98a`
- name: `Microsoft.Crm.Application.ProcessControl.Configuration.BpfConfigurator::SetResourceVars`
- size: `2186`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4b0a0`

## callees

- `0x4aee0`
- `0x4b990`
- `0x4b9b0`
- `0x4b9c0`
- `0x4ba10`

## string_xrefs

- `0x4b110`: `ProcessControl.Configurator.NewStage`
- `0x4b130`: `ProcessControl.Configurator.NewPage`
- `0x4b150`: `ProcessControl.Configurator.NewStep`
- `0x4b170`: `ProcessControl.Configurator.ShowFields`
- `0x4b190`: `ProcessControl.Configurator.NewField`
- `0x4b1b0`: `ProcessControl.Configurator.Field`
- `0x4b1d0`: `ProcessControl.Configurator.Stage.Title.InsertStage`
- `0x4b1f0`: `ProcessControl.Configurator.Stage.Title.InsertStageAfterBranch`
- `0x4b210`: `ProcessControl.Configurator.Stage.Title.InsertPage`
- `0x4b230`: `ProcessControl.Configurator.Stage.Title.InsertPageAfterBranch`
- `0x4b250`: `ProcessControl.Configurator.Stage.Title.branch`
- `0x4b270`: `ProcessControl.Configurator.AddStepTitle`
- `0x4b290`: `ProcessControl.Configurator.Stage.Title.StageName`
- `0x4b2b0`: `ProcessControl.Configurator.Stage.Title.Entity`
- `0x4b2d0`: `ProcessControl.Configurator.Stage.Title.stageCategory`
- `0x4b2f0`: `ProcessControl.Configurator.Stage.Title.StepName`
- `0x4b310`: `ProcessControl.Configurator.Stage.Title.Value`
- `0x4b330`: `ProcessControl.Configurator.Stage.Title.required`
- `0x4b350`: `ProcessControl.Configurator.Stage.Title.StageUniqueName`
- `0x4b370`: `ProcessControl.Configurator.Stage.Title.PageName`
- `0x4b390`: `ProcessControl.Configurator.Stage.Title.PageStepNewLabel`
- `0x4b3b0`: `ProcessControl.Configurator.Stage.Title.PageStepLabel`
- `0x4b3d0`: `ProcessControl.Configurator.Stage.Title.PageStepSource`
- `0x4b3f0`: `ProcessControl.Configurator.Stage.Title.PageStepField`
- `0x4b410`: `ProcessControl.Configurator.Save.Heading`
- `0x4b430`: `ProcessControl.Configurator.Save.Message`
- `0x4b450`: `ProcessControl.Configurator.SaveError`
- `0x4b470`: `ProcessControl.Configurator.ErrorHeading`
- `0x4b490`: `ProcessControl.Configurator.ErrorBackMessage`
- `0x4b4b0`: `ProcessControl.Configurator.ErrorBackLinkText`
- `0x4b4d0`: `ProcessControl.Configurator.ErrorContactAdmin`
- `0x4b510`: `ProcessControl.Configurator.ErrorContactAdmin`
- `0x4b4f0`: `ProcessControl.Configurator.ErrorCloseWarning`
- `0x4b530`: `ProcessControl.Configurator.ErrorCloseWarning`
- `0x4b550`: `ProcessControl.Configurator.ErrorCloseButtonText`
- `0x4b570`: `ProcessControl.Configurator.ErrorBackButtonText`
- `0x4b590`: `ProcessControl.Configurator.CloseWarningIconAltText`
- `0x4b5b0`: `ProcessControl.Configurator.SavingconAltText`
- `0x4b5d0`: `ProcessControl.Configurator.SavingconAltText`
- `0x4b5e6`: `LOCID_PROCESS_MOVE`
- `0x4b5f0`: `ProcessControl.Configurator.Move`
- `0x4b606`: `LOCID_PROCESS_MOVE_UP`
- `0x4b610`: `ProcessControl.Configurator.MoveUp`
- `0x4b626`: `LOCID_PROCESS_MOVE_DOWN`
- `0x4b630`: `ProcessControl.Configurator.MoveDown`
- `0x4b650`: `ProcessControl.Configurator.Unsaved`
- `0x4b666`: `LOCID_PROCESS_CONFIRMDELETESTAGE`
- `0x4b670`: `ProcessControl.Configurator.ConfirmDeleteStage`
- `0x4b686`: `LOCID_PROCESS_DELETESTAGE`
- `0x4b690`: `ProcessControl.Configurator.DeleteStage`
- `0x4b6b0`: `ProcessControl.Configurator.BranchCondition`
- `0x4b6c6`: `LOCID_PROCESS_DELETESTEP`
- `0x4b6d0`: `ProcessControl.Configurator.DeleteStep`
- `0x4b6f0`: `ProcessControl.Configurator.RequiredStep`
- `0x4b710`: `ProcessControl.Configurator.AddEntityTitle`
- `0x4b730`: `ProcessControl.Configurator.AddEntityTooltip`
- `0x4b746`: `LOCID_PROCESS_REMOVEENTITY`
- `0x4b750`: `ProcessControl.Configurator.RemoveEntityTitle`
- `0x4b770`: `ProcessControl.Configurator.CloseLoopTitle`
- `0x4b790`: `ProcessControl.Configurator.CloseLoopTooltip`
- `0x4b7b0`: `ProcessControl.Configurator.CloseLoopIndicator`
- `0x4b7d0`: `ProcessControl.Configurator.Options`
- `0x4b7f0`: `ProcessControl.Configurator.NoRelatedEntities`
- `0x4b806`: `LOCID_PROCESS_ALREADYCLOSED`
- `0x4b810`: `ProcessControl.Configurator.ProcessAlreadyClosed`
- `0x4b830`: `ProcessControl.Configurator.MaxEntitiesReached`
- `0x4b850`: `ProcessControl.Configurator.FieldMustBeSelected`
- `0x4b870`: `ProcessControl.Configurator.Stage.Title.StageRelationship`
- `0x4b890`: `ProcessControl.Configurator.Stage.SelectRelationships`
- `0x4b8b0`: `ProcessControl.Configurator.Stage.SelectRelationships.Tooltip`
- `0x4b8d0`: `ProcessControl.Configurator.Stage.SelectRelationships.Warning`
- `0x4b8f0`: `ProcessControl.Configurator.Page.ControlStep.SectionLabel`
- `0x4b910`: `ProcessControl.Configurator.Page.ControlStep.Label`
- `0x4b926`: `_Process_JsonData`
- `0x4b96d`: `_OverwriteOnSave`

## pseudocode

```c

```

## disassembly

```asm
0x4b100  ldarg.0
0x4b101  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b106  ldstr    aLocidProcessNe// "LOCID_PROCESS_NEWSTAGETEXTKEY"
0x4b10b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b110  ldstr    aProcesscontrol_1// "ProcessControl.Configurator.NewStage"
0x4b115  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b11a  ldc.i4.0
0x4b11b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b120  ldarg.0
0x4b121  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b126  ldstr    aLocidProcessNe_0// "LOCID_PROCESS_NEWPAGETEXTKEY"
0x4b12b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b130  ldstr    aProcesscontrol_2// "ProcessControl.Configurator.NewPage"
0x4b135  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b13a  ldc.i4.0
0x4b13b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b140  ldarg.0
0x4b141  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b146  ldstr    aLocidProcessNe_1// "LOCID_PROCESS_NEWSTEPTEXTKEY"
0x4b14b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b150  ldstr    aProcesscontrol_3// "ProcessControl.Configurator.NewStep"
0x4b155  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b15a  ldc.i4.0
0x4b15b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b160  ldarg.0
0x4b161  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b166  ldstr    aLocidProcessSh// "LOCID_PROCESS_SHOWFIELDS"
0x4b16b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b170  ldstr    aProcesscontrol_4// "ProcessControl.Configurator.ShowFields"
0x4b175  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b17a  ldc.i4.0
0x4b17b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b180  ldarg.0
0x4b181  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b186  ldstr    aLocidProcessNe_2// "LOCID_PROCESS_NEWFIELDTEXTKEY"
0x4b18b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b190  ldstr    aProcesscontrol_5// "ProcessControl.Configurator.NewField"
0x4b195  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b19a  ldc.i4.0
0x4b19b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b1a0  ldarg.0
0x4b1a1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b1a6  ldstr    aLocidProcessFi// "LOCID_PROCESS_FIELDLABEL"
0x4b1ab  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b1b0  ldstr    aProcesscontrol_6// "ProcessControl.Configurator.Field"
0x4b1b5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b1ba  ldc.i4.0
0x4b1bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b1c0  ldarg.0
0x4b1c1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b1c6  ldstr    aLocidProcessIn// "LOCID_PROCESS_INSERTSTAGETEXTKEY"
0x4b1cb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b1d0  ldstr    aProcesscontrol_7// "ProcessControl.Configurator.Stage.Title"...
0x4b1d5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b1da  ldc.i4.0
0x4b1db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b1e0  ldarg.0
0x4b1e1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b1e6  ldstr    aLocidProcessSt// "LOCID_PROCESS_STAGEAFTERBRANCH"
0x4b1eb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b1f0  ldstr    aProcesscontrol_8// "ProcessControl.Configurator.Stage.Title"...
0x4b1f5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b1fa  ldc.i4.0
0x4b1fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b200  ldarg.0
0x4b201  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b206  ldstr    aLocidProcessIn_0// "LOCID_PROCESS_INSERTPAGETEXTKEY"
0x4b20b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b210  ldstr    aProcesscontrol_9// "ProcessControl.Configurator.Stage.Title"...
0x4b215  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b21a  ldc.i4.0
0x4b21b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b220  ldarg.0
0x4b221  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b226  ldstr    aLocidProcessPa// "LOCID_PROCESS_PAGEAFTERBRANCH"
0x4b22b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b230  ldstr    aProcesscontrol_10// "ProcessControl.Configurator.Stage.Title"...
0x4b235  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b23a  ldc.i4.0
0x4b23b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b240  ldarg.0
0x4b241  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b246  ldstr    aLocidProcessAd// "LOCID_PROCESS_ADDBRANCHTEXTKEY"
0x4b24b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b250  ldstr    aProcesscontrol_11// "ProcessControl.Configurator.Stage.Title"...
0x4b255  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b25a  ldc.i4.0
0x4b25b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b260  ldarg.0
0x4b261  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b266  ldstr    aLocidProcessAd_0// "LOCID_PROCESS_ADDSTEP"
0x4b26b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b270  ldstr    aProcesscontrol_12// "ProcessControl.Configurator.AddStepTitl"...
0x4b275  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b27a  ldc.i4.0
0x4b27b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b280  ldarg.0
0x4b281  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b286  ldstr    aLocidProcessSt_0// "LOCID_PROCESS_STAGENAME"
0x4b28b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b290  ldstr    aProcesscontrol_13// "ProcessControl.Configurator.Stage.Title"...
0x4b295  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b29a  ldc.i4.0
0x4b29b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b2a0  ldarg.0
0x4b2a1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b2a6  ldstr    aLocidProcessSt_1// "LOCID_PROCESS_STAGE_ENTITYNAME"
0x4b2ab  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b2b0  ldstr    aProcesscontrol_14// "ProcessControl.Configurator.Stage.Title"...
0x4b2b5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b2ba  ldc.i4.0
0x4b2bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b2c0  ldarg.0
0x4b2c1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b2c6  ldstr    aLocidProcessSt_2// "LOCID_PROCESS_STAGE_CATEGORYNAME"
0x4b2cb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b2d0  ldstr    aProcesscontrol_15// "ProcessControl.Configurator.Stage.Title"...
0x4b2d5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b2da  ldc.i4.0
0x4b2db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b2e0  ldarg.0
0x4b2e1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b2e6  ldstr    aLocidProcessSt_3// "LOCID_PROCESS_STAGE_STEPNAME"
0x4b2eb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b2f0  ldstr    aProcesscontrol_16// "ProcessControl.Configurator.Stage.Title"...
0x4b2f5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b2fa  ldc.i4.0
0x4b2fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b300  ldarg.0
0x4b301  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b306  ldstr    aLocidProcessSt_4// "LOCID_PROCESS_STAGE_STEPVALNAME"
0x4b30b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b310  ldstr    aProcesscontrol_17// "ProcessControl.Configurator.Stage.Title"...
0x4b315  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b31a  ldc.i4.0
0x4b31b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b320  ldarg.0
0x4b321  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b326  ldstr    aLocidProcessSt_5// "LOCID_PROCESS_STAGE_STEPREQNAME"
0x4b32b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b330  ldstr    aProcesscontrol_18// "ProcessControl.Configurator.Stage.Title"...
0x4b335  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b33a  ldc.i4.0
0x4b33b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b340  ldarg.0
0x4b341  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b346  ldstr    aLocidProcessSt_6// "LOCID_PROCESS_STAGEUNIQUENAME"
0x4b34b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b350  ldstr    aProcesscontrol_19// "ProcessControl.Configurator.Stage.Title"...
0x4b355  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b35a  ldc.i4.0
0x4b35b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b360  ldarg.0
0x4b361  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b366  ldstr    aLocidProcessPa_0// "LOCID_PROCESS_PAGENAME"
0x4b36b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b370  ldstr    aProcesscontrol_20// "ProcessControl.Configurator.Stage.Title"...
0x4b375  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b37a  ldc.i4.0
0x4b37b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b380  ldarg.0
0x4b381  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b386  ldstr    aLocidProcessPa_1// "LOCID_PROCESS_PAGE_NEWLABEL"
0x4b38b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b390  ldstr    aProcesscontrol_21// "ProcessControl.Configurator.Stage.Title"...
0x4b395  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b39a  ldc.i4.0
0x4b39b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b3a0  ldarg.0
0x4b3a1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b3a6  ldstr    aLocidProcessPa_2// "LOCID_PROCESS_PAGE_LABELNAME"
0x4b3ab  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b3b0  ldstr    aProcesscontrol_22// "ProcessControl.Configurator.Stage.Title"...
0x4b3b5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b3ba  ldc.i4.0
0x4b3bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b3c0  ldarg.0
0x4b3c1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b3c6  ldstr    aLocidProcessPa_3// "LOCID_PROCESS_PAGE_SOURCENAME"
0x4b3cb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b3d0  ldstr    aProcesscontrol_23// "ProcessControl.Configurator.Stage.Title"...
0x4b3d5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b3da  ldc.i4.0
0x4b3db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b3e0  ldarg.0
0x4b3e1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b3e6  ldstr    aLocidProcessPa_4// "LOCID_PROCESS_PAGE_FIELDNAME"
0x4b3eb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b3f0  ldstr    aProcesscontrol_24// "ProcessControl.Configurator.Stage.Title"...
0x4b3f5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b3fa  ldc.i4.0
0x4b3fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b400  ldarg.0
0x4b401  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b406  ldstr    aLocidProcessSa// "LOCID_PROCESS_SAVE_HEAD"
0x4b40b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b410  ldstr    aProcesscontrol_25// "ProcessControl.Configurator.Save.Headin"...
0x4b415  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b41a  ldc.i4.0
0x4b41b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b420  ldarg.0
0x4b421  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b426  ldstr    aLocidProcessSa_0// "LOCID_PROCESS_SAVEMESSAGE"
0x4b42b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b430  ldstr    aProcesscontrol_26// "ProcessControl.Configurator.Save.Messag"...
0x4b435  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b43a  ldc.i4.0
0x4b43b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b440  ldarg.0
0x4b441  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b446  ldstr    aLocidProcessSa_1// "LOCID_PROCESS_SAVEERROR"
0x4b44b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b450  ldstr    aProcesscontrol_27// "ProcessControl.Configurator.SaveError"
0x4b455  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b45a  ldc.i4.0
0x4b45b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b460  ldarg.0
0x4b461  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b466  ldstr    aLocidProcessEr// "LOCID_PROCESS_ERRORHEADING"
0x4b46b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b470  ldstr    aProcesscontrol_28// "ProcessControl.Configurator.ErrorHeadin"...
0x4b475  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b47a  ldc.i4.0
0x4b47b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b480  ldarg.0
0x4b481  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b486  ldstr    aLocidProcessEr_0// "LOCID_PROCESS_ERRORBACKMESSAGE"
0x4b48b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b490  ldstr    aProcesscontrol_29// "ProcessControl.Configurator.ErrorBackMe"...
0x4b495  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b49a  ldc.i4.0
0x4b49b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b4a0  ldarg.0
0x4b4a1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b4a6  ldstr    aLocidProcessEr_1// "LOCID_PROCESS_ERRORBACKTEXT"
0x4b4ab  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b4b0  ldstr    aProcesscontrol_30// "ProcessControl.Configurator.ErrorBackLi"...
0x4b4b5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b4ba  ldc.i4.0
0x4b4bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b4c0  ldarg.0
0x4b4c1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b4c6  ldstr    aLocidProcessCl// "LOCID_PROCESS_CLOSEWARNING"
0x4b4cb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b4d0  ldstr    aProcesscontrol_31// "ProcessControl.Configurator.ErrorContac"...
0x4b4d5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b4da  ldc.i4.0
0x4b4db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b4e0  ldarg.0
0x4b4e1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b4e6  ldstr    aLocidProcessEr_2// "LOCID_PROCESS_ERRORCONTACTADMIN"
0x4b4eb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b4f0  ldstr    aProcesscontrol_32// "ProcessControl.Configurator.ErrorCloseW"...
0x4b4f5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b4fa  ldc.i4.0
0x4b4fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b500  ldarg.0
0x4b501  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b506  ldstr    aLocidProcessCl// "LOCID_PROCESS_CLOSEWARNING"
0x4b50b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b510  ldstr    aProcesscontrol_31// "ProcessControl.Configurator.ErrorContac"...
0x4b515  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b51a  ldc.i4.0
0x4b51b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b520  ldarg.0
0x4b521  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b526  ldstr    aLocidProcessEr_2// "LOCID_PROCESS_ERRORCONTACTADMIN"
0x4b52b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b530  ldstr    aProcesscontrol_32// "ProcessControl.Configurator.ErrorCloseW"...
0x4b535  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b53a  ldc.i4.0
0x4b53b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b540  ldarg.0
0x4b541  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b546  ldstr    aLocidProcessEr_3// "LOCID_PROCESS_ERRORCLOSE"
0x4b54b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b550  ldstr    aProcesscontrol_33// "ProcessControl.Configurator.ErrorCloseB"...
0x4b555  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b55a  ldc.i4.0
0x4b55b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b560  ldarg.0
0x4b561  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b566  ldstr    aLocidProcessEr_4// "LOCID_PROCESS_ERRORBACK"
0x4b56b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b570  ldstr    aProcesscontrol_34// "ProcessControl.Configurator.ErrorBackBu"...
0x4b575  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b57a  ldc.i4.0
0x4b57b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b580  ldarg.0
0x4b581  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b586  ldstr    aLocidProcessCl_0// "LOCID_PROCESS_CLOSEWARNINGALT"
0x4b58b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4b590  ldstr    aProcesscontrol_35// "ProcessControl.Configurator.CloseWarnin"...
0x4b595  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4b59a  ldc.i4.0
0x4b59b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4b5a0  ldarg.0
0x4b5a1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4b5a6  ldstr    aLocidProcessSa_2// "LOCID_PROCESS_SAVINGALT"
0x4b5ab  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
  ... truncated ...
```
