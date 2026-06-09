# Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::Initialize

- ea: `0x4be0`
- end: `0x4c36`
- name: `Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::Initialize`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180`

## pseudocode

```c

```

## disassembly

```asm
0x4be0  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings>::.ctor()
0x4be5  stsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings> Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::orgSettingsLightCache
0x4bea  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings>::.ctor()
0x4bef  stsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings> Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::orgQueueSettingsCache
0x4bf4  ldarg.0
0x4bf5  stsfld   class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::serverConfiguration
0x4bfa  ldsfld   class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::serverConfiguration
0x4bff  ldnull
0x4c00  ldftn    void Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::OnOrganizationChanged(object sender, class [mscorlib]System.EventArgs e)
0x4c06  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x4c0b  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationList::add_OrganizationsChanged(class [mscorlib]System.EventHandler)
0x4c10  ldc.i4.5
0x4c11  ldnull
0x4c12  ldftn    void Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::UpdateOrgSettingsLight(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs eventArgs)
0x4c18  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0x4c1d  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0x4c22  ldc.i4.s 0x59
0x4c24  ldnull
0x4c25  ldftn    void Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::UpdateQueueSettings(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs eventArgs)
0x4c2b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0x4c30  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0x4c35  ret
```
