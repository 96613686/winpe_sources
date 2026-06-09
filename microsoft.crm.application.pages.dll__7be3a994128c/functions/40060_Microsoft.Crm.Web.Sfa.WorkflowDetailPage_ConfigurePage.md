# Microsoft.Crm.Web.Sfa.WorkflowDetailPage::ConfigurePage

- ea: `0x40060`
- end: `0x40551`
- name: `Microsoft.Crm.Web.Sfa.WorkflowDetailPage::ConfigurePage`
- size: `1265`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x40086`: `/_static/_common/scripts/formevt.js`
- `0x400c6`: `/_common/WindowInformation/windowinformation.js.aspx`
- `0x401dd`: `LOCID_CONFIRM_STEP_DELETE`
- `0x401e8`: `Web.SFA.Workflow.ConfirmOnDeleteStep`
- `0x401fe`: `LOCID_CONFIRM_COMPOSITE_DELETE`
- `0x40209`: `Web.SFA.Workflow.ConfirmOnDeleteCompositeStep`
- `0x4021f`: `LOCID_CONFIRM_STAGE_STEP_DELETE`
- `0x4022a`: `Web.SFA.Workflow.ConfirmOnStageDeleteStep`
- `0x40240`: `LOCID_ALERT_STAGE_STEP_NO_DELETE`
- `0x4024b`: `Web.SFA.Workflow.CannotDeleteStageStep`
- `0x40306`: `LOCID_MENU_ADD_CREATE_STEP`
- `0x40311`: `Web.SFA.Workflow.AddCreateRecordStep`
- `0x403ab`: `LOCID_ERROR_DELETE_COND_BRANCH`
- `0x403b6`: `Web.SFA.Workflow.DeleteElseIfBranch.Error`

## pseudocode

```c

