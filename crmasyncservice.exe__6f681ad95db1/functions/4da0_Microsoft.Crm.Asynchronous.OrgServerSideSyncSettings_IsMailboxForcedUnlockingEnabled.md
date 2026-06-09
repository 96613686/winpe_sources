# Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::IsMailboxForcedUnlockingEnabled

- ea: `0x4da0`
- end: `0x4dff`
- name: `Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::IsMailboxForcedUnlockingEnabled`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x7ff0`

## callees

- `0x4da0`
- `0xaa90`

## pseudocode

```c

```

## disassembly

```asm
0x4da0  newobj   instance void <>c__DisplayClass11_0::.ctor()
0x4da5  stloc.0
0x4da6  ldloc.0
0x4da7  ldarg.0
0x4da8  stfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration <>c__DisplayClass11_0::orgConfiguration
0x4dad  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings> Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::orgSettingsLightCache
0x4db2  ldloc.0
0x4db3  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration <>c__DisplayClass11_0::orgConfiguration
0x4db8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x4dbd  ldloc.0
0x4dbe  ldftn    instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings <>c__DisplayClass11_0::<IsMailboxForcedUnlockingEnabled>b__0(valuetype [mscorlib]System.Guid orgId)
0x4dc4  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings>::.ctor(object, native int)
0x4dc9  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings>::GetOrAdd(void, var<u1>)
0x4dce  callvirt instance bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings::get_IsMailboxForcedUnlockingEnabled()
0x4dd3  stloc.1
0x4dd4  leave.s  loc_4DFD
0x4dd6  stloc.2
0x4dd7  ldloc.2
0x4dd8  ldloc.0
0x4dd9  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration <>c__DisplayClass11_0::orgConfiguration
0x4dde  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x4de3  ldc.i4.s 0x15
0x4de5  ldstr    aExceptionWhile_5// "Exception while fetching 'IsMailboxForc"...
0x4dea  ldc.i4.1
0x4deb  newarr   [mscorlib]System.Object
0x4df0  dup
0x4df1  ldc.i4.0
0x4df2  ldloc.2
0x4df3  stelem.ref
0x4df4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4df9  ldc.i4.1
0x4dfa  stloc.1
0x4dfb  leave.s  loc_4DFD
0x4dfd  ldloc.1
0x4dfe  ret
```
