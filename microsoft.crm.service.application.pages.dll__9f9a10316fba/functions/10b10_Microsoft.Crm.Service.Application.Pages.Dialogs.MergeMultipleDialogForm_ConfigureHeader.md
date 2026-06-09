# Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::ConfigureHeader

- ea: `0x10b10`
- end: `0x10cd2`
- name: `Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::ConfigureHeader`
- size: `450`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x10c49`: `Error_Merge_Privileges`
- `0x10c6a`: `Error_Merge_Privileges`

## pseudocode

```c

```

## disassembly

```asm
0x10b10  ldarg.0
0x10b11  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureHeader()
0x10b16  ldarg.0
0x10b17  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10b1c  ldstr    aGridGridMergeC// "/_grid/grid_merge.css.aspx"
0x10b21  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x10b26  ldarg.0
0x10b27  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10b2c  ldstr    aStaticGridCmds_0// "/_static/_grid/cmds/util.js"
0x10b31  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x10b36  ldarg.0
0x10b37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10b3c  ldstr    aStaticGridCmds// "/_static/_grid/cmds/multiaction.js"
0x10b41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x10b46  ldarg.0
0x10b47  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10b4c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath()
0x10b51  ldarg.0
0x10b52  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10b57  ldstr    aLocidMergeAtle// "LOCID_MERGE_ATLEASETONE_ERROR"
0x10b5c  ldarg.0
0x10b5d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10b62  ldstr    aMergerecordsSe// "MergeRecords_Select_Atleast_OneError"
0x10b67  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10b6c  ldc.i4.0
0x10b6d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10b72  ldarg.0
0x10b73  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10b78  ldstr    aLocidMergeSucc// "LOCID_MERGE_SUCCESS"
0x10b7d  ldarg.0
0x10b7e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10b83  ldstr    aMergerecordsCa// "MergeRecords_Cases_Merged_Success"
0x10b88  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10b8d  ldc.i4.0
0x10b8e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10b93  ldarg.0
0x10b94  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10b99  ldstr    aLocidMergeFail// "LOCID_MERGE_FAIL"
0x10b9e  ldarg.0
0x10b9f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10ba4  ldstr    aMergerecordsCa_0// "MergeRecords_Cases_Merged_Fail"
0x10ba9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10bae  ldc.i4.0
0x10baf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10bb4  ldarg.0
0x10bb5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10bba  ldstr    aLocidParentChi// "LOCID_PARENT_CHILD_ASSCO_SUCCESS"
0x10bbf  ldarg.0
0x10bc0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10bc5  ldstr    aParentchildCas// "ParentChild_Cases_Associate_Success"
0x10bca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10bcf  ldc.i4.0
0x10bd0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10bd5  ldarg.0
0x10bd6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10bdb  ldstr    aLocidMergeSucc_0// "LOCID_MERGE_SUCCESS_FAIL"
0x10be0  ldarg.0
0x10be1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10be6  ldstr    aMergerecordsCa_1// "MergeRecords_Cases_Merged_Success_Fail"
0x10beb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10bf0  ldc.i4.0
0x10bf1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10bf6  ldarg.0
0x10bf7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10bfc  ldstr    aLocidParentchi// "LOCID_PARENTCHILD_NOSUCC_FAILS"
0x10c01  ldarg.0
0x10c02  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10c07  ldstr    aParentchildCas_0// "ParentChild_Cases_NoSuccess_Fail"
0x10c0c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10c11  ldc.i4.0
0x10c12  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10c17  ldarg.0
0x10c18  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10c1d  ldstr    aLocidErrFail1F// "LOCID_ERR_FAIL1_FAIL2"
0x10c22  ldarg.0
0x10c23  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10c28  ldstr    aMergerecordsCa_2// "MergeRecords_Cases_Fail1_Fail2"
0x10c2d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10c32  ldc.i4.0
0x10c33  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10c38  ldarg.0
0x10c39  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10c3e  ldstr    aLocidErrorMsg0// "LOCID_ERROR_MSG_0X80045301"
0x10c43  ldarg.0
0x10c44  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10c49  ldstr    aErrorMergePriv// "Error_Merge_Privileges"
0x10c4e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10c53  ldc.i4.0
0x10c54  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10c59  ldarg.0
0x10c5a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10c5f  ldstr    aLocidErrorMsg0_0// "LOCID_ERROR_MSG_0X80048306"
0x10c64  ldarg.0
0x10c65  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10c6a  ldstr    aErrorMergePriv// "Error_Merge_Privileges"
0x10c6f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10c74  ldc.i4.0
0x10c75  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10c7a  ldarg.0
0x10c7b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10c80  ldstr    aLocidErrorMess// "LOCID_ERROR_MESSAGE_FAIL_SINGLE"
0x10c85  ldarg.0
0x10c86  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10c8b  ldstr    aErrorMessageFa// "Error_Message_Fail_Single"
0x10c90  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10c95  ldc.i4.0
0x10c96  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10c9b  ldarg.0
0x10c9c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10ca1  ldstr    aLocidErrorMess_0// "LOCID_ERROR_MESSAGE_FAIL"
0x10ca6  ldarg.0
0x10ca7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10cac  ldstr    aErrorMessageFa_0// "Error_Message_Fail"
0x10cb1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10cb6  ldc.i4.0
0x10cb7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x10cbc  ldarg.0
0x10cbd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x10cc2  ldstr    aGridonchange// "GridOnChange"
0x10cc7  ldstr    aSetfilters// "setFilters()"
0x10ccc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0x10cd1  ret
```
