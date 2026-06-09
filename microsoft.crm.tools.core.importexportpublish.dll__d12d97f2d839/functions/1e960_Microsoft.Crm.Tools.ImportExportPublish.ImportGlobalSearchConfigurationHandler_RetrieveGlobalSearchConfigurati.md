# Microsoft.Crm.Tools.ImportExportPublish.ImportGlobalSearchConfigurationHandler::RetrieveGlobalSearchConfiguration

- ea: `0x1e960`
- end: `0x1e9ed`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportGlobalSearchConfigurationHandler::RetrieveGlobalSearchConfiguration`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1e7a0`

## string_xrefs

- `0x1e960`: `GlobalSearchConfiguration`
- `0x1e96c`: `GlobalSearchConfiguration`
- `0x1e986`: `globalsearchconfigurationid`
- `0x1e9bf`: `globalsearchconfigurationid`

## pseudocode

```c

```

## disassembly

```asm
0x1e960  ldstr    aGlobalsearchco// "GlobalSearchConfiguration"
0x1e965  ldarg.3
0x1e966  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1e96b  stloc.0
0x1e96c  ldstr    aGlobalsearchco// "GlobalSearchConfiguration"
0x1e971  ldarg.3
0x1e972  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1e977  stloc.1
0x1e978  ldloc.1
0x1e979  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1e97e  ldc.i4.6
0x1e97f  newarr   [mscorlib]System.String
0x1e984  dup
0x1e985  ldc.i4.0
0x1e986  ldstr    aGlobalsearchco_0// "globalsearchconfigurationid"
0x1e98b  stelem.ref
0x1e98c  dup
0x1e98d  ldc.i4.1
0x1e98e  ldstr    aSearchprovider_0// "searchproviderresultspage"
0x1e993  stelem.ref
0x1e994  dup
0x1e995  ldc.i4.2
0x1e996  ldstr    aIslocalized// "islocalized"
0x1e99b  stelem.ref
0x1e99c  dup
0x1e99d  ldc.i4.3
0x1e99e  ldstr    aIsenabled_0// "isenabled"
0x1e9a3  stelem.ref
0x1e9a4  dup
0x1e9a5  ldc.i4.4
0x1e9a6  ldstr    aIssearchboxvis// "issearchboxvisible"
0x1e9ab  stelem.ref
0x1e9ac  dup
0x1e9ad  ldc.i4.5
0x1e9ae  ldstr    aSearchprovider// "searchprovidername"
0x1e9b3  stelem.ref
0x1e9b4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x1e9b9  ldloc.1
0x1e9ba  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1e9bf  ldstr    aGlobalsearchco_0// "globalsearchconfigurationid"
0x1e9c4  ldc.i4.0
0x1e9c5  ldarg.1
0x1e9c6  box      [mscorlib]System.Guid
0x1e9cb  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1e9d0  pop
0x1e9d1  ldloc.1
0x1e9d2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1e9d7  ldstr    aSearchprovider// "searchprovidername"
0x1e9dc  ldc.i4.0
0x1e9dd  ldarg.2
0x1e9de  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x1e9e3  pop
0x1e9e4  ldloc.0
0x1e9e5  ldloc.1
0x1e9e6  ldarg.3
0x1e9e7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1e9ec  ret
```
