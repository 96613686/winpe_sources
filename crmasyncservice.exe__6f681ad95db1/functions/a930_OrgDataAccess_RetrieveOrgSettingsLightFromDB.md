# OrgDataAccess::RetrieveOrgSettingsLightFromDB

- ea: `0xa930`
- end: `0xa988`
- name: `OrgDataAccess::RetrieveOrgSettingsLightFromDB`
- size: `88`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callers

- `0xaa20`
- `0xaa60`
- `0xaaa0`

## callees

- `0xbc70`

## string_xrefs

- `0xa958`: `Select Server Side Sync related Org Settings From OrgDatabase`

## pseudocode

```c

```

## disassembly

```asm
0xa930  newobj   instance void <>c__DisplayClass2_0::.ctor()
0xa935  stloc.0
0xa936  ldloc.0
0xa937  ldarg.1
0xa938  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass2_0::organizationId
0xa93d  ldloc.0
0xa93e  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings::.ctor()
0xa943  stfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings <>c__DisplayClass2_0::orgSettingsLight
0xa948  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation>::.ctor()
0xa94d  ldarg.0
0xa94e  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration OrgDataAccess::serverConfiguration
0xa953  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IServiceConfiguration::get_OperationsFactory()
0xa958  ldstr    aSelectServerSi// "Select Server Side Sync related Org Set"...
0xa95d  ldarg.0
0xa95e  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0xa963  ldloc.0
0xa964  ldftn    instance void <>c__DisplayClass2_0::<RetrieveOrgSettingsLightFromDB>b__0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation serviceOperation)
0xa96a  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0xa96f  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0xa974  stloc.1
0xa975  dup
0xa976  ldloc.1
0xa977  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation>::Add(var<u1>)
0xa97c  call     void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.SequentialExecutionEngine::ExecuteOperations(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation>)
0xa981  ldloc.0
0xa982  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncOrgSettings <>c__DisplayClass2_0::orgSettingsLight
0xa987  ret
```
