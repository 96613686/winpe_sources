# Microsoft.Crm.Controls.Footer::PrepareForRendering

- ea: `0x92a0`
- end: `0x9363`
- name: `Microsoft.Crm.Controls.Footer::PrepareForRendering`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x2ef0`
- `0x3e90`
- `0x4f20`

## string_xrefs

- `0x92e1`: `LOCID_READONLY`
- `0x92eb`: `ReadOnly`
- `0x9315`: `LOCID_TITLE_GLOBAL_QUICKCREATE`
- `0x931f`: `QuickCreate_TitlePrefix`
- `0x932f`: `LOCID_SAVE_GLOBAL_QUICKCREATE`
- `0x9339`: `QuickCreateSaveButtonText`
- `0x9349`: `LOCID_CANCEL_GLOBAL_QUICKCREATE`
- `0x9353`: `QuickCreateCancelButtonText`

## pseudocode

```c

```

## disassembly

```asm
0x92a0  ldarg.0
0x92a1  call     instance void Microsoft.Crm.Controls.PageResourceManager::PrepareForRendering()
0x92a6  ldarg.0
0x92a7  call     instance void Microsoft.Crm.Controls.PageResourceManager::AttachResourcesAndRelatedScripts()
0x92ac  ldarg.0
0x92ad  ldstr    aLocidUnsavedch// "LOCID_UNSAVEDCHANGES"
0x92b2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x92b7  ldstr    aUnsavedchanges// "UnSavedChangesWarning"
0x92bc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x92c1  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x92c6  ldarg.0
0x92c7  ldstr    aLocidSaving// "LOCID_SAVING"
0x92cc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x92d1  ldstr    aSavinginformat// "SavingInformation"
0x92d6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x92db  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x92e0  ldarg.0
0x92e1  ldstr    aLocidReadonly// "LOCID_READONLY"
0x92e6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x92eb  ldstr    aReadonly// "ReadOnly"
0x92f0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x92f5  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x92fa  ldarg.0
0x92fb  ldstr    aLocidMissingre// "LOCID_MISSINGREQUIREDFIELDS"
0x9300  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9305  ldstr    aMissingrequire// "MissingRequiredFieldsError"
0x930a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x930f  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x9314  ldarg.0
0x9315  ldstr    aLocidTitleGlob// "LOCID_TITLE_GLOBAL_QUICKCREATE"
0x931a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x931f  ldstr    aQuickcreateTit// "QuickCreate_TitlePrefix"
0x9324  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9329  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x932e  ldarg.0
0x932f  ldstr    aLocidSaveGloba// "LOCID_SAVE_GLOBAL_QUICKCREATE"
0x9334  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9339  ldstr    aQuickcreatesav// "QuickCreateSaveButtonText"
0x933e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9343  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x9348  ldarg.0
0x9349  ldstr    aLocidCancelGlo// "LOCID_CANCEL_GLOBAL_QUICKCREATE"
0x934e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9353  ldstr    aQuickcreatecan// "QuickCreateCancelButtonText"
0x9358  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x935d  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x9362  ret
```
