# Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioningv1::CheckForStatusUpdate

- ea: `0x6ac40`
- end: `0x6adfa`
- name: `Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioningv1::CheckForStatusUpdate`
- size: `442`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x6ac40`
- `0x6ae00`
- `0x6ae60`
- `0x6ae80`
- `0x6af10`
- `0x6b210`
- `0x6b9e0`
- `0x6ba00`
- `0x6ba40`
- `0x6ba60`
- `0x6ba80`
- `0x6bac0`

## string_xrefs

- `0x6ac91`: `ConfigureButtonLabel`
- `0x6acb1`: `DisableConfigButton`
- `0x6ad61`: `LastUpdateString`
- `0x6ad70`: `Web.Tools.MobileOfflineProvisioning.Config.LastUpdatedTime`
- `0x6adc5`: `IsProvisioningCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x6ac40  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6ac45  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x6ac4a  ldc.i4.0
0x6ac4b  ldnull
0x6ac4c  call     class [Microsoft.Crm]Microsoft.Crm.IMobileOfflineState [Microsoft.Crm]Microsoft.Crm.MobileOfflineUtility::Read(valuetype [mscorlib]System.Guid, bool, string)
0x6ac51  castclass [Microsoft.Crm]Microsoft.Crm.MobileOfflineState
0x6ac56  stloc.0
0x6ac57  ldloc.0
0x6ac58  call     class Microsoft.Crm.Web.Tools.MobileOffline.Resources Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioningv1::GetResourcesForState(class [Microsoft.Crm]Microsoft.Crm.MobileOfflineState offlineState)
0x6ac5d  stloc.1
0x6ac5e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x6ac63  stloc.2
0x6ac64  ldloc.2
0x6ac65  ldstr    aShowprogressbl// "ShowProgressBlock"
0x6ac6a  ldloc.0
0x6ac6b  call     bool Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioningv1::IsAnyActionInProgress(class [Microsoft.Crm]Microsoft.Crm.MobileOfflineState offlineState)
0x6ac70  box      [mscorlib]System.Boolean
0x6ac75  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6ac7a  ldloc.2
0x6ac7b  ldstr    aProgressbar// "ProgressBar"
0x6ac80  ldloc.1
0x6ac81  callvirt instance int32 Microsoft.Crm.Web.Tools.MobileOffline.Resources::get_ProgressBar()
0x6ac86  box      [mscorlib]System.Int32
0x6ac8b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6ac90  ldloc.2
0x6ac91  ldstr    aConfigurebutto// "ConfigureButtonLabel"
0x6ac96  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6ac9b  ldloc.1
0x6ac9c  callvirt instance string Microsoft.Crm.Web.Tools.MobileOffline.Resources::get_ConfigureButtonLabelId()
0x6aca1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6aca6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x6acab  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6acb0  ldloc.2
0x6acb1  ldstr    aDisableconfigb// "DisableConfigButton"
0x6acb6  ldloc.1
0x6acb7  callvirt instance bool Microsoft.Crm.Web.Tools.MobileOffline.Resources::get_ConfigureButtonDisabled()
0x6acbc  box      [mscorlib]System.Boolean
0x6acc1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6acc6  ldloc.2
0x6acc7  ldstr    aRequesttype_0// "RequestType"
0x6accc  ldloc.1
0x6accd  callvirt instance int32 Microsoft.Crm.Web.Tools.MobileOffline.Resources::get_RequestType()
0x6acd2  stloc.s  5
0x6acd4  ldloca.s 5
0x6acd6  call     instance string [mscorlib]System.Int32::ToString()
0x6acdb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x6ace0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6ace5  ldloc.1
0x6ace6  ldarg.0
0x6ace7  call     string Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioningv1::GetProgressStateId(class Microsoft.Crm.Web.Tools.MobileOffline.Resources resources, bool isOrgDedicated)
0x6acec  stloc.3
0x6aced  ldloc.3
0x6acee  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6acf3  brfalse.s loc_6ACF8
0x6acf5  ldloc.3
0x6acf6  br.s     loc_6AD03
0x6acf8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6acfd  ldloc.3
0x6acfe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6ad03  stloc.s  4
0x6ad05  ldloc.2
0x6ad06  ldstr    aProgressstate// "ProgressState"
0x6ad0b  ldloc.s  4
0x6ad0d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x6ad12  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6ad17  ldloc.2
0x6ad18  ldstr    aProgressstatus// "ProgressStatus"
0x6ad1d  ldloc.1
0x6ad1e  callvirt instance string Microsoft.Crm.Web.Tools.MobileOffline.Resources::get_StageProgress()
0x6ad23  ldloc.1
0x6ad24  callvirt instance string Microsoft.Crm.Web.Tools.MobileOffline.Resources::get_StageProgress()
0x6ad29  ldsfld   string [mscorlib]System.String::Empty
0x6ad2e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6ad33  brtrue.s loc_6AD3C
0x6ad35  ldstr    asc_11EF2A// ""
0x6ad3a  br.s     loc_6AD41
0x6ad3c  ldstr    asc_11E6FC// " "
0x6ad41  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6ad46  ldloc.1
0x6ad47  callvirt instance string Microsoft.Crm.Web.Tools.MobileOffline.Resources::get_StatusId()
0x6ad4c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6ad51  call     string [mscorlib]System.String::Concat(string, string, string)
0x6ad56  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x6ad5b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6ad60  ldloc.2
0x6ad61  ldstr    aLastupdatestri// "LastUpdateString"
0x6ad66  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x6ad6b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6ad70  ldstr    aWebToolsMobile_25// "Web.Tools.MobileOfflineProvisioning.Con"...
0x6ad75  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6ad7a  ldc.i4.1
0x6ad7b  newarr   [mscorlib]System.Object
0x6ad80  dup
0x6ad81  ldc.i4.0
0x6ad82  ldloc.0
0x6ad83  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm]Microsoft.Crm.MobileOfflineState::get_LastUpdatedTime()
0x6ad88  call     string Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioningv1::GetFormattedUserDateTimeFromUtcDateTime(valuetype [mscorlib]System.DateTime dateTime)
0x6ad8d  stelem.ref
0x6ad8e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6ad93  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x6ad98  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6ad9d  ldloc.2
0x6ad9e  ldstr    aMobileofflined// "MobileOfflineDataSyncProgress"
0x6ada3  ldloc.0
0x6ada4  callvirt instance string [Microsoft.Crm]Microsoft.Crm.MobileOfflineState::get_MobileOfflineDataSyncProgress()
0x6ada9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6adae  ldloc.2
0x6adaf  ldstr    aShouldshowdata// "ShouldShowDataSyncProgressUi"
0x6adb4  ldloc.0
0x6adb5  call     bool Microsoft.Crm.Web.Tools.MobileOffline.MobileOfflineProvisioningv1::ShouldShowDataSyncProgressUi(class [Microsoft.Crm]Microsoft.Crm.MobileOfflineState offlineState)
0x6adba  box      [mscorlib]System.Boolean
0x6adbf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6adc4  ldloc.2
0x6adc5  ldstr    aIsprovisioning// "IsProvisioningCompleted"
0x6adca  ldloc.0
0x6adcb  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.MobileOfflineState::get_MobileOfflineStatus()
0x6add0  ldc.i4.2
0x6add1  ceq
0x6add3  box      [mscorlib]System.Boolean
0x6add8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6addd  ldloc.2
0x6adde  ldstr    aMobileofflined_0// "MobileOfflineDeprovisionReason"
0x6ade3  ldloc.0
0x6ade4  callvirt instance string [Microsoft.Crm]Microsoft.Crm.MobileOfflineState::get_MobileOfflineDeprovisionReason()
0x6ade9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x6adee  newobj   instance void [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::.ctor()
0x6adf3  ldloc.2
0x6adf4  callvirt instance string [System.Web.Extensions]System.Web.Script.Serialization.JavaScriptSerializer::Serialize(object)
0x6adf9  ret
```
