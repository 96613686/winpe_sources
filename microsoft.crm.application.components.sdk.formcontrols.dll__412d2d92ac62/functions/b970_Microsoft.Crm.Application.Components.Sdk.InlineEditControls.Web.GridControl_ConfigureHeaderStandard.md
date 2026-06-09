# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::ConfigureHeaderStandard

- ea: `0xb970`
- end: `0xbb0f`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::ConfigureHeaderStandard`
- size: `415`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0xb970`
- `0xe480`
- `0x17b10`

## string_xrefs

- `0xb9a4`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0xb97c`: `/_static/_common/scripts/InlineEditCommon.js`
- `0xb98c`: `/_static/_controls/GlobalQuickCreate/GlobalQuickCreateBehavior.js`
- `0xb9b4`: `/_static/_common/scripts/Mscrm.Caching.js`
- `0xba04`: `/_static/_controls/ReadForm/ReadFormUtilities.js`
- `0xba14`: `LOCID_CLOSE_GLOBAL_QUICKCREATE`
- `0xba1e`: `RefreshForm_CloseGlobalQuickCreate`
- `0xba34`: `LOCID_SAVE_GLOBAL_QUICKCREATE`
- `0xba3e`: `QuickCreateSaveButtonText`
- `0xba54`: `LOCID_CANCEL_GLOBAL_QUICKCREATE`
- `0xba5e`: `QuickCreateCancelButtonText`
- `0xba74`: `LOCID_TITLE_GLOBAL_QUICKCREATE`
- `0xba7e`: `QuickCreate_TitlePrefix`
- `0xbab4`: `LOCID_FLYOUT_WRITEINPRODUCT`
- `0xbabe`: `FlyOut_WriteInProduct`

## pseudocode

```c

```

## disassembly

```asm
0xb970  ldarg.0
0xb971  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::ConfigureHeaderStandard()
0xb976  ldarg.0
0xb977  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb97c  ldstr    aStaticCommonSc_6// "/_static/_common/scripts/InlineEditComm"...
0xb981  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb986  ldarg.0
0xb987  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb98c  ldstr    aStaticControls_8// "/_static/_controls/GlobalQuickCreate/Gl"...
0xb991  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb996  ldarg.0
0xb997  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::IsAssociatedGrid()
0xb99c  brfalse.s loc_BA0E
0xb99e  ldarg.0
0xb99f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb9a4  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/CrmInternalUti"...
0xb9a9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb9ae  ldarg.0
0xb9af  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb9b4  ldstr    aStaticCommonSc_7// "/_static/_common/scripts/Mscrm.Caching."...
0xb9b9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb9be  ldarg.0
0xb9bf  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb9c4  ldstr    aStaticFormsLoo// "/_static/_forms/LookupBehavior.js"
0xb9c9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb9ce  ldarg.0
0xb9cf  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb9d4  ldstr    aStaticControls_9// "/_static/_controls/FlyoutDialog/FlyoutD"...
0xb9d9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb9de  ldarg.0
0xb9df  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb9e4  ldstr    aStaticControls_10// "/_static/_controls/inlineedit/InlineEdi"...
0xb9e9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb9ee  ldarg.0
0xb9ef  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb9f4  ldstr    aStaticControls_11// "/_static/_controls/inlineedit/inlineedi"...
0xb9f9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb9fe  ldarg.0
0xb9ff  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xba04  ldstr    aStaticControls_12// "/_static/_controls/ReadForm/ReadFormUti"...
0xba09  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xba0e  ldarg.0
0xba0f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xba14  ldstr    aLocidCloseGlob// "LOCID_CLOSE_GLOBAL_QUICKCREATE"
0xba19  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xba1e  ldstr    aRefreshformClo// "RefreshForm_CloseGlobalQuickCreate"
0xba23  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xba28  ldc.i4.0
0xba29  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xba2e  ldarg.0
0xba2f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xba34  ldstr    aLocidSaveGloba// "LOCID_SAVE_GLOBAL_QUICKCREATE"
0xba39  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xba3e  ldstr    aQuickcreatesav// "QuickCreateSaveButtonText"
0xba43  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xba48  ldc.i4.0
0xba49  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xba4e  ldarg.0
0xba4f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xba54  ldstr    aLocidCancelGlo// "LOCID_CANCEL_GLOBAL_QUICKCREATE"
0xba59  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xba5e  ldstr    aQuickcreatecan// "QuickCreateCancelButtonText"
0xba63  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xba68  ldc.i4.0
0xba69  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xba6e  ldarg.0
0xba6f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xba74  ldstr    aLocidTitleGlob// "LOCID_TITLE_GLOBAL_QUICKCREATE"
0xba79  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xba7e  ldstr    aQuickcreateTit// "QuickCreate_TitlePrefix"
0xba83  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xba88  ldc.i4.0
0xba89  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xba8e  ldarg.0
0xba8f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xba94  ldstr    aLocidFlyoutExi// "LOCID_FLYOUT_EXISTINGPRODUCT"
0xba99  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xba9e  ldstr    aFlyoutExisting// "FlyOut_ExistingProduct"
0xbaa3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbaa8  ldc.i4.0
0xbaa9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbaae  ldarg.0
0xbaaf  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xbab4  ldstr    aLocidFlyoutWri// "LOCID_FLYOUT_WRITEINPRODUCT"
0xbab9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xbabe  ldstr    aFlyoutWriteinp// "FlyOut_WriteInProduct"
0xbac3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbac8  ldc.i4.0
0xbac9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbace  ldarg.0
0xbacf  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xbad4  ldstr    aLocidFlyoutGet// "LOCID_FLYOUT_GETPRODUCTS"
0xbad9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xbade  ldstr    aFlyoutGetprodu// "FlyOut_GetProducts"
0xbae3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbae8  ldc.i4.0
0xbae9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbaee  ldarg.0
0xbaef  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xbaf4  ldstr    aLocidOfflineAd// "LOCID_OFFLINE_ADD_RECORD"
0xbaf9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xbafe  ldstr    aOfflineCannotA// "Offline_Cannot_Add_Record"
0xbb03  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbb08  ldc.i4.0
0xbb09  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbb0e  ret
```
