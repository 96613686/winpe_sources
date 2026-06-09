# Microsoft.Crm.Application.Controls.AttributeDependencyControl::ConfigureHeader

- ea: `0x9ae70`
- end: `0x9b04f`
- name: `Microsoft.Crm.Application.Controls.AttributeDependencyControl::ConfigureHeader`
- size: `479`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x9ad20`

## string_xrefs

- `0x9afa5`: `LOCID_WR_REMOVE_LIBRARY_WARNING`
- `0x9afb0`: `WebResource_Remove_Library_Warning`
- `0x9afc6`: `LOCID_WR_REMOVE_ATRIBUTE_WARNING`
- `0x9afd1`: `WebResource_Remove_Atribute_Warning`

## pseudocode

```c

```

## disassembly

```asm
0x9ae70  ldarg.0
0x9ae71  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x9ae76  ldarg.0
0x9ae77  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9ae7c  ldstr    aLocidNameParam// "LOCID_NAME_PARAM"
0x9ae81  ldarg.0
0x9ae82  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AttributeDependencyControl::_resourceManager
0x9ae87  ldstr    aFormLibrariesA_25// "Form_Libraries_And_Event_Handler_Contro"...
0x9ae8c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ae91  ldc.i4.0
0x9ae92  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9ae97  ldarg.0
0x9ae98  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9ae9d  ldstr    aLocidDisplayNa// "LOCID_DISPLAY_NAME_PARAM"
0x9aea2  ldarg.0
0x9aea3  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AttributeDependencyControl::_resourceManager
0x9aea8  ldstr    aFormLibrariesA_26// "Form_Libraries_And_Event_Handler_Contro"...
0x9aead  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9aeb2  ldc.i4.0
0x9aeb3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9aeb8  ldarg.0
0x9aeb9  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9aebe  ldstr    aLocidLanguagec// "LOCID_LANGUAGECODE_PARAM"
0x9aec3  ldarg.0
0x9aec4  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AttributeDependencyControl::_resourceManager
0x9aec9  ldstr    aFormLibrariesA_37// "Form_Libraries_And_Event_Handler_Contro"...
0x9aece  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9aed3  ldc.i4.0
0x9aed4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9aed9  ldarg.0
0x9aeda  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9aedf  ldstr    aLocidDescripti// "LOCID_DESCRIPTION_PARAM"
0x9aee4  ldarg.0
0x9aee5  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AttributeDependencyControl::_resourceManager
0x9aeea  ldstr    aFormLibrariesA_27// "Form_Libraries_And_Event_Handler_Contro"...
0x9aeef  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9aef4  ldc.i4.0
0x9aef5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9aefa  ldarg.0
0x9aefb  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9af00  ldstr    aLocidLibraryNa// "LOCID_LIBRARY_NAME_PARAM"
0x9af05  ldarg.0
0x9af06  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AttributeDependencyControl::_resourceManager
0x9af0b  ldstr    aFormLibrariesA_28// "Form_Libraries_And_Event_Handler_Contro"...
0x9af10  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9af15  ldc.i4.0
0x9af16  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9af1b  ldarg.0
0x9af1c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9af21  ldstr    aLocidFunctionN// "LOCID_FUNCTION_NAME_PARAM"
0x9af26  ldarg.0
0x9af27  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AttributeDependencyControl::_resourceManager
0x9af2c  ldstr    aFormLibrariesA_29// "Form_Libraries_And_Event_Handler_Contro"...
0x9af31  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9af36  ldc.i4.0
0x9af37  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9af3c  ldarg.0
0x9af3d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9af42  ldstr    aLocidEnabledPa// "LOCID_ENABLED_PARAM"
0x9af47  ldarg.0
0x9af48  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AttributeDependencyControl::_resourceManager
0x9af4d  ldstr    aFormLibrariesA_30// "Form_Libraries_And_Event_Handler_Contro"...
0x9af52  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9af57  ldc.i4.0
0x9af58  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9af5d  ldarg.0
0x9af5e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9af63  ldstr    aLocidAttribute// "LOCID_ATTRIBUTENAME_PARAM"
0x9af68  ldarg.0
0x9af69  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AttributeDependencyControl::_resourceManager
0x9af6e  ldstr    aFormLibrariesA_38// "Form_Libraries_And_Event_Handler_Contro"...
0x9af73  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9af78  ldc.i4.0
0x9af79  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9af7e  ldarg.0
0x9af7f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9af84  ldstr    aLocidEntityPar// "LOCID_ENTITY_PARAM"
0x9af89  ldarg.0
0x9af8a  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AttributeDependencyControl::_resourceManager
0x9af8f  ldstr    aFormLibrariesA_39// "Form_Libraries_And_Event_Handler_Contro"...
0x9af94  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9af99  ldc.i4.0
0x9af9a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9af9f  ldarg.0
0x9afa0  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9afa5  ldstr    aLocidWrRemoveL// "LOCID_WR_REMOVE_LIBRARY_WARNING"
0x9afaa  ldarg.0
0x9afab  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AttributeDependencyControl::_resourceManager
0x9afb0  ldstr    aWebresourceRem// "WebResource_Remove_Library_Warning"
0x9afb5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9afba  ldc.i4.0
0x9afbb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9afc0  ldarg.0
0x9afc1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9afc6  ldstr    aLocidWrRemoveA// "LOCID_WR_REMOVE_ATRIBUTE_WARNING"
0x9afcb  ldarg.0
0x9afcc  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AttributeDependencyControl::_resourceManager
0x9afd1  ldstr    aWebresourceRem_0// "WebResource_Remove_Atribute_Warning"
0x9afd6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9afdb  ldc.i4.0
0x9afdc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9afe1  ldarg.0
0x9afe2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9afe7  ldstr    aLocidHandlerEn// "LOCID_HANDLER_ENABLED_TRUE"
0x9afec  ldarg.0
0x9afed  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AttributeDependencyControl::_resourceManager
0x9aff2  ldstr    aJslibraryContr// "JSLibrary_Control_Handler_Enabled_State"...
0x9aff7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9affc  ldc.i4.0
0x9affd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9b002  ldarg.0
0x9b003  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9b008  ldstr    aLocidHandlerEn_0// "LOCID_HANDLER_ENABLED_FALSE"
0x9b00d  ldarg.0
0x9b00e  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AttributeDependencyControl::_resourceManager
0x9b013  ldstr    aJslibraryContr_0// "JSLibrary_Control_Handler_Enabled_State"...
0x9b018  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9b01d  ldc.i4.0
0x9b01e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9b023  ldarg.0
0x9b024  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9b029  ldstr    aToolsFormedito_3// "/tools/formeditor/styles/dialogs.css.as"...
0x9b02e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9b033  ldarg.0
0x9b034  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9b039  ldstr    aStaticToolsFor// "/_static/tools/formeditor/scripts/FormE"...
0x9b03e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9b043  ldarg.0
0x9b044  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.AttributeDependencyControl::get_WebResourceLibraryMenuBar()
0x9b049  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x9b04e  ret
```
