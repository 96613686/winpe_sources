# Microsoft.Crm.Application.Controls.WebResourceDependencyControl::ConfigureHeader

- ea: `0x9ab30`
- end: `0x9accd`
- name: `Microsoft.Crm.Application.Controls.WebResourceDependencyControl::ConfigureHeader`
- size: `413`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x9a9a0`

## string_xrefs

- `0x9ac23`: `LOCID_WR_REMOVE_LIBRARY_WARNING`
- `0x9ac2e`: `WebResource_Remove_Library_Warning`
- `0x9ac44`: `LOCID_WR_REMOVE_ATRIBUTE_WARNING`
- `0x9ac4f`: `WebResource_Remove_Atribute_Warning`

## pseudocode

```c

```

## disassembly

```asm
0x9ab30  ldarg.0
0x9ab31  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x9ab36  ldarg.0
0x9ab37  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9ab3c  ldstr    aLocidNameParam// "LOCID_NAME_PARAM"
0x9ab41  ldarg.0
0x9ab42  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_resourceManager
0x9ab47  ldstr    aFormLibrariesA_25// "Form_Libraries_And_Event_Handler_Contro"...
0x9ab4c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ab51  ldc.i4.0
0x9ab52  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ab57  ldarg.0
0x9ab58  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9ab5d  ldstr    aLocidDisplayNa// "LOCID_DISPLAY_NAME_PARAM"
0x9ab62  ldarg.0
0x9ab63  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_resourceManager
0x9ab68  ldstr    aFormLibrariesA_26// "Form_Libraries_And_Event_Handler_Contro"...
0x9ab6d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ab72  ldc.i4.0
0x9ab73  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ab78  ldarg.0
0x9ab79  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9ab7e  ldstr    aLocidLanguagec// "LOCID_LANGUAGECODE_PARAM"
0x9ab83  ldarg.0
0x9ab84  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_resourceManager
0x9ab89  ldstr    aFormLibrariesA_37// "Form_Libraries_And_Event_Handler_Contro"...
0x9ab8e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ab93  ldc.i4.0
0x9ab94  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ab99  ldarg.0
0x9ab9a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9ab9f  ldstr    aLocidDescripti// "LOCID_DESCRIPTION_PARAM"
0x9aba4  ldarg.0
0x9aba5  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_resourceManager
0x9abaa  ldstr    aFormLibrariesA_27// "Form_Libraries_And_Event_Handler_Contro"...
0x9abaf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9abb4  ldc.i4.0
0x9abb5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9abba  ldarg.0
0x9abbb  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9abc0  ldstr    aLocidLibraryNa// "LOCID_LIBRARY_NAME_PARAM"
0x9abc5  ldarg.0
0x9abc6  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_resourceManager
0x9abcb  ldstr    aFormLibrariesA_28// "Form_Libraries_And_Event_Handler_Contro"...
0x9abd0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9abd5  ldc.i4.0
0x9abd6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9abdb  ldarg.0
0x9abdc  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9abe1  ldstr    aLocidFunctionN// "LOCID_FUNCTION_NAME_PARAM"
0x9abe6  ldarg.0
0x9abe7  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_resourceManager
0x9abec  ldstr    aFormLibrariesA_29// "Form_Libraries_And_Event_Handler_Contro"...
0x9abf1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9abf6  ldc.i4.0
0x9abf7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9abfc  ldarg.0
0x9abfd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9ac02  ldstr    aLocidEnabledPa// "LOCID_ENABLED_PARAM"
0x9ac07  ldarg.0
0x9ac08  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_resourceManager
0x9ac0d  ldstr    aFormLibrariesA_30// "Form_Libraries_And_Event_Handler_Contro"...
0x9ac12  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ac17  ldc.i4.0
0x9ac18  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ac1d  ldarg.0
0x9ac1e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9ac23  ldstr    aLocidWrRemoveL// "LOCID_WR_REMOVE_LIBRARY_WARNING"
0x9ac28  ldarg.0
0x9ac29  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_resourceManager
0x9ac2e  ldstr    aWebresourceRem// "WebResource_Remove_Library_Warning"
0x9ac33  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ac38  ldc.i4.0
0x9ac39  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ac3e  ldarg.0
0x9ac3f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9ac44  ldstr    aLocidWrRemoveA// "LOCID_WR_REMOVE_ATRIBUTE_WARNING"
0x9ac49  ldarg.0
0x9ac4a  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_resourceManager
0x9ac4f  ldstr    aWebresourceRem_0// "WebResource_Remove_Atribute_Warning"
0x9ac54  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ac59  ldc.i4.0
0x9ac5a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ac5f  ldarg.0
0x9ac60  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9ac65  ldstr    aLocidHandlerEn// "LOCID_HANDLER_ENABLED_TRUE"
0x9ac6a  ldarg.0
0x9ac6b  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_resourceManager
0x9ac70  ldstr    aJslibraryContr// "JSLibrary_Control_Handler_Enabled_State"...
0x9ac75  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ac7a  ldc.i4.0
0x9ac7b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ac80  ldarg.0
0x9ac81  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9ac86  ldstr    aLocidHandlerEn_0// "LOCID_HANDLER_ENABLED_FALSE"
0x9ac8b  ldarg.0
0x9ac8c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_resourceManager
0x9ac91  ldstr    aJslibraryContr_0// "JSLibrary_Control_Handler_Enabled_State"...
0x9ac96  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ac9b  ldc.i4.0
0x9ac9c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9aca1  ldarg.0
0x9aca2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9aca7  ldstr    aToolsFormedito_3// "/tools/formeditor/styles/dialogs.css.as"...
0x9acac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9acb1  ldarg.0
0x9acb2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9acb7  ldstr    aStaticToolsFor// "/_static/tools/formeditor/scripts/FormE"...
0x9acbc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9acc1  ldarg.0
0x9acc2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.WebResourceDependencyControl::get_WebResourceLibraryMenuBar()
0x9acc7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x9accc  ret
```
