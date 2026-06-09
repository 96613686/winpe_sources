# Microsoft.Crm.Web.Tools.SystemCustomization.OptionSet.OptionSetPage::SetPageHeader

- ea: `0xaa050`
- end: `0xaa364`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.OptionSet.OptionSetPage::SetPageHeader`
- size: `788`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0xa9df0`

## callees

- `0xaa050`
- `0xaa370`
- `0xaace0`

## string_xrefs

- `0xaa0d6`: `/_static/_common/styles/AutoToolTip.js`
- `0xaa251`: `Solution.SolutionComponent.OptionSet.Messages.PublishingOptionSet`
- `0xaa0e6`: `_bCreate`
- `0xaa1ab`: `LOCID_MULTI_UPDATESET`
- `0xaa1c7`: `LOCID_MULTI_DELETESET`
- `0xaa272`: `Solution.SolutionComponent.OptionSet.Messages.PublishUnSaved`
- `0xaa293`: `SystemCustomization.AttributeUtil.Messages.CannotDeleteSystemAttribute`
- `0xaa2b4`: `SystemCustomization.AttributeUtil.Messages.ConfirmAttributeDelete`

## pseudocode

```c

```

## disassembly

```asm
0xaa050  ldarg.0
0xaa051  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa056  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0xaa05b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xaa060  ldarg.0
0xaa061  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa066  ldstr    aStaticToolsSys_19// "/_static/tools/systemcustomization/attr"...
0xaa06b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xaa070  ldarg.0
0xaa071  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa076  ldstr    aStaticGridCmds// "/_static/_grid/cmds/util.js"
0xaa07b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xaa080  ldarg.0
0xaa081  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa086  ldstr    aStaticToolsSys_0// "/_static/tools/systemcustomization/scri"...
0xaa08b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xaa090  ldarg.0
0xaa091  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa096  ldstr    aStaticToolsSys_1// "/_static/tools/systemcustomization/scri"...
0xaa09b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xaa0a0  ldarg.0
0xaa0a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa0a6  ldstr    aStaticToolsSys_20// "/_static/tools/systemcustomization/opti"...
0xaa0ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xaa0b0  ldarg.0
0xaa0b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa0b6  ldstr    aStaticToolsDep// "/_static/tools/dependency/scripts/depen"...
0xaa0bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xaa0c0  ldarg.0
0xaa0c1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa0c6  ldstr    aStaticToolsSol// "/_static/tools/solution/scripts/Managed"...
0xaa0cb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xaa0d0  ldarg.0
0xaa0d1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa0d6  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0xaa0db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xaa0e0  ldarg.0
0xaa0e1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa0e6  ldstr    aBcreate// "_bCreate"
0xaa0eb  ldarg.0
0xaa0ec  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.OptionSet.OptionSetPage::_mode
0xaa0f1  ldc.i4.0
0xaa0f2  ceq
0xaa0f4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xaa0f9  ldarg.0
0xaa0fa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa0ff  ldstr    aSpicklistedito// "sPicklistEditorUrlFormat"
0xaa104  ldstr    aOptionsetAspxI// "optionset.aspx?id={0}"
0xaa109  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xaa10e  ldarg.0
0xaa10f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa114  ldstr    aOptionsetid// "_optionSetId"
0xaa119  ldarg.0
0xaa11a  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Web.Tools.SystemCustomization.OptionSet.OptionSetPage::OptionSetId
0xaa11f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xaa124  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0xaa129  brtrue.s loc_AA13D
0xaa12b  ldarg.0
0xaa12c  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Web.Tools.SystemCustomization.OptionSet.OptionSetPage::OptionSetId
0xaa131  ldstr    aB// "B"
0xaa136  call     instance string [mscorlib]System.Guid::ToString(string)
0xaa13b  br.s     loc_AA142
0xaa13d  ldstr    asc_11EF2A// ""
0xaa142  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xaa147  ldarg.0
0xaa148  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa14d  ldstr    aBisbooleanopti// "_bIsBooleanOptionSet"
0xaa152  ldarg.0
0xaa153  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata Microsoft.Crm.Web.Tools.SystemCustomization.OptionSet.OptionSetPage::optionSetMeta
0xaa158  brfalse.s loc_AA16A
0xaa15a  ldarg.0
0xaa15b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata Microsoft.Crm.Web.Tools.SystemCustomization.OptionSet.OptionSetPage::optionSetMeta
0xaa160  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetMetadata::get_OptionSetType()
0xaa165  ldc.i4.3
0xaa166  ceq
0xaa168  br.s     loc_AA16B
0xaa16a  ldc.i4.0
0xaa16b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xaa170  ldarg.0
0xaa171  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa176  ldstr    aBview// "_bView"
0xaa17b  ldarg.0
0xaa17c  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.OptionSet.OptionSetPage::_mode
0xaa181  ldc.i4.2
0xaa182  ceq
0xaa184  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xaa189  ldarg.0
0xaa18a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa18f  ldstr    aLocidMultiCrea// "LOCID_MULTI_CREATINGSET"
0xaa194  ldarg.0
0xaa195  ldstr    aMessagesCreati_0// "Messages.CreatingSet"
0xaa19a  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.OptionSet.OptionSetPage::GetString(string name)
0xaa19f  ldc.i4.0
0xaa1a0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xaa1a5  ldarg.0
0xaa1a6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa1ab  ldstr    aLocidMultiUpda// "LOCID_MULTI_UPDATESET"
0xaa1b0  ldarg.0
0xaa1b1  ldstr    aMessagesDeleti// "Messages.DeletingSet"
0xaa1b6  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.OptionSet.OptionSetPage::GetString(string name)
0xaa1bb  ldc.i4.0
0xaa1bc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xaa1c1  ldarg.0
0xaa1c2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa1c7  ldstr    aLocidMultiDele// "LOCID_MULTI_DELETESET"
0xaa1cc  ldarg.0
0xaa1cd  ldstr    aMessagesUpdati// "Messages.UpdatingSet"
0xaa1d2  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.OptionSet.OptionSetPage::GetString(string name)
0xaa1d7  ldc.i4.0
0xaa1d8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xaa1dd  ldarg.0
0xaa1de  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa1e3  ldstr    aLocidSyscustCa// "LOCID_SYSCUST_CANTBEBLANK"
0xaa1e8  ldarg.0
0xaa1e9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaa1ee  ldstr    aSystemcustomiz_11// "SystemCustomization.Validation.Errors.C"...
0xaa1f3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaa1f8  ldc.i4.0
0xaa1f9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xaa1fe  ldarg.0
0xaa1ff  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa204  ldstr    aLocidSyscustIn// "LOCID_SYSCUST_INVALCHARS"
0xaa209  ldarg.0
0xaa20a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaa20f  ldstr    aSystemcustomiz_12// "SystemCustomization.Validation.Errors.C"...
0xaa214  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaa219  ldc.i4.0
0xaa21a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xaa21f  ldarg.0
0xaa220  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa225  ldstr    aLocidSyscustAl// "LOCID_SYSCUST_ALPHANUMSONLY"
0xaa22a  ldarg.0
0xaa22b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaa230  ldstr    aSystemcustomiz_13// "SystemCustomization.Validation.Errors.C"...
0xaa235  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaa23a  ldc.i4.0
0xaa23b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xaa240  ldarg.0
0xaa241  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa246  ldstr    aLocidOptionset// "LOCID_OPTIONSET_PUBLISHING"
0xaa24b  ldarg.0
0xaa24c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaa251  ldstr    aSolutionSoluti_0// "Solution.SolutionComponent.OptionSet.Me"...
0xaa256  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaa25b  ldc.i4.0
0xaa25c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xaa261  ldarg.0
0xaa262  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa267  ldstr    aLocidOptionset_0// "LOCID_OPTIONSET_PUBLISHUNSAVED"
0xaa26c  ldarg.0
0xaa26d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaa272  ldstr    aSolutionSoluti_5// "Solution.SolutionComponent.OptionSet.Me"...
0xaa277  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaa27c  ldc.i4.0
0xaa27d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xaa282  ldarg.0
0xaa283  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa288  ldstr    aLocidAttrutlCa// "LOCID_ATTRUTL_CANTDELSYSATTR"
0xaa28d  ldarg.0
0xaa28e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaa293  ldstr    aSystemcustomiz_405// "SystemCustomization.AttributeUtil.Messa"...
0xaa298  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaa29d  ldc.i4.0
0xaa29e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xaa2a3  ldarg.0
0xaa2a4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa2a9  ldstr    aLocidAttrutlCo// "LOCID_ATTRUTL_CONFIRMDELATTR"
0xaa2ae  ldarg.0
0xaa2af  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaa2b4  ldstr    aSystemcustomiz_406// "SystemCustomization.AttributeUtil.Messa"...
0xaa2b9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaa2be  ldc.i4.0
0xaa2bf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xaa2c4  ldarg.0
0xaa2c5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa2ca  ldstr    aLocidAttrutlCr// "LOCID_ATTRUTL_CREATINGATTR"
0xaa2cf  ldarg.0
0xaa2d0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaa2d5  ldstr    aSystemcustomiz_407// "SystemCustomization.AttributeUtil.Messa"...
0xaa2da  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaa2df  ldc.i4.0
0xaa2e0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xaa2e5  ldarg.0
0xaa2e6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa2eb  ldstr    aLocidAttrutlUp// "LOCID_ATTRUTL_UPDATINGATTR"
0xaa2f0  ldarg.0
0xaa2f1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaa2f6  ldstr    aSystemcustomiz_408// "SystemCustomization.AttributeUtil.Messa"...
0xaa2fb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaa300  ldc.i4.0
0xaa301  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xaa306  ldarg.0
0xaa307  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa30c  ldstr    aLocidAttrutlDe// "LOCID_ATTRUTL_DELETINGATTR"
0xaa311  ldarg.0
0xaa312  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xaa317  ldstr    aSystemcustomiz_409// "SystemCustomization.AttributeUtil.Messa"...
0xaa31c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaa321  ldc.i4.0
0xaa322  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xaa327  ldarg.0
0xaa328  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaa32d  ldstr    aSysApplication_3// "Sys.Application.add_load(function() {Ms"...
0xaa332  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptStatementForInit(string)
0xaa337  ldarg.0
0xaa338  ldstr    aTxtdisplayname// "txtDisplayNameLabel"
0xaa33d  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.OptionSet.OptionSetPage::AddAutoToolTipControl(string elementId)
0xaa342  ldarg.0
0xaa343  ldstr    aTxtschemanamel// "txtSchemaNameLabel"
0xaa348  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.OptionSet.OptionSetPage::AddAutoToolTipControl(string elementId)
0xaa34d  ldarg.0
0xaa34e  ldstr    aTdledtpicklist// "tdledtPicklistValues_txtItemLb"
0xaa353  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.OptionSet.OptionSetPage::AddAutoToolTipControl(string elementId)
0xaa358  ldarg.0
0xaa359  ldstr    aTdledtpicklist_0// "tdledtPicklistValues_txtItemVal"
0xaa35e  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.OptionSet.OptionSetPage::AddAutoToolTipControl(string elementId)
0xaa363  ret
```
