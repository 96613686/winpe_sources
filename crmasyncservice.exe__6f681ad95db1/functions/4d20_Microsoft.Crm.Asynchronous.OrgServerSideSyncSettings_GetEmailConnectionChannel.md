# Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::GetEmailConnectionChannel

- ea: `0x4d20`
- end: `0x4d54`
- name: `Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::GetEmailConnectionChannel`
- size: `52`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x7520`
- `0x81e0`
- `0x8540`

## callees

- `0xaa10`

## pseudocode

```c

```

## disassembly

```asm
0x4d20  newobj   instance void <>c__DisplayClass9_0::.ctor()
0x4d25  stloc.0
0x4d26  ldloc.0
0x4d27  ldarg.0
0x4d28  stfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration <>c__DisplayClass9_0::orgConfiguration
0x4d2d  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings> Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::orgSettingsLightCache
0x4d32  ldloc.0
0x4d33  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration <>c__DisplayClass9_0::orgConfiguration
0x4d38  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x4d3d  ldloc.0
0x4d3e  ldftn    instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings <>c__DisplayClass9_0::<GetEmailConnectionChannel>b__0(valuetype [mscorlib]System.Guid orgId)
0x4d44  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings>::.ctor(object, native int)
0x4d49  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings>::GetOrAdd(void, var<u1>)
0x4d4e  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailConnectionChannelType [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings::get_EmailConnectionChannelType()
0x4d53  ret
```
