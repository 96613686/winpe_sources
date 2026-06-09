# Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderBase::UpdateConfigHeaderForEntityRecord_0

- ea: `0xcb0b0`
- end: `0xcb354`
- name: `Microsoft.Crm.Application.Components.EntityPageHeaders.ConfigHeaderBase::UpdateConfigHeaderForEntityRecord_0`
- size: `676`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xcaf80`
- `0xcb0a0`
- `0xcb520`
- `0xcb600`

## callees

- `0xcb0b0`

## string_xrefs

- `0xcb0e5`: `LOCID_READONLY`
- `0xcb0ef`: `ReadOnly`
- `0xcb167`: `LOCID_PROCESS_CONTROL_CONFIGURATION_MAIN_TITLE`
- `0xcb171`: `ProcessControl.Configurator.MainTitle`
- `0xcb181`: `LOCID_PROCESS_CONTROL_CONFIGURATION_HELP_BUTTON_ALT`
- `0xcb18b`: `ProcessControl.Configurator.HelpButtonAlt`
- `0xcb19b`: `LOCID_PROCESS_CONTROL_CONFIGURATION_SUB_TITLE_SALES`
- `0xcb1a5`: `ProcessControl.Configurator.SubTitle.Sales`
- `0xcb1b5`: `LOCID_PROCESS_CONTROL_CONFIGURATION_SUB_TITLE_SERVICE`
- `0xcb1bf`: `ProcessControl.Configurator.SubTitle.Service`
- `0xcb1cf`: `LOCID_PROCESS_CONTROL_CONFIGURATION_SAVING_DIALOG_CLOSE_BUTTON_TEXT`
- `0xcb1d9`: `ProcessControl.Configurator.SavingDialog.CloseButton`

## pseudocode

```c

