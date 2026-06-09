# Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::ConfigureHeader

- ea: `0x9a530`
- end: `0x9a93d`
- name: `Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::ConfigureHeader`
- size: `1037`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x99910`
- `0x99920`
- `0x99930`
- `0x99940`
- `0x99950`
- `0x99960`
- `0x99a70`
- `0x9a530`

## string_xrefs

- `0x9a5e1`: `LOCID_ONSTATE_COMPLETE_EVENT`
- `0x9a5ec`: `Form_Libraries_And_Event_Handler_Control_OnReadyStateComplete_Event_Label`
- `0x9a7ba`: `Form_Editor_Command_Group_Fields`
- `0x9a7db`: `Form_Editor_Command_Group_Grids`
- `0x9a81d`: `Form_Editor_Command_Group_Tabs`
- `0x9a875`: `LOCID_REMOVE_HANDLER_WARNING`
- `0x9a880`: `Form_Libraries_And_Event_Handler_Control_Remove_Handler_Warning`
- `0x9a896`: `LOCID_REMOVE_LIBRARY_WARNING`
- `0x9a8a1`: `Form_Libraries_And_Event_Handler_Control_Remove_Library_Warning`

## pseudocode

```c

```

## disassembly

```asm
0x9a530  ldarg.0
0x9a531  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x9a536  ldarg.0
0x9a537  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a53c  ldstr    aLocidDataevent// "LOCID_DATAEVENTS_LABEL"
0x9a541  ldarg.0
0x9a542  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a547  ldstr    aFormLibrariesA_15// "Form_Libraries_And_Event_Handler_Contro"...
0x9a54c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a551  ldc.i4.0
0x9a552  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a557  ldarg.0
0x9a558  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a55d  ldstr    aLocidUieventsL// "LOCID_UIEVENTS_LABEL"
0x9a562  ldarg.0
0x9a563  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a568  ldstr    aFormLibrariesA_16// "Form_Libraries_And_Event_Handler_Contro"...
0x9a56d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a572  ldc.i4.0
0x9a573  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a578  ldarg.0
0x9a579  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a57e  ldstr    aLocidOnloadEve// "LOCID_ONLOAD_EVENT_LABEL"
0x9a583  ldarg.0
0x9a584  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a589  ldstr    aFormLibrariesA_17// "Form_Libraries_And_Event_Handler_Contro"...
0x9a58e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a593  ldc.i4.0
0x9a594  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a599  ldarg.0
0x9a59a  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a59f  ldstr    aLocidOnchangeE// "LOCID_ONCHANGE_EVENT_LABEL"
0x9a5a4  ldarg.0
0x9a5a5  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a5aa  ldstr    aFormLibrariesA_18// "Form_Libraries_And_Event_Handler_Contro"...
0x9a5af  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a5b4  ldc.i4.0
0x9a5b5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a5ba  ldarg.0
0x9a5bb  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a5c0  ldstr    aLocidOnrecords// "LOCID_ONRECORDSELECT_EVENT_LABEL"
0x9a5c5  ldarg.0
0x9a5c6  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a5cb  ldstr    aFormLibrariesA_19// "Form_Libraries_And_Event_Handler_Contro"...
0x9a5d0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a5d5  ldc.i4.0
0x9a5d6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a5db  ldarg.0
0x9a5dc  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a5e1  ldstr    aLocidOnstateCo// "LOCID_ONSTATE_COMPLETE_EVENT"
0x9a5e6  ldarg.0
0x9a5e7  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a5ec  ldstr    aFormLibrariesA_20// "Form_Libraries_And_Event_Handler_Contro"...
0x9a5f1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a5f6  ldc.i4.0
0x9a5f7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a5fc  ldarg.0
0x9a5fd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a602  ldstr    aLocidOntabStat// "LOCID_ONTAB_STATE_CHANGE"
0x9a607  ldarg.0
0x9a608  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a60d  ldstr    aFormLibrariesA// "Form_Libraries_And_Event_Handler_Contro"...
0x9a612  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a617  ldc.i4.0
0x9a618  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a61d  ldarg.0
0x9a61e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a623  ldstr    aLocidOnsaveEve// "LOCID_ONSAVE_EVENT_LABEL"
0x9a628  ldarg.0
0x9a629  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a62e  ldstr    aFormLibrariesA_21// "Form_Libraries_And_Event_Handler_Contro"...
0x9a633  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a638  ldc.i4.0
0x9a639  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a63e  ldarg.0
0x9a63f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a644  ldstr    aLocidHomegridL// "LOCID_HOMEGRID_LIBRARIES_LABEL"
0x9a649  ldarg.0
0x9a64a  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a64f  ldstr    aFormLibrariesA_22// "Form_Libraries_And_Event_Handler_Contro"...
0x9a654  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a659  ldc.i4.0
0x9a65a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a65f  ldarg.0
0x9a660  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a665  ldstr    aLocidHomegridE// "LOCID_HOMEGRID_EVENTS_LABEL"
0x9a66a  ldarg.0
0x9a66b  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a670  ldstr    aFormLibrariesA_23// "Form_Libraries_And_Event_Handler_Contro"...
0x9a675  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a67a  ldc.i4.0
0x9a67b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a680  ldarg.0
0x9a681  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a686  ldstr    aLocidEgcContro// "LOCID_EGC_CONTROL_LABEL"
0x9a68b  ldarg.0
0x9a68c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a691  ldstr    aFormLibrariesA_24// "Form_Libraries_And_Event_Handler_Contro"...
0x9a696  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a69b  ldc.i4.0
0x9a69c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a6a1  ldarg.0
0x9a6a2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a6a7  ldstr    aLocidNameParam// "LOCID_NAME_PARAM"
0x9a6ac  ldarg.0
0x9a6ad  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a6b2  ldstr    aFormLibrariesA_25// "Form_Libraries_And_Event_Handler_Contro"...
0x9a6b7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a6bc  ldc.i4.0
0x9a6bd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a6c2  ldarg.0
0x9a6c3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a6c8  ldstr    aLocidDisplayNa// "LOCID_DISPLAY_NAME_PARAM"
0x9a6cd  ldarg.0
0x9a6ce  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a6d3  ldstr    aFormLibrariesA_26// "Form_Libraries_And_Event_Handler_Contro"...
0x9a6d8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a6dd  ldc.i4.0
0x9a6de  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a6e3  ldarg.0
0x9a6e4  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a6e9  ldstr    aLocidDescripti// "LOCID_DESCRIPTION_PARAM"
0x9a6ee  ldarg.0
0x9a6ef  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a6f4  ldstr    aFormLibrariesA_27// "Form_Libraries_And_Event_Handler_Contro"...
0x9a6f9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a6fe  ldc.i4.0
0x9a6ff  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a704  ldarg.0
0x9a705  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a70a  ldstr    aLocidLibraryNa// "LOCID_LIBRARY_NAME_PARAM"
0x9a70f  ldarg.0
0x9a710  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a715  ldstr    aFormLibrariesA_28// "Form_Libraries_And_Event_Handler_Contro"...
0x9a71a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a71f  ldc.i4.0
0x9a720  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a725  ldarg.0
0x9a726  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a72b  ldstr    aLocidFunctionN// "LOCID_FUNCTION_NAME_PARAM"
0x9a730  ldarg.0
0x9a731  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a736  ldstr    aFormLibrariesA_29// "Form_Libraries_And_Event_Handler_Contro"...
0x9a73b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a740  ldc.i4.0
0x9a741  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a746  ldarg.0
0x9a747  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a74c  ldstr    aLocidEnabledPa// "LOCID_ENABLED_PARAM"
0x9a751  ldarg.0
0x9a752  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a757  ldstr    aFormLibrariesA_30// "Form_Libraries_And_Event_Handler_Contro"...
0x9a75c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a761  ldc.i4.0
0x9a762  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a767  ldarg.0
0x9a768  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a76d  ldstr    aLocidMaxLibrar// "LOCID_MAX_LIBRARIES_MESSAGE"
0x9a772  ldarg.0
0x9a773  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a778  ldstr    aFormLibrariesA_31// "Form_Libraries_And_Event_Handler_Contro"...
0x9a77d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a782  ldc.i4.0
0x9a783  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a788  ldarg.0
0x9a789  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a78e  ldstr    aLocidMaxHandle// "LOCID_MAX_HANDLERS_MESSAGE"
0x9a793  ldarg.0
0x9a794  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a799  ldstr    aFormLibrariesA_32// "Form_Libraries_And_Event_Handler_Contro"...
0x9a79e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a7a3  ldc.i4.0
0x9a7a4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a7a9  ldarg.0
0x9a7aa  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a7af  ldstr    aLocidFieldsGro// "LOCID_FIELDS_GROUP_CAPTION"
0x9a7b4  ldarg.0
0x9a7b5  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a7ba  ldstr    aFormEditorComm_0// "Form_Editor_Command_Group_Fields"
0x9a7bf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a7c4  ldc.i4.0
0x9a7c5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a7ca  ldarg.0
0x9a7cb  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a7d0  ldstr    aLocidGridsGrou// "LOCID_GRIDS_GROUP_CAPTION"
0x9a7d5  ldarg.0
0x9a7d6  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a7db  ldstr    aFormEditorComm_1// "Form_Editor_Command_Group_Grids"
0x9a7e0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a7e5  ldc.i4.0
0x9a7e6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a7eb  ldarg.0
0x9a7ec  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a7f1  ldstr    aLocidFormCapti// "LOCID_FORM_CAPTION"
0x9a7f6  ldarg.0
0x9a7f7  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a7fc  ldstr    aFormLibrariesA_33// "Form_Libraries_And_Event_Handler_Contro"...
0x9a801  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a806  ldc.i4.0
0x9a807  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a80c  ldarg.0
0x9a80d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a812  ldstr    aLocidTabsGroup// "LOCID_TABS_GROUP_CAPTION"
0x9a817  ldarg.0
0x9a818  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a81d  ldstr    aFormEditorComm_2// "Form_Editor_Command_Group_Tabs"
0x9a822  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a827  ldc.i4.0
0x9a828  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a82d  ldarg.0
0x9a82e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a833  ldstr    aLocidHandlerEn// "LOCID_HANDLER_ENABLED_TRUE"
0x9a838  ldarg.0
0x9a839  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a83e  ldstr    aJslibraryContr// "JSLibrary_Control_Handler_Enabled_State"...
0x9a843  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a848  ldc.i4.0
0x9a849  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a84e  ldarg.0
0x9a84f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a854  ldstr    aLocidHandlerEn_0// "LOCID_HANDLER_ENABLED_FALSE"
0x9a859  ldarg.0
0x9a85a  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a85f  ldstr    aJslibraryContr_0// "JSLibrary_Control_Handler_Enabled_State"...
0x9a864  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a869  ldc.i4.0
0x9a86a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a86f  ldarg.0
0x9a870  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a875  ldstr    aLocidRemoveHan// "LOCID_REMOVE_HANDLER_WARNING"
0x9a87a  ldarg.0
0x9a87b  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a880  ldstr    aFormLibrariesA_34// "Form_Libraries_And_Event_Handler_Contro"...
0x9a885  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a88a  ldc.i4.0
0x9a88b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a890  ldarg.0
0x9a891  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a896  ldstr    aLocidRemoveLib// "LOCID_REMOVE_LIBRARY_WARNING"
0x9a89b  ldarg.0
0x9a89c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a8a1  ldstr    aFormLibrariesA_35// "Form_Libraries_And_Event_Handler_Contro"...
0x9a8a6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a8ab  ldc.i4.0
0x9a8ac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a8b1  ldarg.0
0x9a8b2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a8b7  ldstr    aLocidAddHandle// "LOCID_ADD_HANDLER_MESSAGE"
0x9a8bc  ldarg.0
0x9a8bd  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a8c2  ldstr    aFormLibrariesA_36// "Form_Libraries_And_Event_Handler_Contro"...
0x9a8c7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a8cc  ldc.i4.0
0x9a8cd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x9a8d2  ldarg.0
0x9a8d3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a8d8  ldstr    aStaticToolsFor// "/_static/tools/formeditor/scripts/FormE"...
0x9a8dd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x9a8e2  ldarg.0
0x9a8e3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x9a8e8  ldstr    aToolsFormedito_3// "/tools/formeditor/styles/dialogs.css.as"...
0x9a8ed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x9a8f2  ldarg.0
0x9a8f3  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::get_ControlTypeCombo()
0x9a8f8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x9a8fd  ldarg.0
0x9a8fe  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::get_EventTypeCombo()
0x9a903  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x9a908  ldarg.0
0x9a909  call     instance bool Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::get_IsJsEditableGridJsEventsEnabled()
0x9a90e  brfalse.s loc_9A926
0x9a910  ldarg.0
0x9a911  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::get_ColumnCombo()
0x9a916  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x9a91b  ldarg.0
0x9a91c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::get_EntityCombo()
0x9a921  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x9a926  ldarg.0
0x9a927  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::get_FormLibraryMenuBar()
0x9a92c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x9a931  ldarg.0
0x9a932  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::get_EventHandlerMenuBar()
0x9a937  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::SetHeaders()
0x9a93c  ret
```
