# Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::IsActivityQueueEnabled

- ea: `0x4e00`
- end: `0x4e34`
- name: `Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::IsActivityQueueEnabled`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x7490`

## callees

- `0xaad0`

## pseudocode

```c

```

## disassembly

```asm
0x4e00  newobj   instance void <>c__DisplayClass12_0::.ctor()
0x4e05  stloc.0
0x4e06  ldloc.0
0x4e07  ldarg.0
0x4e08  stfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration <>c__DisplayClass12_0::orgConfiguration
0x4e0d  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings> Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::orgQueueSettingsCache
0x4e12  ldloc.0
0x4e13  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration <>c__DisplayClass12_0::orgConfiguration
0x4e18  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x4e1d  ldloc.0
0x4e1e  ldftn    instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings <>c__DisplayClass12_0::<IsActivityQueueEnabled>b__0(valuetype [mscorlib]System.Guid orgId)
0x4e24  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings>::.ctor(object, native int)
0x4e29  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings>::GetOrAdd(void, var<u1>)
0x4e2e  callvirt instance bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings::get_IsActivityQueueEnabled()
0x4e33  ret
```
