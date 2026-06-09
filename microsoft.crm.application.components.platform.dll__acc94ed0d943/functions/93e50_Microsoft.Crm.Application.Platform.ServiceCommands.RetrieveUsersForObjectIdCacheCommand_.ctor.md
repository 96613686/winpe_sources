# Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveUsersForObjectIdCacheCommand::.ctor

- ea: `0x93e50`
- end: `0x93ec2`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveUsersForObjectIdCacheCommand::.ctor`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x12380`

## callees

- `0x90d70`
- `0x90e30`
- `0x90e40`
- `0x94440`

## string_xrefs

- `0x93e7d`: `azureactivedirectoryobjectid`
- `0x93e93`: `azureactivedirectoryobjectid`

## pseudocode

```c

```

## disassembly

```asm
0x93e50  ldarg.0
0x93e51  ldstr    aSystemuser// "systemuser"
0x93e56  ldarg.2
0x93e57  call     instance void Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::.ctor(string entityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x93e5c  ldstr    aSystemuser// "systemuser"
0x93e61  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x93e66  stloc.0
0x93e67  ldloc.0
0x93e68  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x93e6d  ldc.i4.2
0x93e6e  newarr   [mscorlib]System.String
0x93e73  dup
0x93e74  ldc.i4.0
0x93e75  ldstr    aSystemuserid// "systemuserid"
0x93e7a  stelem.ref
0x93e7b  dup
0x93e7c  ldc.i4.1
0x93e7d  ldstr    aAzureactivedir_0// "azureactivedirectoryobjectid"
0x93e82  stelem.ref
0x93e83  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x93e88  ldloc.0
0x93e89  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x93e8e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0x93e93  ldstr    aAzureactivedir_0// "azureactivedirectoryobjectid"
0x93e98  ldc.i4.0
0x93e99  ldarga.s 1
0x93e9b  ldstr    aN// "N"
0x93ea0  call     instance string [mscorlib]System.Guid::ToString(string)
0x93ea5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x93eaa  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0x93eaf  ldarg.0
0x93eb0  ldloc.0
0x93eb1  ldarg.2
0x93eb2  newobj   instance void Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMultipleCommand::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x93eb7  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::get_XrmRequestInternal()
0x93ebc  call     instance void Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::set_XrmRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest value)
0x93ec1  ret
```
