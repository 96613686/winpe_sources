# Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GenerateFormDependencies

- ea: `0x64490`
- end: `0x64565`
- name: `Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GenerateFormDependencies`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x63c60`

## callees

- `0x64490`

## string_xrefs

- `0x644d3`: `formjson`
- `0x6450c`: `formjson`

## pseudocode

```c

```

## disassembly

```asm
0x64490  ldarg.2
0x64491  callvirt instance object [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_Data()
0x64496  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x6449b  stloc.0
0x6449c  ldnull
0x6449d  stloc.1
0x6449e  ldnull
0x6449f  stloc.2
0x644a0  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::.ctor()
0x644a5  dup
0x644a6  ldc.i4.3
0x644a7  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_TypeNameHandling(valuetype [Newtonsoft.Json]Newtonsoft.Json.TypeNameHandling)
0x644ac  dup
0x644ad  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.SerializationBinder::.ctor()
0x644b2  callvirt instance void [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings::set_Binder(class [mscorlib]System.Runtime.Serialization.SerializationBinder)
0x644b7  stloc.3
0x644b8  ldloc.0
0x644b9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x644be  ldstr    aSystemform// "SystemForm"
0x644c3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x644c8  brfalse.s loc_644EB
0x644ca  ldloc.0
0x644cb  ldarg.3
0x644cc  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.SystemFormGenerator::GetSystemForm(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x644d1  stloc.1
0x644d2  ldloc.1
0x644d3  ldstr    aFormjson// "formjson"
0x644d8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x644dd  callvirt instance string [mscorlib]System.Object::ToString()
0x644e2  ldloc.3
0x644e3  call     T0x2B00005F
0x644e8  stloc.2
0x644e9  br.s     loc_64522
0x644eb  ldloc.0
0x644ec  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x644f1  ldstr    aUserform// "UserForm"
0x644f6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x644fb  brfalse.s loc_64522
0x644fd  ldloc.0
0x644fe  ldarg.3
0x644ff  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.UserDashboardGenerator::GetUserDashboard(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x64504  stloc.1
0x64505  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.FormXmlParser::.ctor()
0x6450a  pop
0x6450b  ldloc.1
0x6450c  ldstr    aFormjson// "formjson"
0x64511  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64516  callvirt instance string [mscorlib]System.Object::ToString()
0x6451b  ldloc.3
0x6451c  call     T0x2B00005F
0x64521  stloc.2
0x64522  ldarg.1
0x64523  ldloc.2
0x64524  ldarg.2
0x64525  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_QueryContext()
0x6452a  ldarg.3
0x6452b  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.MetadataService.Utility.ClientMetadataHelper::AddHiddenAttributes(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem>, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Form, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x64530  ldarg.1
0x64531  ldloc.2
0x64532  ldarg.2
0x64533  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_QueryContext()
0x64538  ldarg.3
0x64539  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.MetadataService.Utility.ClientMetadataHelper::AddWebResources(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem>, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Form, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6453e  ldarg.1
0x6453f  ldloc.2
0x64540  ldarg.2
0x64541  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_QueryContext()
0x64546  ldarg.3
0x64547  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.MetadataService.Utility.ClientMetadataHelper::AddCustomControls(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem>, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormXmlToJsonUtil.Descriptors.Form, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6454c  ldarg.1
0x6454d  ldloc.1
0x6454e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x64553  unbox.any [mscorlib]System.Guid
0x64558  ldarg.2
0x64559  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem::get_QueryContext()
0x6455e  ldarg.3
0x6455f  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.MetadataService.Utility.ClientMetadataHelper::AddLabels(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CandidateItem>, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.QueryContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x64564  ret
```