```

## disassembly

```asm
0x40060  ldarg.0
0x40061  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40066  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0x4006b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x40070  ldarg.0
0x40071  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40076  ldstr    aSfaWorkflowWor_0// "/sfa/workflow/workflowstep.css.aspx"
0x4007b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x40080  ldarg.0
0x40081  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40086  ldstr    aStaticCommonSc_23// "/_static/_common/scripts/formevt.js"
0x4008b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x40090  ldarg.0
0x40091  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40096  ldstr    aStaticControls_6// "/_static/_controls/popupmenu/popupmenu."...
0x4009b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x400a0  ldarg.0
0x400a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x400a6  ldstr    aStaticSfaWorkf_1// "/_static/sfa/workflow/slugsupport.js"
0x400ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x400b0  ldarg.0
0x400b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x400b6  ldstr    aStaticSfaWorkf_2// "/_static/sfa/workflow/workflowstep.js"
0x400bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x400c0  ldarg.0
0x400c1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x400c6  ldstr    aCommonWindowin// "/_common/WindowInformation/windowinform"...
0x400cb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x400d0  ldarg.0
0x400d1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x400d6  ldstr    aStaticToolsDep// "/_static/tools/dependency/scripts/depen"...
0x400db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x400e0  ldarg.0
0x400e1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x400e6  ldstr    aWorkflow_0// "Workflow"
0x400eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x400f0  ldarg.0
0x400f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x400f6  ldstr    aLocidPublicati// "LOCID_PUBLICATION_TITLE_SHOW"
0x400fb  ldarg.0
0x400fc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x40101  ldstr    aWorkflowpublic// "WorkflowPublicationTitleShow"
0x40106  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4010b  ldc.i4.0
0x4010c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x40111  ldarg.0
0x40112  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40117  ldstr    aLocidPublicati_0// "LOCID_PUBLICATION_TITLE_HIDE"
0x4011c  ldarg.0
0x4011d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x40122  ldstr    aWorkflowpublic_0// "WorkflowPublicationTitleHide"
0x40127  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4012c  ldc.i4.0
0x4012d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x40132  ldarg.0
0x40133  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40138  ldstr    aLocidArguments// "LOCID_ARGUMENTS_TITLE_SHOW"
0x4013d  ldarg.0
0x4013e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x40143  ldstr    aWorkflowargume// "WorkflowArgumentsTitleShow"
0x40148  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4014d  ldc.i4.0
0x4014e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x40153  ldarg.0
0x40154  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40159  ldstr    aLocidArguments_0// "LOCID_ARGUMENTS_TITLE_HIDE"
0x4015e  ldarg.0
0x4015f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x40164  ldstr    aWorkflowargume_0// "WorkflowArgumentsTitleHide"
0x40169  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4016e  ldc.i4.0
0x4016f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x40174  ldarg.0
0x40175  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4017a  ldstr    aLocidWarnToSav// "LOCID_WARN_TO_SAVE_WORKFLOW"
0x4017f  ldarg.0
0x40180  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x40185  ldstr    aWebSfaWorkflow_26// "Web.SFA.Workflow.WarnToSave"
0x4018a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4018f  ldc.i4.0
0x40190  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x40195  ldarg.0
0x40196  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4019b  ldstr    aLocidWarnToSpe// "LOCID_WARN_TO_SPECIFY_TRIGGER"
0x401a0  ldarg.0
0x401a1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x401a6  ldstr    aWebSfaWorkflow_27// "Web.SFA.Workflow.TriggerEventWarning"
0x401ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x401b0  ldc.i4.0
0x401b1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x401b6  ldarg.0
0x401b7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x401bc  ldstr    aLocidWarnToSpe_0// "LOCID_WARN_TO_SPECIFY_ENTITY"
0x401c1  ldarg.0
0x401c2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x401c7  ldstr    aWebSfaWorkflow_28// "Web.SFA.Workflow.EntityWarning"
0x401cc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x401d1  ldc.i4.0
0x401d2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x401d7  ldarg.0
0x401d8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x401dd  ldstr    aLocidConfirmSt// "LOCID_CONFIRM_STEP_DELETE"
0x401e2  ldarg.0
0x401e3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x401e8  ldstr    aWebSfaWorkflow_29// "Web.SFA.Workflow.ConfirmOnDeleteStep"
0x401ed  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x401f2  ldc.i4.0
0x401f3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x401f8  ldarg.0
0x401f9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x401fe  ldstr    aLocidConfirmCo// "LOCID_CONFIRM_COMPOSITE_DELETE"
0x40203  ldarg.0
0x40204  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x40209  ldstr    aWebSfaWorkflow_30// "Web.SFA.Workflow.ConfirmOnDeleteComposi"...
0x4020e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x40213  ldc.i4.0
0x40214  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x40219  ldarg.0
0x4021a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4021f  ldstr    aLocidConfirmSt_0// "LOCID_CONFIRM_STAGE_STEP_DELETE"
0x40224  ldarg.0
0x40225  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4022a  ldstr    aWebSfaWorkflow_31// "Web.SFA.Workflow.ConfirmOnStageDeleteSt"...
0x4022f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x40234  ldc.i4.0
0x40235  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4023a  ldarg.0
0x4023b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40240  ldstr    aLocidAlertStag// "LOCID_ALERT_STAGE_STEP_NO_DELETE"
0x40245  ldarg.0
0x40246  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4024b  ldstr    aWebSfaWorkflow_32// "Web.SFA.Workflow.CannotDeleteStageStep"
0x40250  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x40255  ldc.i4.0
0x40256  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4025b  ldarg.0
0x4025c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40261  ldstr    aLocidConfirmSt_1// "LOCID_CONFIRM_STAGE_STEP_ADD"
0x40266  ldarg.0
0x40267  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4026c  ldstr    aWebSfaWorkflow_33// "Web.SFA.Workflow.ConfirmOnStageAddStep"
0x40271  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x40276  ldc.i4.0
0x40277  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4027c  ldarg.0
0x4027d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40282  ldstr    aLocidMenuAddSt// "LOCID_MENU_ADD_STAGE_STEP"
0x40287  ldarg.0
0x40288  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4028d  ldstr    aWebSfaWorkflow_34// "Web.SFA.Workflow.AddStageStep"
0x40292  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x40297  ldc.i4.0
0x40298  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4029d  ldarg.0
0x4029e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x402a3  ldstr    aLocidMenuAddCh// "LOCID_MENU_ADD_CHECK_STEP"
0x402a8  ldarg.0
0x402a9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x402ae  ldstr    aWebSfaWorkflow_35// "Web.SFA.Workflow.AddCheckStep"
0x402b3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x402b8  ldc.i4.0
0x402b9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x402be  ldarg.0
0x402bf  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x402c4  ldstr    aLocidMenuAddEl// "LOCID_MENU_ADD_ELSEIF_STEP"
0x402c9  ldarg.0
0x402ca  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x402cf  ldstr    aWebSfaWorkflow_36// "Web.SFA.Workflow.AddElseIfStep"
0x402d4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x402d9  ldc.i4.0
0x402da  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x402df  ldarg.0
0x402e0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x402e5  ldstr    aLocidMenuAddEl_0// "LOCID_MENU_ADD_ELSE_STEP"
0x402ea  ldarg.0
0x402eb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x402f0  ldstr    aWebSfaWorkflow_37// "Web.SFA.Workflow.AddElseStep"
0x402f5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x402fa  ldc.i4.0
0x402fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x40300  ldarg.0
0x40301  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40306  ldstr    aLocidMenuAddCr// "LOCID_MENU_ADD_CREATE_STEP"
0x4030b  ldarg.0
0x4030c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x40311  ldstr    aWebSfaWorkflow_38// "Web.SFA.Workflow.AddCreateRecordStep"
0x40316  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4031b  ldc.i4.0
0x4031c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x40321  ldarg.0
0x40322  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40327  ldstr    aLocidMenuAddAs// "LOCID_MENU_ADD_ASSIGN_STEP"
0x4032c  ldarg.0
0x4032d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x40332  ldstr    aWebSfaWorkflow_39// "Web.SFA.Workflow.AddAssignStep"
0x40337  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4033c  ldc.i4.0
0x4033d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x40342  ldarg.0
0x40343  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40348  ldstr    aLocidMenuAddCh_0// "LOCID_MENU_ADD_CHANGESTATUS_STEP"
0x4034d  ldarg.0
0x4034e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x40353  ldstr    aWebSfaWorkflow_40// "Web.SFA.Workflow.ChangeStatus"
0x40358  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4035d  ldc.i4.0
0x4035e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x40363  ldarg.0
0x40364  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40369  ldstr    aLocidMenuAddSt_0// "LOCID_MENU_ADD_STOPWORKFLOW_STEP"
0x4036e  ldarg.0
0x4036f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x40374  ldstr    aWebSfaWorkflow_41// "Web.SFA.Workflow.StopWorkflow"
0x40379  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4037e  ldc.i4.0
0x4037f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x40384  ldarg.0
0x40385  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4038a  ldstr    aLocidErrorAddC// "LOCID_ERROR_ADD_COND_BRANCH"
0x4038f  ldarg.0
0x40390  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x40395  ldstr    aWebSfaWorkflow_42// "Web.SFA.Workflow.Error.AddCondBranch"
0x4039a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4039f  ldc.i4.0
0x403a0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x403a5  ldarg.0
0x403a6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x403ab  ldstr    aLocidErrorDele// "LOCID_ERROR_DELETE_COND_BRANCH"
0x403b0  ldarg.0
0x403b1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x403b6  ldstr    aWebSfaWorkflow_43// "Web.SFA.Workflow.DeleteElseIfBranch.Err"...
0x403bb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x403c0  ldc.i4.0
0x403c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x403c6  ldarg.0
0x403c7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x403cc  ldstr    aLocidConfirmCh// "LOCID_CONFIRM_CHANGE_ENTITY"
0x403d1  ldarg.0
0x403d2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x403d7  ldstr    aWebSfaWorkflow_44// "Web.SFA.Workflow.Confirm.ChangeEntity"
0x403dc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x403e1  ldc.i4.0
0x403e2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x403e7  ldarg.0
0x403e8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x403ed  ldstr    aLocidConfirmCh_0// "LOCID_CONFIRM_CHANGE_WAITTIMEOUT"
0x403f2  ldarg.0
0x403f3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x403f8  ldstr    aWebSfaWorkflow_45// "Web.SFA.Workflow.Confirm.ChangeToWaitTi"...
0x403fd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x40402  ldc.i4.0
0x40403  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x40408  ldarg.0
0x40409  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4040e  ldstr    aLocidCloseButt// "LOCID_CLOSE_BUTTON_LABEL"
0x40413  ldarg.0
0x40414  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x40419  ldstr    aButtonLabelClo// "Button_Label_Close"
0x4041e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x40423  ldc.i4.0
0x40424  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x40429  ldarg.0
0x4042a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x4042f  ldstr    aLocidPopupMenu// "LOCID_POPUP_MENU_LABEL"
0x40434  ldarg.0
0x40435  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x4043a  ldstr    aPopupMenuTitle// "Popup_Menu_Title_Format"
0x4043f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x40444  ldc.i4.0
0x40445  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4044a  ldarg.0
0x4044b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40450  ldarg.0
0x40451  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x40456  call     void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.RelatedInformation.Categories.WorkflowRelatedCategory::SetStringResources(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager)
0x4045b  ldarg.0
0x4045c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40461  ldstr    aLocidNumberRan// "LOCID_NUMBER_RANGE_MASK"
0x40466  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4046b  ldstr    aCCrmSrcApplica// "C:.crm.src.Application.Web._controls.nu"...
0x40470  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x40475  ldc.i4.0
0x40476  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4047b  ldarg.0
0x4047c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x40481  ldstr    aLocidFloatRang// "LOCID_FLOAT_RANGE_MASK"
0x40486  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4048b  ldstr    aCCrmSrcApplica_0// "C:.crm.src.Application.Web._controls.nu"...
0x40490  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x40495  ldc.i4.0
0x40496  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4049b  ldarg.0
0x4049c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x404a1  ldstr    aLocidDeverrorB// "LOCID_DEVERROR_BADDATATYPE_INT"
0x404a6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x404ab  ldstr    aDeverrorBaddat// "DevError.BadDataType.Integer"
0x404b0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x404b5  ldc.i4.0
0x404b6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x404bb  ldarg.0
  ... truncated ...
```
