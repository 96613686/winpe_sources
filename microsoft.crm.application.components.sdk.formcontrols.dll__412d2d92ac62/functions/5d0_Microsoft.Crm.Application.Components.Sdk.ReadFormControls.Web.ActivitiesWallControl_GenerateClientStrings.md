# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::GenerateClientStrings

- ea: `0x5d0`
- end: `0xf83`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::GenerateClientStrings`
- size: `2483`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x170`

## callees

- `0x5d0`
- `0xf90`

## string_xrefs

- `0x72f`: `scheduledend`
- `0x8dd`: `COMPLETE_BUTTON_TEXT`
- `0x8e7`: `ActivityWall.CompleteButtonLabel`
- `0x8f8`: `COMPLETE_FAILED_ACTION_ERROR_MESSAGE`
- `0x902`: `ActivityWall.CompleteActionErrorMessage`
- `0x913`: `CLICK_OPEN_RECORD_TOOLTIP`
- `0x91d`: `ActivityWall.OpenRecordToolTip`
- `0xa02`: `COMPLETE_BUTTON_TOOLTIP`
- `0xa0c`: `ActivityWall.CompleteButtonToolTip`
- `0xa53`: `ACT_WALL_LASTOPENED_JUST_NOW`
- `0xa5d`: `ActivityItem_LastOpened_JustNow_Text`
- `0xaa4`: `ACT_WALL_LASTOPENED_ON`
- `0xaae`: `ActivityItem_Opened_ON`
- `0xada`: `ACT_WALL_LASTOPENED_TODAY`
- `0xae4`: `ActivityItem_Opened_TODAY`
- `0xb10`: `ACT_WALL_LASTOPENED_YESTERDAY`
- `0xb1a`: `ActivityItem_Opened_YESTERDAY`
- `0xb46`: `ACT_WALL_LASTOPENED_HOURS_AGO`
- `0xb50`: `ActivityItem_LastOpened_Hours_Text`
- `0xb7c`: `ACT_WALL_LASTOPENED_HOUR_AGO`
- `0xb86`: `ActivityItem_LastOpened_Hour_Text`
- `0xbb2`: `ACT_WALL_LASTOPENED_YEAR_AGO`
- `0xbbc`: `ActivityItem_LastOpened_Year_Text`
- `0xbcd`: `ACT_WALL_NOT_YET_OPENED`
- `0xbd7`: `ActivityItem_NotOpened_Text`
- `0xc03`: `ACT_WALL_LASTOPENED_MONTH`
- `0xc0d`: `ActivityItem_LastOpened_Month_Text`
- `0xc54`: `ACT_WALL_COMPLETED_BY_LOC_STRING`
- `0xc5e`: `ActivityWall.CompletedBy`
- `0xd66`: `ACT_WALL_INCOMING_VALUE_LOC_STRING`
- `0xd70`: `ActivityWall.Incoming`
- `0xd9c`: `ACT_WALL_VOICEMAIL_INCOMING_VALUE_LOC_STRING`
- `0xda6`: `ActivityWall.IncomingVoicemail`
- `0xf67`: `ACT_WALL_LAST_OPENED`
- `0xf71`: `ACT_WALL_LAST_OPENED`

## pseudocode

```c

```

## disassembly

