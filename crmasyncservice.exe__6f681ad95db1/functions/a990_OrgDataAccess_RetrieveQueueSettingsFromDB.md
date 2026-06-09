# OrgDataAccess::RetrieveQueueSettingsFromDB

- ea: `0xa990`
- end: `0xa9e8`
- name: `OrgDataAccess::RetrieveQueueSettingsFromDB`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0xaae0`
- `0xab20`

## callees

- `0xbcb0`

## pseudocode

```c

```

## disassembly

```asm
0xa990  newobj   instance void <>c__DisplayClass3_0::.ctor()
0xa995  stloc.0
0xa996  ldloc.0
0xa997  ldarg.1
0xa998  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass3_0::organizationId
0xa99d  ldloc.0
0xa99e  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings::.ctor()
0xa9a3  stfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings <>c__DisplayClass3_0::queueSettings
0xa9a8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation>::.ctor()
0xa9ad  ldarg.0
0xa9ae  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration OrgDataAccess::serverConfiguration
0xa9b3  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IServiceConfiguration::get_OperationsFactory()
0xa9b8  ldstr    aSelectQueueSet// "Select Queue Settings From OrgDatabase"
0xa9bd  ldarg.0
0xa9be  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0xa9c3  ldloc.0
0xa9c4  ldftn    instance void <>c__DisplayClass3_0::<RetrieveQueueSettingsFromDB>b__0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation serviceOperation)
0xa9ca  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0xa9cf  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0xa9d4  stloc.1
0xa9d5  dup
0xa9d6  ldloc.1
0xa9d7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation>::Add(var<u1>)
0xa9dc  call     void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.SequentialExecutionEngine::ExecuteOperations(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation>)
0xa9e1  ldloc.0
0xa9e2  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailboxUtil/ServerSideSyncAsyncQueueSettings <>c__DisplayClass3_0::queueSettings
0xa9e7  ret
```
