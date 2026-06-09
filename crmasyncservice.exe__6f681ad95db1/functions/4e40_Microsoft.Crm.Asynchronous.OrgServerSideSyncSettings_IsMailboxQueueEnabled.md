# Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::IsMailboxQueueEnabled

- ea: `0x4e40`
- end: `0x4e74`
- name: `Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::IsMailboxQueueEnabled`
- size: `52`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x7e40`
- `0x7f10`
- `0x7ff0`
- `0x81e0`

## callees

- `0xab10`

## pseudocode

```c

```

## disassembly

```asm
0x4e40  newobj   instance void <>c__DisplayClass13_0::.ctor()
0x4e45  stloc.0
0x4e46  ldloc.0
0x4e47  ldarg.0
0x4e48  stfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration <>c__DisplayClass13_0::orgConfiguration
0x4e4d  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings> Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::orgQueueSettingsCache
0x4e52  ldloc.0
0x4e53  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration <>c__DisplayClass13_0::orgConfiguration
0x4e58  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x4e5d  ldloc.0
0x4e5e  ldftn    instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings <>c__DisplayClass13_0::<IsMailboxQueueEnabled>b__0(valuetype [mscorlib]System.Guid orgId)
0x4e64  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings>::.ctor(object, native int)
0x4e69  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings>::GetOrAdd(void, var<u1>)
0x4e6e  callvirt instance bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings::get_IsMailboxQueueEnabled()
0x4e73  ret
```
