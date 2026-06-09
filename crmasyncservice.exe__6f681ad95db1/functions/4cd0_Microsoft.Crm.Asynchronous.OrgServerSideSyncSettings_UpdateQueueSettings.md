# Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::UpdateQueueSettings

- ea: `0x4cd0`
- end: `0x4d1e`
- name: `Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::UpdateQueueSettings`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x4cb0`
- `0x4cd0`

## pseudocode

```c

```

## disassembly

```asm
0x4cd0  ldnull
0x4cd1  stloc.0
0x4cd2  ldsfld   class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::serverConfiguration
0x4cd7  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationList::get_Organizations()
0x4cdc  ldarg.0
0x4cdd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_OrganizationId()
0x4ce2  ldloca.s 0
0x4ce4  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::TryGetValue(var<u1>, !!T0)
0x4ce9  pop
0x4cea  ldnull
0x4ceb  stloc.1
0x4cec  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings> Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::orgQueueSettingsCache
0x4cf1  ldarg.0
0x4cf2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_OrganizationId()
0x4cf7  ldloca.s 1
0x4cf9  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings>::TryGetValue(var<u1>, !!T0)
0x4cfe  pop
0x4cff  ldloc.1
0x4d00  brfalse.s loc_4D1D
0x4d02  ldloc.1
0x4d03  callvirt instance bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings::get_IsActivityQueueEnabled()
0x4d08  brfalse.s loc_4D12
0x4d0a  ldloc.1
0x4d0b  callvirt instance bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings::get_IsMailboxQueueEnabled()
0x4d10  brtrue.s loc_4D1D
0x4d12  ldarg.0
0x4d13  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_OrganizationId()
0x4d18  call     void Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::RemoveOrgFromQueueSettingsCache(valuetype [mscorlib]System.Guid organizationId)
0x4d1d  ret
```
