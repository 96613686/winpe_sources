# Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::IsMailboxInactiveBackOffEnabled

- ea: `0x4d60`
- end: `0x4d94`
- name: `Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::IsMailboxInactiveBackOffEnabled`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x8db0`

## callees

- `0xaa50`

## pseudocode

```c

```

## disassembly

```asm
0x4d60  newobj   instance void <>c__DisplayClass10_0::.ctor()
0x4d65  stloc.0
0x4d66  ldloc.0
0x4d67  ldarg.0
0x4d68  stfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration <>c__DisplayClass10_0::orgConfiguration
0x4d6d  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings> Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::orgSettingsLightCache
0x4d72  ldloc.0
0x4d73  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration <>c__DisplayClass10_0::orgConfiguration
0x4d78  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x4d7d  ldloc.0
0x4d7e  ldftn    instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings <>c__DisplayClass10_0::<IsMailboxInactiveBackOffEnabled>b__0(valuetype [mscorlib]System.Guid orgId)
0x4d84  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings>::.ctor(object, native int)
0x4d89  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings>::GetOrAdd(void, var<u1>)
0x4d8e  callvirt instance bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings::get_IsMailboxInactiveBackOffEnabled()
0x4d93  ret
```
