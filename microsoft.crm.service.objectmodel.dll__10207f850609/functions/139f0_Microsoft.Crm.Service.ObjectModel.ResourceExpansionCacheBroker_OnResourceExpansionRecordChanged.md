# Microsoft.Crm.Service.ObjectModel.ResourceExpansionCacheBroker::OnResourceExpansionRecordChanged

- ea: `0x139f0`
- end: `0x13a60`
- name: `Microsoft.Crm.Service.ObjectModel.ResourceExpansionCacheBroker::OnResourceExpansionRecordChanged`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x139f0`
- `0x13a60`

## string_xrefs

- `0x139f1`: `cacheNotification`
- `0x13a54`: `Notification type must be one of the constants defined in CacheNotificationType class.`

## pseudocode

```c

```

## disassembly

```asm
0x139f0  ldarg.0
0x139f1  ldstr    aCachenotificat// "cacheNotification"
0x139f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x139fb  ldarg.0
0x139fc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ICacheNotification::get_ExecutionContext()
0x13a01  ldstr    aExecutionconte// "ExecutionContext"
0x13a06  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x13a0b  ldarg.0
0x13a0c  callvirt instance valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CacheNotificationType [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ICacheNotification::get_NotificationType()
0x13a11  stloc.0
0x13a12  ldloc.0
0x13a13  switch   loc_13A5F, loc_13A5F, loc_13A5F, loc_13A32, loc_13A32, loc_13A32
0x13a30  br.s     loc_13A44
0x13a32  ldarg.0
0x13a33  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ICacheNotification::get_ExecutionContext()
0x13a38  ldarg.0
0x13a39  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ICacheNotification::get_EntityId()
0x13a3e  call     void Microsoft.Crm.Service.ObjectModel.ResourceExpansionCacheBroker::InvalidateExpansionCache(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid entityId)
0x13a43  ret
0x13a44  ldstr    aNotificationty// "notificationType"
0x13a49  ldarg.0
0x13a4a  callvirt instance valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CacheNotificationType [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ICacheNotification::get_NotificationType()
0x13a4f  box      [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CacheNotificationType
0x13a54  ldstr    aNotificationTy// "Notification type must be one of the co"...
0x13a59  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentOutOfRangeException::.ctor(string, object, string)
0x13a5e  throw
0x13a5f  ret
```
