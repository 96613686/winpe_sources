# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrieveMultiplePlugin::RetrieveDataSource

- ea: `0xd20`
- end: `0xe06`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrieveMultiplePlugin::RetrieveDataSource`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xd20`

## pseudocode

```c

```

## disassembly

```asm
0xd20  nop
0xd21  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0xd26  stloc.0
0xd27  ldloc.0
0xd28  ldstr    aEntitydatasour// "entitydatasource"
0xd2d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0xd32  nop
0xd33  ldc.i4.3
0xd34  newarr   [mscorlib]System.String
0xd39  dup
0xd3a  ldc.i4.0
0xd3b  ldstr    aConnectiondefi// "connectiondefinition"
0xd40  stelem.ref
0xd41  dup
0xd42  ldc.i4.1
0xd43  ldstr    aConnectiondefi_0// "connectiondefinitionsecrets"
0xd48  stelem.ref
0xd49  dup
0xd4a  ldc.i4.2
0xd4b  ldstr    aName// "name"
0xd50  stelem.ref
0xd51  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0xd56  stloc.1
0xd57  ldloc.0
0xd58  ldloc.1
0xd59  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0xd5e  nop
0xd5f  ldloc.0
0xd60  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0xd65  ldstr    aEntitydatasour// "entitydatasource"
0xd6a  ldstr    aEntitydataprov// "entitydataprovider"
0xd6f  ldstr    aEntitydataprov_0// "entitydataproviderid"
0xd74  ldstr    aEntitydataprov_0// "entitydataproviderid"
0xd79  ldc.i4.0
0xd7a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor(string, string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0xd7f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::Add(var<u1>)
0xd84  nop
0xd85  ldloc.0
0xd86  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0xd8b  ldc.i4.0
0xd8c  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::get_Item(!!T0)
0xd91  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_Columns()
0xd96  ldstr    aDatasourcelogi// "datasourcelogicalname"
0xd9b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0xda0  nop
0xda1  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor()
0xda6  stloc.2
0xda7  ldloc.2
0xda8  ldstr    aDatasourcelogi// "datasourcelogicalname"
0xdad  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_AttributeName(string)
0xdb2  nop
0xdb3  ldloc.2
0xdb4  ldc.i4.0
0xdb5  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::set_Operator(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0xdba  nop
0xdbb  ldloc.2
0xdbc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::get_Values()
0xdc1  ldarg.1
0xdc2  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_LogicalName()
0xdc7  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<object>::Add(var<u1>)
0xdcc  nop
0xdcd  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0xdd2  stloc.3
0xdd3  ldloc.3
0xdd4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::get_Conditions()
0xdd9  ldloc.2
0xdda  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression>::Add(var<u1>)
0xddf  nop
0xde0  ldloc.0
0xde1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0xde6  ldc.i4.0
0xde7  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity>::get_Item(!!T0)
0xdec  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkCriteria()
0xdf1  ldloc.3
0xdf2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddFilter(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0xdf7  nop
0xdf8  ldarg.2
0xdf9  ldloc.0
0xdfa  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0xdff  stloc.s  4
0xe01  br.s     loc_E03
0xe03  ldloc.s  4
0xe05  ret
```
