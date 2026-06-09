# Microsoft.Crm.Service.ObjectModel.ResourceExpansionCacheBroker::.cctor

- ea: `0x13980`
- end: `0x139e2`
- name: `Microsoft.Crm.Service.ObjectModel.ResourceExpansionCacheBroker::.cctor`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x139b9`: `Service`

## pseudocode

```c

```

## disassembly

```asm
0x13980  ldnull
0x13981  ldftn    void Microsoft.Crm.Service.ObjectModel.ResourceExpansionCacheBroker::OnResourceExpansionRecordChanged(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ICacheNotification cacheNotification)
0x13987  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CacheNotificationsMediator/CacheNotificationHandler::.ctor(object, native int)
0x1398c  stloc.0
0x1398d  ldstr    aSystemuser// "SystemUser"
0x13992  ldloc.0
0x13993  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CacheNotificationsMediator::Register(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CacheNotificationsMediator/CacheNotificationHandler)
0x13998  ldstr    aEquipment// "Equipment"
0x1399d  ldloc.0
0x1399e  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CacheNotificationsMediator::Register(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CacheNotificationsMediator/CacheNotificationHandler)
0x139a3  ldstr    aResourcespec// "ResourceSpec"
0x139a8  ldloc.0
0x139a9  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CacheNotificationsMediator::Register(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CacheNotificationsMediator/CacheNotificationHandler)
0x139ae  ldstr    aConstraintbase// "ConstraintBasedGroup"
0x139b3  ldloc.0
0x139b4  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CacheNotificationsMediator::Register(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CacheNotificationsMediator/CacheNotificationHandler)
0x139b9  ldstr    aService// "Service"
0x139be  ldloc.0
0x139bf  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CacheNotificationsMediator::Register(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CacheNotificationsMediator/CacheNotificationHandler)
0x139c4  ldstr    aTeam// "Team"
0x139c9  ldloc.0
0x139ca  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CacheNotificationsMediator::Register(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CacheNotificationsMediator/CacheNotificationHandler)
0x139cf  ldc.i4.8
0x139d0  ldnull
0x139d1  ldftn    void Microsoft.Crm.Service.ObjectModel.ResourceExpansionCacheBroker::OnNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0x139d7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0x139dc  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0x139e1  ret
```