```asm
0x5d0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5d5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5da  ldstr    aPhonecall// "phonecall"
0x5df  ldc.i4.1
0x5e0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x5e5  stloc.0
0x5e6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5eb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5f0  ldstr    aEmail// "email"
0x5f5  ldc.i4.1
0x5f6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x5fb  stloc.1
0x5fc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x601  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x606  ldstr    aTask// "task"
0x60b  ldc.i4.1
0x60c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x611  stloc.2
0x612  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x617  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x61c  ldstr    aOpportunityclo// "opportunityclose"
0x621  ldc.i4.1
0x622  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x627  stloc.3
0x628  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x62d  stloc.s  4
0x62f  ldloc.s  4
0x631  ldstr    aDirectionLocSt// "DIRECTION_LOC_STRING"
0x636  ldloc.0
0x637  ldstr    aDirectioncode// "directioncode"
0x63c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x641  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x646  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x64b  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_ClientUserUILanguageId()
0x650  stloc.s  5
0x652  ldloca.s 5
0x654  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x659  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x65e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x663  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x668  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x66d  ldloc.s  4
0x66f  ldstr    aFromLocString// "FROM_LOC_STRING"
0x674  ldloc.1
0x675  ldstr    aFrom// "from"
0x67a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x67f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x684  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x689  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_ClientUserUILanguageId()
0x68e  stloc.s  5
0x690  ldloca.s 5
0x692  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x697  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x69c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6a1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x6a6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6ab  ldloc.s  4
0x6ad  ldstr    aToLocString// "TO_LOC_STRING"
0x6b2  ldloc.1
0x6b3  ldstr    aTo// "to"
0x6b8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x6bd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x6c2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6c7  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_ClientUserUILanguageId()
0x6cc  stloc.s  5
0x6ce  ldloca.s 5
0x6d0  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x6d5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6da  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6df  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x6e4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x6e9  ldloc.s  4
0x6eb  ldstr    aCcLocString// "CC_LOC_STRING"
0x6f0  ldloc.1
0x6f1  ldstr    aCc// "cc"
0x6f6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x6fb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x700  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x705  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_ClientUserUILanguageId()
0x70a  stloc.s  5
0x70c  ldloca.s 5
0x70e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x713  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x718  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x71d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x722  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x727  ldloc.s  4
0x729  ldstr    aDuedateLocStri// "DUEDATE_LOC_STRING"
0x72e  ldloc.2
0x72f  ldstr    aScheduledend// "scheduledend"
0x734  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x739  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x73e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x743  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_ClientUserUILanguageId()
0x748  stloc.s  5
0x74a  ldloca.s 5
0x74c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x751  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x756  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x75b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x760  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x765  ldloc.s  4
0x767  ldstr    aPrioritycodeLo// "PRIORITYCODE_LOC_STRING"
0x76c  ldloc.2
0x76d  ldstr    aPrioritycode// "prioritycode"
0x772  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x777  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x77c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x781  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_ClientUserUILanguageId()
0x786  stloc.s  5
0x788  ldloca.s 5
0x78a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x78f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x794  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x799  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x79e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x7a3  ldloc.3
0x7a4  brfalse.s loc_7F1
0x7a6  ldloc.3
0x7a7  ldstr    aActualrevenue// "actualrevenue"
0x7ac  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x7b1  brfalse.s loc_7F1
0x7b3  ldloc.s  4
0x7b5  ldstr    aActualrevenueL// "ACTUALREVENUE_LOC_STRING"
0x7ba  ldloc.3
0x7bb  ldstr    aActualrevenue// "actualrevenue"
0x7c0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x7c5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x7ca  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7cf  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_ClientUserUILanguageId()
0x7d4  stloc.s  5
0x7d6  ldloca.s 5
0x7d8  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x7dd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7e2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7e7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x7ec  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x7f1  ldloc.s  4
0x7f3  ldstr    aRefreshTooltip// "REFRESH_TOOLTIP_LOC_STRING"
0x7f8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x7fd  ldstr    aActivitieswall_1// "ActivitiesWall.Refresh_Tool_Tip"
0x802  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x807  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x80c  ldloc.s  4
0x80e  ldstr    aActivitypointe_0// "ACTIVITYPOINTER_RELATIONSHIP_NAME"
0x813  ldarg.0
0x814  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::RetrieveRelatioinShipWithActivityPointer()
0x819  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x81e  ldloc.s  4
0x820  ldstr    aEmptyMessageLo// "EMPTY_MESSAGE_LOC_STRING"
0x825  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x82a  ldstr    aActivitywallEm// "ActivityWall.EmptyMessage"
0x82f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x834  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x839  ldloc.s  4
0x83b  ldstr    aEmptyMessageFc// "EMPTY_MESSAGE_FCB_ON_LOC_STRING"
0x840  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x845  ldstr    aActivitywallEm_0// "ActivityWall.EmptyMessageFCBOn"
0x84a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x84f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x854  ldloc.s  4
0x856  ldstr    aEmptyMessageWi// "EMPTY_MESSAGE_WITH_FILTER_LOC_STRING"
0x85b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x860  ldstr    aActivitywallEm_1// "ActivityWall.EmptyMessageWithFilter"
0x865  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x86a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x86f  ldloc.s  4
0x871  ldstr    aLoadingTextLoc// "LOADING_TEXT_LOC_STRING"
0x876  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x87b  ldstr    aActivitywallLo// "ActivityWall.Loading"
0x880  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x885  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x88a  ldloc.s  4
0x88c  ldstr    aSenderNotFound// "SENDER_NOT_FOUND_MESSAGE_LOC_STRING"
0x891  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x896  ldstr    aActivitywallSe// "ActivityWall.SenderNotFoundMessage"
0x89b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8a0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x8a5  ldloc.s  4
0x8a7  ldstr    aDescriptionNot// "DESCRIPTION_NOT_FOUND_MESSAGE_LOC_STRIN"...
0x8ac  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8b1  ldstr    aActivitywallDe// "ActivityWall.DescriptionNotFoundMessage"
0x8b6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8bb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x8c0  ldloc.s  4
0x8c2  ldstr    aLeftVoiceMailM// "LEFT_VOICE_MAIL_MESSAGE_LOC_STRING"
0x8c7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8cc  ldstr    aActivitycontai// "ActivityContainerControl.LeftvoicemailL"...
0x8d1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8d6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x8db  ldloc.s  4
0x8dd  ldstr    aCompleteButton// "COMPLETE_BUTTON_TEXT"
0x8e2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8e7  ldstr    aActivitywallCo// "ActivityWall.CompleteButtonLabel"
0x8ec  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8f1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x8f6  ldloc.s  4
0x8f8  ldstr    aCompleteFailed// "COMPLETE_FAILED_ACTION_ERROR_MESSAGE"
0x8fd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x902  ldstr    aActivitywallCo_0// "ActivityWall.CompleteActionErrorMessage"
0x907  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x90c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x911  ldloc.s  4
0x913  ldstr    aClickOpenRecor// "CLICK_OPEN_RECORD_TOOLTIP"
0x918  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x91d  ldstr    aActivitywallOp// "ActivityWall.OpenRecordToolTip"
0x922  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x927  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x92c  ldloc.s  4
0x92e  ldstr    aExpandIconTool// "EXPAND_ICON_TOOL_TIP"
0x933  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x938  ldstr    aActivitywallEx// "ActivityWall.ExpandIconToolTip"
0x93d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x942  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x947  ldloc.s  4
0x949  ldstr    aCollapseIconTo// "COLLAPSE_ICON_TOOL_TIP"
0x94e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x953  ldstr    aActivitywallCo_1// "ActivityWall.CollapnseIconToolTip"
0x958  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x95d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x962  ldloc.s  4
0x964  ldstr    aExpandConversa// "EXPAND_CONVERSATION_TOOL_TIP"
0x969  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x96e  ldstr    aActivitywallEx_0// "ActivityWall.ExpandConversationToolTip"
0x973  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x978  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x97d  ldloc.s  4
0x97f  ldstr    aCollapseConver// "COLLAPSE_CONVERSATION_TOOL_TIP"
0x984  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x989  ldstr    aActivitywallCo_2// "ActivityWall.CollapnseConversationToolT"...
0x98e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x993  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x998  ldloc.s  4
0x99a  ldstr    aActWallShowmor// "ACT_WALL_SHOWMORE_TOOLTIP"
0x99f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9a4  ldstr    aActivitywallSh// "ActivityWall.ShowMoreActivitiesToolTip"
0x9a9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x9b3  ldloc.s  4
0x9b5  ldstr    aActWallShowmor_0// "ACT_WALL_SHOWMORE_TEXT"
0x9ba  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9bf  ldstr    aActivitywallSh_0// "ActivityWall.ShowMoreActivitiesText"
0x9c4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9c9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x9ce  ldloc.s  4
0x9d0  ldstr    aActWallShowmor_1// "ACT_WALL_SHOWMOREPROGRESS_ALT"
0x9d5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x9da  ldstr    aActivitywallLo// "ActivityWall.Loading"
0x9df  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9e4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x9e9  ldloc.s  4
0x9eb  ldstr    aIsactivitypart// "ISACTIVITYPARTY"
0x9f0  ldarg.0
0x9f1  ldflda   bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::isActivityParty
0x9f6  call     instance string [mscorlib]System.Boolean::ToString()
0x9fb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa00  ldloc.s  4
0xa02  ldstr    aCompleteButton_0// "COMPLETE_BUTTON_TOOLTIP"
0xa07  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa0c  ldstr    aActivitywallCo_3// "ActivityWall.CompleteButtonToolTip"
0xa11  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa16  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa1b  ldloc.s  4
0xa1d  ldstr    aActWallYou// "ACT_WALL_YOU"
0xa22  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa27  ldstr    aActivitywallYo// "ActivityWall.You"
0xa2c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa31  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa36  ldloc.s  4
0xa38  ldstr    aActWallSentJus// "ACT_WALL_SENT_JUST_NOW"
0xa3d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa42  ldstr    aActivityitemSe// "ActivityItem_Sent_JustNow_Text"
0xa47  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa4c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa51  ldloc.s  4
0xa53  ldstr    aActWallLastope// "ACT_WALL_LASTOPENED_JUST_NOW"
0xa58  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa5d  ldstr    aActivityitemLa// "ActivityItem_LastOpened_JustNow_Text"
0xa62  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa67  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa6c  ldloc.s  4
0xa6e  ldstr    aActWallAt// "ACT_WALL_AT"
0xa73  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa78  ldstr    aActivitywallAt// "ActivityWall.At"
0xa7d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa82  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xa87  ldloc.s  4
0xa89  ldstr    aActWallSentOn// "ACT_WALL_SENT_ON"
0xa8e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa93  ldstr    aActivityitemSe_0// "ActivityItem_Sent_ON"
0xa98  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xa9d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xaa2  ldloc.s  4
0xaa4  ldstr    aActWallLastope_0// "ACT_WALL_LASTOPENED_ON"
0xaa9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xaae  ldstr    aActivityitemOp// "ActivityItem_Opened_ON"
0xab3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xab8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xabd  ldloc.s  4
0xabf  ldstr    aActWallSentTod// "ACT_WALL_SENT_TODAY"
  ... truncated ...
```
