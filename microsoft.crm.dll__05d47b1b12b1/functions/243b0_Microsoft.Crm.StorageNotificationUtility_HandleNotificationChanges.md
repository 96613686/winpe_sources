# Microsoft.Crm.StorageNotificationUtility::HandleNotificationChanges

- ea: `0x243b0`
- end: `0x24453`
- name: `Microsoft.Crm.StorageNotificationUtility::HandleNotificationChanges`
- size: `163`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x24380`
- `0x245f0`

## callees

- `0x243b0`
- `0x24460`
- `0x24490`
- `0x244b0`
- `0x244e0`
- `0x24640`
- `0x24690`
- `0x255c0`

## string_xrefs

- `0x243b0`: `Default template for StorageLimitReachedThreshold`
- `0x243b6`: `Default template for StorageLimitExceeded`
- `0x243c9`: `Template with Organization Summary for MS Online StorageLimitReachedThreshold`
- `0x243cf`: `Template with Organization Summary for MS Online StorageLimitExceeded`

## pseudocode

```c

```

## disassembly

```asm
0x243b0  ldstr    aDefaultTemplat// "Default template for StorageLimitReache"...
0x243b5  stloc.0
0x243b6  ldstr    aDefaultTemplat_0// "Default template for StorageLimitExceed"...
0x243bb  stloc.1
0x243bc  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x243c1  ldarg.0
0x243c2  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x243c7  brfalse.s loc_243D5
0x243c9  ldstr    aTemplateWithOr// "Template with Organization Summary for "...
0x243ce  stloc.0
0x243cf  ldstr    aTemplateWithOr_0// "Template with Organization Summary for "...
0x243d4  stloc.1
0x243d5  ldarg.0
0x243d6  ldc.i4.2
0x243d7  call     void Microsoft.Crm.StorageNotificationUtility::DeleteStorageNotifications(valuetype [mscorlib]System.Guid organizationId, valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationType notificationType)
0x243dc  ldarg.0
0x243dd  ldc.i4.1
0x243de  call     void Microsoft.Crm.StorageNotificationUtility::DeleteStorageNotifications(valuetype [mscorlib]System.Guid organizationId, valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationType notificationType)
0x243e3  ldarg.0
0x243e4  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageState Microsoft.Crm.StorageNotificationUtility::GetOrganizationStorageState(valuetype [mscorlib]System.Guid organizationId)
0x243e9  stloc.2
0x243ea  ldarg.2
0x243eb  conv.i8
0x243ec  ldarg.1
0x243ed  conv.i8
0x243ee  mul
0x243ef  ldc.i4.s 0x64
0x243f1  conv.i8
0x243f2  div
0x243f3  stloc.3
0x243f4  ldarg.3
0x243f5  conv.i8
0x243f6  ldloc.3
0x243f7  bge.s    loc_2440F
0x243f9  ldloc.2
0x243fa  brfalse.s loc_24409
0x243fc  ldarg.0
0x243fd  call     void Microsoft.Crm.StorageNotificationUtility::ClearStorageNotificationLastEmailSent(valuetype [mscorlib]System.Guid organizationId)
0x24402  ldarg.0
0x24403  ldc.i4.0
0x24404  call     void Microsoft.Crm.StorageNotificationUtility::SetOrganizationStorageState(valuetype [mscorlib]System.Guid organizationId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageState newState)
0x24409  ldsfld   string [mscorlib]System.String::Empty
0x2440e  ret
0x2440f  ldarg.3
0x24410  ldarg.1
0x24411  bge.s    loc_24433
0x24413  ldloc.2
0x24414  ldc.i4.1
0x24415  beq.s    loc_24424
0x24417  ldarg.0
0x24418  call     void Microsoft.Crm.StorageNotificationUtility::ClearStorageNotificationLastEmailSent(valuetype [mscorlib]System.Guid organizationId)
0x2441d  ldarg.0
0x2441e  ldc.i4.1
0x2441f  call     void Microsoft.Crm.StorageNotificationUtility::SetOrganizationStorageState(valuetype [mscorlib]System.Guid organizationId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageState newState)
0x24424  ldloc.0
0x24425  ldarg.0
0x24426  ldarg.0
0x24427  call     int32 Microsoft.Crm.StorageNotificationUtility::GetStorageNotificationWarningRecurrenceInDaysSetting(valuetype [mscorlib]System.Guid organizationId)
0x2442c  call     void Microsoft.Crm.StorageNotificationUtility::HandleStorageNotifications(string templateName, valuetype [mscorlib]System.Guid organizationId, int32 daysToWaitUntilNextMailNotification)
0x24431  ldloc.0
0x24432  ret
0x24433  ldloc.2
0x24434  ldc.i4.2
0x24435  beq.s    loc_24444
0x24437  ldarg.0
0x24438  call     void Microsoft.Crm.StorageNotificationUtility::ClearStorageNotificationLastEmailSent(valuetype [mscorlib]System.Guid organizationId)
0x2443d  ldarg.0
0x2443e  ldc.i4.2
0x2443f  call     void Microsoft.Crm.StorageNotificationUtility::SetOrganizationStorageState(valuetype [mscorlib]System.Guid organizationId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageState newState)
0x24444  ldloc.1
0x24445  ldarg.0
0x24446  ldarg.0
0x24447  call     int32 Microsoft.Crm.StorageNotificationUtility::GetStorageNotificationAlertRecurrenceInDaysSetting(valuetype [mscorlib]System.Guid organizationId)
0x2444c  call     void Microsoft.Crm.StorageNotificationUtility::HandleStorageNotifications(string templateName, valuetype [mscorlib]System.Guid organizationId, int32 daysToWaitUntilNextMailNotification)
0x24451  ldloc.1
0x24452  ret
```
