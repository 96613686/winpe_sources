# Microsoft.Crm.Sdk.CrmServiceInternal::Retrieve

- ea: `0x7d0`
- end: `0x873`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::Retrieve`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xab80`

## callees

- `0x990`
- `0x9d0`

## pseudocode

```c

```

## disassembly

```asm
0x7d0  ldarg.0
0x7d1  ldstr    aRetrieve// "Retrieve"
0x7d6  ldstr    aRetrieve// "Retrieve"
0x7db  ldarg.1
0x7dc  ldarg.2
0x7dd  call     instance int32 Microsoft.Crm.Sdk.CrmServiceInternal::VerifyAndRetrieveEntityForCategoryMessage(string messageName, string categoryName, string namespaceName, string entityName)
0x7e2  stloc.0
0x7e3  ldarg.2
0x7e4  ldarg.3
0x7e5  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker::.ctor(string, valuetype [mscorlib]System.Guid)
0x7ea  stloc.1
0x7eb  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection::.ctor()
0x7f0  stloc.2
0x7f1  ldloc.2
0x7f2  ldstr    aTarget// "Target"
0x7f7  ldloc.1
0x7f8  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x7fd  ldloc.2
0x7fe  ldstr    aColumnset// "columnset"
0x803  ldarg.s  4
0x805  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x80a  ldloc.2
0x80b  ldstr    aRelatedentitie// "RelatedEntitiesQuery"
0x810  ldnull
0x811  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x816  ldloc.2
0x817  ldstr    aOptionalparame// "OptionalParameters"
0x81c  ldc.i4.0
0x81d  newarr   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x822  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x827  ldarg.0
0x828  ldstr    aRetrieve// "Retrieve"
0x82d  ldstr    aRetrieve// "Retrieve"
0x832  ldloc.0
0x833  ldloc.2
0x834  ldarg.s  5
0x836  ldarg.s  6
0x838  ldarg.s  7
0x83a  ldarg.s  8
0x83c  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Sdk.CrmServiceInternal::ExecuteRequest(string messageName, string requestName, int32 primaryObjectTypeCode, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection fields, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken originToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid callerId)
0x841  stloc.3
0x842  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionContextFactory [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionContextFactory::get_Instance()
0x847  ldarg.s  7
0x849  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0x84e  ldc.i4.0
0x84f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.ConversionContextFactory::CreateInstance(valuetype [mscorlib]System.Guid, int32)
0x854  stloc.s  4
0x856  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityToDynamicEntityConverter::.ctor()
0x85b  ldloc.s  4
0x85d  ldloc.3
0x85e  ldstr    aBusinessentity// "BusinessEntity"
0x863  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x868  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x86d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityToDynamicEntityConverter::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x872  ret
```
