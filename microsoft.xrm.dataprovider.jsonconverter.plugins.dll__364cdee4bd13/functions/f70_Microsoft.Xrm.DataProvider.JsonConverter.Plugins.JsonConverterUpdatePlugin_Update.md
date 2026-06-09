# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterUpdatePlugin::Update

- ea: `0xf70`
- end: `0x10ca`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterUpdatePlugin::Update`
- size: `346`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0xf70`
- `0x1460`
- `0x1530`
- `0x1540`
- `0x1550`
- `0x1560`
- `0x1570`

## pseudocode

```c

```

## disassembly

```asm
0xf70  nop
0xf71  ldarg.1
0xf72  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0xf77  ldstr    aTarget// "Target"
0xf7c  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xf81  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0xf86  stloc.0
0xf87  ldarg.0
0xf88  ldloc.0
0xf89  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0xf8e  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterUpdatePlugin::attributesToBeUpdated
0xf93  ldarg.2
0xf94  newobj   instance void [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.DefaultTypeMapFactory::.ctor()
0xf99  ldnull
0xf9a  call     class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMap [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMapFactory::Create(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.ITypeMapFactory, string)
0xf9f  stloc.1
0xfa0  ldloc.0
0xfa1  ldloc.1
0xfa2  call     T0x2B000009
0xfa7  stloc.2
0xfa8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor()
0xfad  stloc.3
0xfae  ldloc.3
0xfaf  ldstr    aConnectiondefi// "connectiondefinition"
0xfb4  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0xfb9  nop
0xfba  ldloc.3
0xfbb  ldstr    aConnectiondefi_0// "connectiondefinitionsecrets"
0xfc0  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0xfc5  nop
0xfc6  ldarg.3
0xfc7  ldstr    aEntitydatasour// "entitydatasource"
0xfcc  ldloc.0
0xfcd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0xfd2  ldloc.3
0xfd3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0xfd8  stloc.s  4
0xfda  newobj   instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::.ctor()
0xfdf  stloc.s  5
0xfe1  ldloc.s  5
0xfe3  ldloc.s  4
0xfe5  ldstr    aConnectiondefi// "connectiondefinition"
0xfea  callvirt T0x2B000013
0xfef  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::set_ConnectionDefinition(string value)
0xff4  nop
0xff5  ldloc.s  5
0xff7  ldloc.s  4
0xff9  ldstr    aConnectiondefi_0// "connectiondefinitionsecrets"
0xffe  callvirt T0x2B000013
0x1003  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::set_ConnectionDefinitionSecrets(string value)
0x1008  nop
0x1009  ldloc.s  5
0x100b  call     T0x2B000014
0x1010  stloc.s  6
0x1012  ldarg.0
0x1013  ldloc.2
0x1014  ldloc.s  6
0x1016  ldloc.1
0x1017  call     T0x2B000015
0x101c  stloc.s  7
0x101e  ldstr    aEntitydatasour// "entitydatasource"
0x1023  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x1028  stloc.s  8
0x102a  ldloc.s  8
0x102c  ldloc.0
0x102d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x1032  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x1037  nop
0x1038  ldloc.s  7
0x103a  box      mvar<u1>
0x103f  ldtoken  mvar<u1>
0x1044  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1049  ldsfld   class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings Microsoft.Xrm.DataProvider.JsonConverter.Plugins.State::SecureJsonSerializerSettings
0x104e  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object, class [mscorlib]System.Type, class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings)
0x1053  ldarg.2
0x1054  call     class Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSourceConverter::GetDefinitionString(string entityToCreate, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata entityMetadata)
0x1059  stloc.s  9
0x105b  ldloc.s  8
0x105d  ldstr    aConnectiondefi// "connectiondefinition"
0x1062  ldloc.s  9
0x1064  callvirt instance string Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::get_ConnectionDefinition()
0x1069  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x106e  nop
0x106f  ldloc.s  8
0x1071  ldstr    aConnectiondefi_0// "connectiondefinitionsecrets"
0x1076  ldloc.s  9
0x1078  callvirt instance string Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::get_ConnectionDefinitionSecrets()
0x107d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1082  nop
0x1083  ldarg.2
0x1084  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_PrimaryNameAttribute()
0x1089  brfalse.s loc_109E
0x108b  ldloc.0
0x108c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1091  ldarg.2
0x1092  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_PrimaryNameAttribute()
0x1097  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x109c  br.s     loc_109F
0x109e  ldc.i4.0
0x109f  stloc.s  0xA
0x10a1  ldloc.s  0xA
0x10a3  brfalse.s loc_10C0
0x10a5  nop
0x10a6  ldloc.s  8
0x10a8  ldstr    aName// "name"
0x10ad  ldloc.0
0x10ae  ldarg.2
0x10af  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_PrimaryNameAttribute()
0x10b4  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x10b9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x10be  nop
0x10bf  nop
0x10c0  ldarg.3
0x10c1  ldloc.s  8
0x10c3  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x10c8  nop
0x10c9  ret
```
