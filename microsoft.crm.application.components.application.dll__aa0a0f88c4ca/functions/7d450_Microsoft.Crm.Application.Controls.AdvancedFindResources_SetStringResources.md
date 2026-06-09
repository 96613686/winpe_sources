# Microsoft.Crm.Application.Controls.AdvancedFindResources::SetStringResources

- ea: `0x7d450`
- end: `0x7e147`
- name: `Microsoft.Crm.Application.Controls.AdvancedFindResources::SetStringResources`
- size: `3319`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x7f650`
- `0x825b0`
- `0x9d1b0`

## string_xrefs

- `0x7d67f`: `MenuItem_Label_Delete`
- `0x7d5c1`: `LOCID_AF_DELETEENTITY`
- `0x7d5c7`: `AF_Msg_DeleteEntity`
- `0x7d679`: `LOCID_AF_MNUITMDELETE`
- `0x7d690`: `LOCID_AF_DELETEFIELD`
- `0x7d696`: `AF_Msg_DeleteField`
- `0x7d6a7`: `LOCID_AF_DELETEGROUP`
- `0x7d6ad`: `AF_Msg_DeleteGroup`
- `0x7d879`: `AF_ToolTip_DeleteThisErrClause`
- `0x7d88a`: `LOCID_AF_ERRINLINKENTITY`
- `0x7d890`: `AF_Msg_ErrorInShowingLinkEntity`

## pseudocode

```c