```

## disassembly

```asm
0xcb0b0  ldarg.1
0xcb0b1  ldstr    aLocidUnsavedch_0// "LOCID_UNSAVEDCHANGES"
0xcb0b6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xcb0bb  ldstr    aUnsavedchanges// "UnSavedChangesWarning"
0xcb0c0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcb0c5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcb0ca  ldarg.1
0xcb0cb  ldstr    aLocidSaving// "LOCID_SAVING"
0xcb0d0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xcb0d5  ldstr    aSavinginformat// "SavingInformation"
0xcb0da  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcb0df  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcb0e4  ldarg.1
0xcb0e5  ldstr    aLocidReadonly// "LOCID_READONLY"
0xcb0ea  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xcb0ef  ldstr    aReadonly_0// "ReadOnly"
0xcb0f4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcb0f9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcb0fe  ldarg.1
0xcb0ff  ldstr    aLocidSavetoolt// "LOCID_SAVETOOLTIP"
0xcb104  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xcb109  ldstr    aErrorstatuscon// "ErrorStatusControlSaveToolTip"
0xcb10e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcb113  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcb118  ldarg.1
0xcb119  ldstr    aLocidMissingre// "LOCID_MISSINGREQUIREDFIELDS"
0xcb11e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xcb123  ldstr    aMissingrequire// "MissingRequiredFieldsError"
0xcb128  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcb12d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcb132  ldarg.1
0xcb133  ldstr    aLocidFormconta// "LOCID_FORMCONTAININVALIDDATA"
0xcb138  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xcb13d  ldstr    aFormcontaininv// "FormContainInvalidData"
0xcb142  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcb147  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcb14c  ldarg.1
0xcb14d  ldstr    aLocidGenericMe// "LOCID_GENERIC_MESSAGE"
0xcb152  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xcb157  ldstr    aErrorMessage0x_32// "Error_Message_0x80041101"
0xcb15c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcb161  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcb166  ldarg.1
0xcb167  ldstr    aLocidProcessCo// "LOCID_PROCESS_CONTROL_CONFIGURATION_MAI"...
0xcb16c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xcb171  ldstr    aProcesscontrol_44// "ProcessControl.Configurator.MainTitle"
0xcb176  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcb17b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcb180  ldarg.1
0xcb181  ldstr    aLocidProcessCo_0// "LOCID_PROCESS_CONTROL_CONFIGURATION_HEL"...
0xcb186  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xcb18b  ldstr    aProcesscontrol_45// "ProcessControl.Configurator.HelpButtonA"...
0xcb190  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcb195  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcb19a  ldarg.1
0xcb19b  ldstr    aLocidProcessCo_1// "LOCID_PROCESS_CONTROL_CONFIGURATION_SUB"...
0xcb1a0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xcb1a5  ldstr    aProcesscontrol_46// "ProcessControl.Configurator.SubTitle.Sa"...
0xcb1aa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcb1af  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcb1b4  ldarg.1
0xcb1b5  ldstr    aLocidProcessCo_2// "LOCID_PROCESS_CONTROL_CONFIGURATION_SUB"...
0xcb1ba  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xcb1bf  ldstr    aProcesscontrol_47// "ProcessControl.Configurator.SubTitle.Se"...
0xcb1c4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcb1c9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcb1ce  ldarg.1
0xcb1cf  ldstr    aLocidProcessCo_3// "LOCID_PROCESS_CONTROL_CONFIGURATION_SAV"...
0xcb1d4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xcb1d9  ldstr    aProcesscontrol_48// "ProcessControl.Configurator.SavingDialo"...
0xcb1de  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcb1e3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcb1e8  ldarg.1
0xcb1e9  ldstr    aLocidProcessin// "LOCID_PROCESSING"
0xcb1ee  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xcb1f3  ldstr    aInlineeditform// "InlineEditForm_Processing"
0xcb1f8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcb1fd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcb202  ldarg.1
0xcb203  ldstr    aLocidRevenueca// "LOCID_REVENUECANNOTBENULL"
0xcb208  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xcb20d  ldstr    aOpportunityToo// "Opportunity.Tooltip.CloseAsWonOrLost"
0xcb212  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xcb217  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcb21c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0xcb221  ldstr    aAutosaveinterv// "AutoSaveInterval"
0xcb226  callvirt T0x2B000002
0xcb22b  stloc.0
0xcb22c  ldloca.s 0
0xcb22e  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xcb233  brfalse.s loc_CB24A
0xcb235  ldarg.1
0xcb236  ldstr    aAutosaveinterv_0// "_autoSaveInterval"
0xcb23b  ldloca.s 0
0xcb23d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xcb242  conv.i8
0xcb243  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xcb248  br.s     loc_CB258
0xcb24a  ldarg.1
0xcb24b  ldstr    aAutosaveinterv_0// "_autoSaveInterval"
0xcb250  ldc.i4.s 0x1E
0xcb252  conv.i8
0xcb253  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xcb258  ldarg.2
0xcb259  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0xcb25e  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0xcb263  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xcb268  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsRefreshEnabledForEntity(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcb26d  brfalse.s loc_CB28F
0xcb26f  ldarg.1
0xcb270  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xcb275  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xcb27a  callvirt instance string [System.Web]System.Web.HttpRequest::get_CurrentExecutionFilePath()
0xcb27f  ldstr    aEditAspx// "edit.aspx"
0xcb284  ldc.i4.5
0xcb285  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0xcb28a  ldc.i4.0
0xcb28b  ceq
0xcb28d  br.s     loc_CB290
0xcb28f  ldc.i4.0
0xcb290  stloc.1
0xcb291  ldarg.2
0xcb292  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0xcb297  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0xcb29c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xcb2a1  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::IsCurrentFormRefreshForm(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xcb2a6  stloc.2
0xcb2a7  ldarg.1
0xcb2a8  ldstr    aIsrefreshform// "_IsRefreshForm"
0xcb2ad  ldloc.1
0xcb2ae  brtrue.s loc_CB2B7
0xcb2b0  ldstr    a0_1// "0"
0xcb2b5  br.s     loc_CB2BC
0xcb2b7  ldstr    a1// "1"
0xcb2bc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcb2c1  ldarg.1
0xcb2c2  ldstr    aIsprocessform// "_IsProcessForm"
0xcb2c7  ldloc.2
0xcb2c8  brtrue.s loc_CB2D1
0xcb2ca  ldstr    a0_1// "0"
0xcb2cf  br.s     loc_CB2D6
0xcb2d1  ldstr    a1// "1"
0xcb2d6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcb2db  ldarg.1
0xcb2dc  ldstr    aEnforcestatetr// "_EnforceStateTransitions"
0xcb2e1  ldarg.2
0xcb2e2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0xcb2e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xcb2ec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xcb2f1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::IsStateModelAware(valuetype [mscorlib]System.Guid)
0xcb2f6  brfalse.s loc_CB305
0xcb2f8  ldarg.2
0xcb2f9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0xcb2fe  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EnforceStateTransitions()
0xcb303  brtrue.s loc_CB30C
0xcb305  ldstr    a0_1// "0"
0xcb30a  br.s     loc_CB311
0xcb30c  ldstr    a1// "1"
0xcb311  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xcb316  ldarg.1
0xcb317  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader
0xcb31c  stloc.3
0xcb31d  ldarg.2
0xcb31e  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Disabled()
0xcb323  brfalse.s loc_CB332
0xcb325  ldloc.3
0xcb326  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Ribbon.RibbonData [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader::get_RibbonDataControl()
0xcb32b  ldc.i4.4
0xcb32c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Ribbon.RibbonData::RegisterFormState(valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.FormState)
0xcb331  ret
0xcb332  ldarg.2
0xcb333  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0xcb338  brfalse.s loc_CB347
0xcb33a  ldloc.3
0xcb33b  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Ribbon.RibbonData [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader::get_RibbonDataControl()
0xcb340  ldc.i4.1
0xcb341  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Ribbon.RibbonData::RegisterFormState(valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.FormState)
0xcb346  ret
0xcb347  ldloc.3
0xcb348  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Ribbon.RibbonData [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader::get_RibbonDataControl()
0xcb34d  ldc.i4.2
0xcb34e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Ribbon.RibbonData::RegisterFormState(valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.FormState)
0xcb353  ret
```
