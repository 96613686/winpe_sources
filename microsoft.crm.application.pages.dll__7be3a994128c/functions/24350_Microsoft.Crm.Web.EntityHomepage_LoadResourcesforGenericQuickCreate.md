# Microsoft.Crm.Web.EntityHomepage::LoadResourcesforGenericQuickCreate

- ea: `0x24350`
- end: `0x243d1`
- name: `Microsoft.Crm.Web.EntityHomepage::LoadResourcesforGenericQuickCreate`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x23ac0`

## string_xrefs

- `0x24356`: `LOCID_SAVE_GLOBAL_QUICKCREATE`
- `0x24360`: `QuickCreateSaveButtonText`
- `0x24376`: `LOCID_CANCEL_GLOBAL_QUICKCREATE`
- `0x24380`: `QuickCreateCancelButtonText`
- `0x24396`: `LOCID_CLOSE_GLOBAL_QUICKCREATE`
- `0x243a0`: `RefreshForm_CloseGlobalQuickCreate`
- `0x243b6`: `LOCID_TITLE_GLOBAL_QUICKCREATE`
- `0x243c0`: `QuickCreate_TitlePrefix`

## pseudocode

```c

```

## disassembly

```asm
0x24350  ldarg.0
0x24351  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x24356  ldstr    aLocidSaveGloba// "LOCID_SAVE_GLOBAL_QUICKCREATE"
0x2435b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24360  ldstr    aQuickcreatesav// "QuickCreateSaveButtonText"
0x24365  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2436a  ldc.i4.0
0x2436b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x24370  ldarg.0
0x24371  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x24376  ldstr    aLocidCancelGlo// "LOCID_CANCEL_GLOBAL_QUICKCREATE"
0x2437b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24380  ldstr    aQuickcreatecan// "QuickCreateCancelButtonText"
0x24385  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2438a  ldc.i4.0
0x2438b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x24390  ldarg.0
0x24391  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x24396  ldstr    aLocidCloseGlob// "LOCID_CLOSE_GLOBAL_QUICKCREATE"
0x2439b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x243a0  ldstr    aRefreshformClo// "RefreshForm_CloseGlobalQuickCreate"
0x243a5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x243aa  ldc.i4.0
0x243ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x243b0  ldarg.0
0x243b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x243b6  ldstr    aLocidTitleGlob// "LOCID_TITLE_GLOBAL_QUICKCREATE"
0x243bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x243c0  ldstr    aQuickcreateTit// "QuickCreate_TitlePrefix"
0x243c5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x243ca  ldc.i4.0
0x243cb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x243d0  ret
```