```

## disassembly

```asm
0x7d450  ldarg.1
0x7d451  ldstr    aLocidAfAllhidd// "LOCID_AF_ALLHIDDENMSG"
0x7d456  ldarg.2
0x7d457  ldstr    aAfMessageAllhi// "AF_Message_AllHidden"
0x7d45c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d461  ldc.i4.0
0x7d462  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d467  ldarg.1
0x7d468  ldstr    aLocidAfSpecial// "LOCID_AF_SPECIALQRYMSG"
0x7d46d  ldarg.2
0x7d46e  ldstr    aAfMessageSpeci// "AF_Message_SpecialQuery"
0x7d473  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d478  ldc.i4.0
0x7d479  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d47e  ldarg.1
0x7d47f  ldstr    aLocidAfSearchm// "LOCID_AF_SEARCHMODIFIED_TITLE"
0x7d484  ldarg.2
0x7d485  ldstr    aAfMsgSearchmod// "AF_Msg_SearchModified_Title"
0x7d48a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d48f  ldc.i4.0
0x7d490  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d495  ldarg.1
0x7d496  ldstr    aLocidAfOnwincl// "LOCID_AF_ONWINCLOSE_MSG"
0x7d49b  ldarg.2
0x7d49c  ldstr    aAfMsgOnclosewi// "AF_Msg_OnCloseWindow"
0x7d4a1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d4a6  ldc.i4.0
0x7d4a7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d4ac  ldarg.1
0x7d4ad  ldstr    aLocidAfSearchm_0// "LOCID_AF_SEARCHMODIFIED_MSG"
0x7d4b2  ldarg.2
0x7d4b3  ldstr    aAfMsgSearchmod_0// "AF_Msg_SearchModified"
0x7d4b8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d4bd  ldc.i4.0
0x7d4be  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d4c3  ldarg.1
0x7d4c4  ldstr    aLocidAfValuemi// "LOCID_AF_VALUEMISSINGFOR_MSG"
0x7d4c9  ldarg.2
0x7d4ca  ldstr    aAfMsgValuemiss// "AF_Msg_ValueMissingFor"
0x7d4cf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d4d4  ldc.i4.0
0x7d4d5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d4da  ldarg.1
0x7d4db  ldstr    aLocidAfErrorgr// "LOCID_AF_ERRORGROUPING_MSG"
0x7d4e0  ldarg.2
0x7d4e1  ldstr    aAfMsgErrorgrou// "AF_Msg_ErrorGrouping"
0x7d4e6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d4eb  ldc.i4.0
0x7d4ec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d4f1  ldarg.1
0x7d4f2  ldstr    aLocidAfHierarc// "LOCID_AF_HIERARCHIAL_ERROR_MSG"
0x7d4f7  ldarg.2
0x7d4f8  ldstr    aAfMsgErrorgrou_0// "AF_Msg_ErrorGrouping_WithHierarchialOpe"...
0x7d4fd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d502  ldc.i4.0
0x7d503  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d508  ldarg.1
0x7d509  ldstr    aLocidAfNewqryt// "LOCID_AF_NEWQRYTITLE"
0x7d50e  ldarg.2
0x7d50f  ldstr    aAdvancedFindOp// "Advanced_Find_Option_New"
0x7d514  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d519  ldc.i4.0
0x7d51a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d51f  ldarg.1
0x7d520  ldstr    aLocidAfEnterva// "LOCID_AF_ENTERVALUE"
0x7d525  ldarg.2
0x7d526  ldstr    aAfLabelEnterva// "AF_Label_EnterValue"
0x7d52b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d530  ldc.i4.0
0x7d531  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d536  ldarg.1
0x7d537  ldstr    aLocidAfEnterpi// "LOCID_AF_ENTERPICKLIST"
0x7d53c  ldarg.2
0x7d53d  ldstr    aAfLabelEnterpi// "AF_Label_EnterPicklist"
0x7d542  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d547  ldc.i4.0
0x7d548  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d54d  ldarg.1
0x7d54e  ldstr    aLocidAfEnterda// "LOCID_AF_ENTERDATE"
0x7d553  ldarg.2
0x7d554  ldstr    aAfLabelEnterda// "AF_Label_EnterDate"
0x7d559  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d55e  ldc.i4.0
0x7d55f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d564  ldarg.1
0x7d565  ldstr    aLocidAfEnterte// "LOCID_AF_ENTERTEXT"
0x7d56a  ldarg.2
0x7d56b  ldstr    aAfLabelEnterte// "AF_Label_EnterText"
0x7d570  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d575  ldc.i4.0
0x7d576  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d57b  ldarg.1
0x7d57c  ldstr    aLocidAfSelectf// "LOCID_AF_SELECTFIELDENTITY"
0x7d581  ldarg.2
0x7d582  ldstr    aAfLabelSelectf// "AF_Label_SelectFieldOrEntity"
0x7d587  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d58c  ldc.i4.0
0x7d58d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d592  ldarg.1
0x7d593  ldstr    aLocidAfExpande// "LOCID_AF_EXPANDENTITY"
0x7d598  ldarg.2
0x7d599  ldstr    aAfMenuitemExpa// "AF_MenuItem_Expand"
0x7d59e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d5a3  ldc.i4.0
0x7d5a4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d5a9  ldarg.1
0x7d5aa  ldstr    aLocidAfCollaps// "LOCID_AF_COLLAPSEENTITY"
0x7d5af  ldarg.2
0x7d5b0  ldstr    aAfMenuitemColl// "AF_MenuItem_Collapse"
0x7d5b5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d5ba  ldc.i4.0
0x7d5bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d5c0  ldarg.1
0x7d5c1  ldstr    aLocidAfDeletee// "LOCID_AF_DELETEENTITY"
0x7d5c6  ldarg.2
0x7d5c7  ldstr    aAfMsgDeleteent// "AF_Msg_DeleteEntity"
0x7d5cc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d5d1  ldc.i4.0
0x7d5d2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d5d7  ldarg.1
0x7d5d8  ldstr    aLocidAfChangee// "LOCID_AF_CHANGEENTITY"
0x7d5dd  ldarg.2
0x7d5de  ldstr    aAfMsgChangeent// "AF_Msg_ChangeEntity"
0x7d5e3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d5e8  ldc.i4.0
0x7d5e9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d5ee  ldarg.1
0x7d5ef  ldstr    aLocidAfRelenti// "LOCID_AF_RELENTITYEXISTSINQUERY"
0x7d5f4  ldarg.2
0x7d5f5  ldstr    aAfMsgRelentity// "AF_Msg_RelEntityExistsInQuery"
0x7d5fa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d5ff  ldc.i4.0
0x7d600  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d605  ldarg.1
0x7d606  ldstr    aLocidAfClauseh// "LOCID_AF_CLAUSEHIDDEN"
0x7d60b  ldarg.2
0x7d60c  ldstr    aAfLabelClauseh// "AF_Label_ClauseHidden"
0x7d611  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d616  ldc.i4.0
0x7d617  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d61c  ldarg.1
0x7d61d  ldstr    aLocidAfSelectr// "LOCID_AF_SELECTROW"
0x7d622  ldarg.2
0x7d623  ldstr    aAfMenuitemSele// "AF_MenuItem_SelectRow"
0x7d628  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d62d  ldc.i4.0
0x7d62e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d633  ldarg.1
0x7d634  ldstr    aLocidAfUnselec// "LOCID_AF_UNSELECTROW"
0x7d639  ldarg.2
0x7d63a  ldstr    aAfMenuitemUnse// "AF_MenuItem_UnselectRow"
0x7d63f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d644  ldc.i4.0
0x7d645  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d64a  ldarg.1
0x7d64b  ldstr    aLocidAfHideins// "LOCID_AF_HIDEINSIMPLE"
0x7d650  ldarg.2
0x7d651  ldstr    aAfMenuitemHide// "AF_MenuItem_HideInSimple"
0x7d656  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d65b  ldc.i4.0
0x7d65c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d661  ldarg.1
0x7d662  ldstr    aLocidAfShowins// "LOCID_AF_SHOWINSIMPLE"
0x7d667  ldarg.2
0x7d668  ldstr    aAfMenuitemShow// "AF_MenuItem_ShowInSimple"
0x7d66d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d672  ldc.i4.0
0x7d673  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d678  ldarg.1
0x7d679  ldstr    aLocidAfMnuitmd// "LOCID_AF_MNUITMDELETE"
0x7d67e  ldarg.2
0x7d67f  ldstr    aMenuitemLabelD_1// "MenuItem_Label_Delete"
0x7d684  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d689  ldc.i4.0
0x7d68a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d68f  ldarg.1
0x7d690  ldstr    aLocidAfDeletef// "LOCID_AF_DELETEFIELD"
0x7d695  ldarg.2
0x7d696  ldstr    aAfMsgDeletefie// "AF_Msg_DeleteField"
0x7d69b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d6a0  ldc.i4.0
0x7d6a1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d6a6  ldarg.1
0x7d6a7  ldstr    aLocidAfDeleteg// "LOCID_AF_DELETEGROUP"
0x7d6ac  ldarg.2
0x7d6ad  ldstr    aAfMsgDeletegro// "AF_Msg_DeleteGroup"
0x7d6b2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d6b7  ldc.i4.0
0x7d6b8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d6bd  ldarg.1
0x7d6be  ldstr    aLocidAfSelectg// "LOCID_AF_SELECTGROUP"
0x7d6c3  ldarg.2
0x7d6c4  ldstr    aAfMenuitemSele_0// "AF_MenuItem_SelectGroup"
0x7d6c9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d6ce  ldc.i4.0
0x7d6cf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d6d4  ldarg.1
0x7d6d5  ldstr    aLocidAfUnselec_0// "LOCID_AF_UNSELECTGROUP"
0x7d6da  ldarg.2
0x7d6db  ldstr    aAfMenuitemUnse_0// "AF_MenuItem_UnselectGroup"
0x7d6e0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d6e5  ldc.i4.0
0x7d6e6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d6eb  ldarg.1
0x7d6ec  ldstr    aLocidAfUngroup// "LOCID_AF_UNGROUP"
0x7d6f1  ldarg.2
0x7d6f2  ldstr    aAfMenuitemUngr// "AF_MenuItem_UnGroup"
0x7d6f7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d6fc  ldc.i4.0
0x7d6fd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d702  ldarg.1
0x7d703  ldstr    aLocidAfChangeg// "LOCID_AF_CHANGEGRP"
0x7d708  ldarg.2
0x7d709  ldstr    aAfMenuitemChan// "AF_MenuItem_ChangeGroup"
0x7d70e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d713  ldc.i4.0
0x7d714  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d719  ldarg.1
0x7d71a  ldstr    aLocidAfTxtor// "LOCID_AF_TXTOR"
0x7d71f  ldarg.2
0x7d720  ldstr    aAfTextOr// "AF_Text_Or"
0x7d725  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d72a  ldc.i4.0
0x7d72b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d730  ldarg.1
0x7d731  ldstr    aLocidAfTxtand// "LOCID_AF_TXTAND"
0x7d736  ldarg.2
0x7d737  ldstr    aAfTextAnd// "AF_Text_And"
0x7d73c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d741  ldc.i4.0
0x7d742  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d747  ldarg.1
0x7d748  ldstr    aLocidAfAddrowt// "LOCID_AF_ADDROWTOGRP"
0x7d74d  ldarg.2
0x7d74e  ldstr    aAfMenuitemAddr// "AF_MenuItem_AddRowToGroup"
0x7d753  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d758  ldc.i4.0
0x7d759  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d75e  ldarg.1
0x7d75f  ldstr    aLocidAfSelectc// "LOCID_AF_SELECTCOND"
0x7d764  ldarg.2
0x7d765  ldstr    aAfLabelSelectc// "AF_Label_SelectCondition"
0x7d76a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d76f  ldc.i4.0
0x7d770  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d775  ldarg.1
0x7d776  ldstr    aLocidAfOptgrpf// "LOCID_AF_OPTGRPFIELDS"
0x7d77b  ldarg.2
0x7d77c  ldstr    aAfOptiongrplab// "AF_OptionGrpLabel_Fields"
0x7d781  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d786  ldc.i4.0
0x7d787  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d78c  ldarg.1
0x7d78d  ldstr    aLocidAfOptgrpr// "LOCID_AF_OPTGRPRELATED"
0x7d792  ldarg.2
0x7d793  ldstr    aAfOptiongrplab_0// "AF_OptionGrpLabel_Related"
0x7d798  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d79d  ldc.i4.0
0x7d79e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d7a3  ldarg.1
0x7d7a4  ldstr    aLocidAfFielddo// "LOCID_AF_FIELDDOESNOTEXIST"
0x7d7a9  ldarg.2
0x7d7aa  ldstr    aAfFielddoesnot// "AF_FieldDoesNotExist"
0x7d7af  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d7b4  ldc.i4.0
0x7d7b5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d7ba  ldarg.1
0x7d7bb  ldstr    aLocidAfReldoes// "LOCID_AF_RELDOESNOTEXIST"
0x7d7c0  ldarg.2
0x7d7c1  ldstr    aAfRelationship// "AF_RelationshipDoesNotExist"
0x7d7c6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d7cb  ldc.i4.0
0x7d7cc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d7d1  ldarg.1
0x7d7d2  ldstr    aLocidAfPcklstv// "LOCID_AF_PCKLSTVALDOESNOTEXIST"
0x7d7d7  ldarg.2
0x7d7d8  ldstr    aAfPicklistvalu// "AF_PicklistValueDoesNotExist"
0x7d7dd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d7e2  ldc.i4.0
0x7d7e3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d7e8  ldarg.1
0x7d7e9  ldstr    aLocidAfMultipl// "LOCID_AF_MULTIPLEVALSNOTALLOWED"
0x7d7ee  ldarg.2
0x7d7ef  ldstr    aAfMultiplevalu// "AF_MultipleValuesNotAllowed"
0x7d7f4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d7f9  ldc.i4.0
0x7d7fa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d7ff  ldarg.1
0x7d800  ldstr    aLocidAfNonnumm// "LOCID_AF_NONNUMMERICVAL"
0x7d805  ldarg.2
0x7d806  ldstr    aAfNonnumericva// "AF_NonNumericValue"
0x7d80b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d810  ldc.i4.0
0x7d811  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x7d816  ldarg.1
0x7d817  ldstr    aLocidAfNonlook// "LOCID_AF_NONLOOKUPVAL"
0x7d81c  ldarg.2
0x7d81d  ldstr    aAfNonlookupval// "AF_NonLookupValue"
0x7d822  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7d827  ldc.i4.0
  ... truncated ...
```
