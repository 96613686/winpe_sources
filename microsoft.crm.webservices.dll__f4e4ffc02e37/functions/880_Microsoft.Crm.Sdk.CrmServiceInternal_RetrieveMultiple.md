# Microsoft.Crm.Sdk.CrmServiceInternal::RetrieveMultiple

- ea: `0x880`
- end: `0x918`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::RetrieveMultiple`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xabd0`

## callees

- `0x990`
- `0x9d0`

## pseudocode

```c

```

## disassembly

```asm
0x880  ldarg.0
0x881  ldstr    aRetrievemultip// "RetrieveMultiple"
0x886  ldstr    aRetrieve// "Retrieve"
0x88b  ldarg.1
0x88c  ldarg.2
0x88d  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_EntityName()
0x892  call     instance int32 Microsoft.Crm.Sdk.CrmServiceInternal::VerifyAndRetrieveEntityForCategoryMessage(string messageName, string categoryName, string namespaceName, string entityName)
0x897  stloc.0
0x898  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection::.ctor()
0x89d  stloc.1
0x89e  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.QueryFromLegacyQueryVisitor::.ctor()
0x8a3  stloc.2
0x8a4  ldarg.2
0x8a5  ldloc.2
0x8a6  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::Accept(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.IQueryVisitor)
0x8ab  ldloc.1
0x8ac  ldstr    aQuery// "Query"
0x8b1  ldloc.2
0x8b2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.QueryFromLegacyQueryVisitor::get_Query()
0x8b7  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8bc  ldloc.1
0x8bd  ldstr    aOptionalparame// "OptionalParameters"
0x8c2  ldc.i4.0
0x8c3  newarr   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x8c8  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x8cd  ldarg.0
0x8ce  ldstr    aRetrievemultip// "RetrieveMultiple"
0x8d3  ldstr    aRetrievemultip// "RetrieveMultiple"
0x8d8  ldloc.0
0x8d9  ldloc.1
0x8da  ldarg.3
0x8db  ldarg.s  4
0x8dd  ldarg.s  5
0x8df  ldarg.s  6
0x8e1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Sdk.CrmServiceInternal::ExecuteRequest(string messageName, string requestName, int32 primaryObjectTypeCode, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection fields, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken originToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid callerId)
0x8e6  stloc.3
0x8e7  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionContextFactory [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionContextFactory::get_Instance()
0x8ec  ldarg.s  5
0x8ee  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0x8f3  ldc.i4.0
0x8f4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionContextFactory::CreateInstance(valuetype [mscorlib]System.Guid, int32)
0x8f9  stloc.s  4
0x8fb  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityCollectionToDynamicEntityCollectionConverter::.ctor()
0x900  ldloc.s  4
0x902  ldloc.3
0x903  ldstr    aBusinessentity_1// "BusinessEntityCollection"
0x908  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x90d  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection
0x912  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityCollectionToDynamicEntityCollectionConverter::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection)
0x917  ret
```
