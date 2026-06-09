# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterCreatePlugin::Create

- ea: `0x880`
- end: `0xab4`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterCreatePlugin::Create`
- size: `564`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x880`
- `0x1460`
- `0x1530`
- `0x1550`

## pseudocode

```c

```

## disassembly

```asm
0x880  nop
0x881  ldarg.1
0x882  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x887  ldstr    aTarget// "Target"
0x88c  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x891  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x896  stloc.0
0x897  ldstr    aEntitydatasour// "entitydatasource"
0x89c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x8a1  stloc.1
0x8a2  ldloc.0
0x8a3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x8a8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8ad  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8b2  stloc.s  0xB
0x8b4  ldloc.s  0xB
0x8b6  brfalse.s loc_8D5
0x8b8  nop
0x8b9  ldloc.1
0x8ba  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x8bf  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x8c4  nop
0x8c5  ldloc.0
0x8c6  ldloc.1
0x8c7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x8cc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x8d1  nop
0x8d2  nop
0x8d3  br.s     loc_8E4
0x8d5  nop
0x8d6  ldloc.1
0x8d7  ldloc.0
0x8d8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x8dd  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x8e2  nop
0x8e3  nop
0x8e4  ldarg.2
0x8e5  newobj   instance void [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.DefaultTypeMapFactory::.ctor()
0x8ea  ldnull
0x8eb  call     class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMap [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMapFactory::Create(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.ITypeMapFactory, string)
0x8f0  stloc.2
0x8f1  ldloc.0
0x8f2  ldloc.2
0x8f3  call     T0x2B000009
0x8f8  stloc.3
0x8f9  ldloc.2
0x8fa  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.AttributeMap> [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMap::get_AttributeMap()
0x8ff  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.AttributeMap, bool> class <>c__2`1<mvar<u1>>::<>9__2_0
0x904  dup
0x905  brtrue.s loc_91E
0x907  pop
0x908  ldsfld   class <>c__2`1<var<u1>> class <>c__2`1<mvar<u1>>::<>9
0x90d  ldftn    instance bool class <>c__2`1<mvar<u1>>::<Create>b__2_0(class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.AttributeMap)
0x913  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.AttributeMap, bool>::.ctor(object, native int)
0x918  dup
0x919  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.AttributeMap, bool> class <>c__2`1<mvar<u1>>::<>9__2_0
0x91e  call     T0x2B00000A
0x923  stloc.s  4
0x925  ldloc.s  4
0x927  callvirt instance class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.NameMap [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.AttributeMap::get_NameMap()
0x92c  callvirt instance string [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.NameMap::get_ExternalName()
0x931  stloc.s  5
0x933  ldsfld   class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, class [mscorlib]System.Reflection.PropertyInfo> class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.TypeReflector`1<mvar<u1>>::TypeProperties
0x938  ldloc.s  5
0x93a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, class [mscorlib]System.Reflection.PropertyInfo>::get_Item(void)
0x93f  ldloc.3
0x940  box      mvar<u1>
0x945  ldloc.1
0x946  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x94b  box      [mscorlib]System.Guid
0x950  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object)
0x955  nop
0x956  ldloc.3
0x957  box      mvar<u1>
0x95c  ldtoken  mvar<u1>
0x961  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x966  ldsfld   class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings Microsoft.Xrm.DataProvider.JsonConverter.Plugins.State::SecureJsonSerializerSettings
0x96b  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object, class [mscorlib]System.Type, class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings)
0x970  ldarg.2
0x971  call     class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSourceConverter::GetDefinitionString(string entityToCreate, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata entityMetadata)
0x976  stloc.s  6
0x978  ldloc.1
0x979  ldstr    aConnectiondefi// "connectiondefinition"
0x97e  ldloc.s  6
0x980  callvirt instance string Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::get_ConnectionDefinition()
0x985  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x98a  nop
0x98b  ldloc.1
0x98c  ldstr    aConnectiondefi_0// "connectiondefinitionsecrets"
0x991  ldloc.s  6
0x993  callvirt instance string Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::get_ConnectionDefinitionSecrets()
0x998  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x99d  nop
0x99e  ldarg.2
0x99f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_PrimaryNameAttribute()
0x9a4  ldnull
0x9a5  cgt.un
0x9a7  stloc.s  0xC
0x9a9  ldloc.s  0xC
0x9ab  brfalse.s loc_9C7
0x9ad  nop
0x9ae  ldloc.1
0x9af  ldstr    aName// "name"
0x9b4  ldloc.0
0x9b5  ldarg.2
0x9b6  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_PrimaryNameAttribute()
0x9bb  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x9c0  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x9c5  nop
0x9c6  nop
0x9c7  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor()
0x9cc  stloc.s  7
0x9ce  ldloc.s  7
0x9d0  ldc.i4.1
0x9d1  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(bool)
0x9d6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x9db  nop
0x9dc  ldloc.s  7
0x9de  ldstr    aEntitydataprov// "entitydataprovider"
0x9e3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_EntityName(string)
0x9e8  nop
0x9e9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor()
0x9ee  stloc.s  8
0x9f0  ldloc.s  8
0x9f2  ldstr    aDatasourcelogi// "datasourcelogicalname"
0x9f7  ldc.i4.0
0x9f8  ldarg.2
0x9f9  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_LogicalName()
0x9fe  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xa03  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression)
0xa08  nop
0xa09  ldloc.s  7
0xa0b  ldloc.s  8
0xa0d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0xa12  nop
0xa13  ldarg.3
0xa14  ldloc.s  7
0xa16  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0xa1b  stloc.s  9
0xa1d  ldloc.s  9
0xa1f  brfalse.s loc_A32
0xa21  ldloc.s  9
0xa23  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xa28  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0xa2d  ldc.i4.0
0xa2e  cgt
0xa30  br.s     loc_A33
0xa32  ldc.i4.0
0xa33  stloc.s  0xD
0xa35  ldloc.s  0xD
0xa37  brfalse.s loc_A7B
0xa39  nop
0xa3a  ldstr    aEntitydataprov// "entitydataprovider"
0xa3f  ldloc.s  9
0xa41  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xa46  ldc.i4.0
0xa47  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0xa4c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xa51  ldstr    aEntitydataprov_0// "entitydataproviderid"
0xa56  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xa5b  callvirt instance string [mscorlib]System.Object::ToString()
0xa60  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa65  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0xa6a  stloc.s  0xE
0xa6c  ldloc.1
0xa6d  ldstr    aEntitydataprov_0// "entitydataproviderid"
0xa72  ldloc.s  0xE
0xa74  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0xa79  nop
0xa7a  nop
0xa7b  ldloc.1
0xa7c  ldstr    aEntitydatasour_0// "entitydatasourceid"
0xa81  ldloc.1
0xa82  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0xa87  box      [mscorlib]System.Guid
0xa8c  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0xa91  nop
0xa92  ldarg.3
0xa93  ldloc.1
0xa94  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Create(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0xa99  stloc.s  0xA
0xa9b  ldarg.1
0xa9c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OutputParameters()
0xaa1  ldstr    aId// "id"
0xaa6  ldloc.s  0xA
0xaa8  box      [mscorlib]System.Guid
0xaad  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xab2  nop
0xab3  ret
```
