# Microsoft.Crm.ObjectModel.CustomControlsDefaultConfigDependencyCalculator::SetGridFormDependencies

- ea: `0x19c5f0`
- end: `0x19c8d0`
- name: `Microsoft.Crm.ObjectModel.CustomControlsDefaultConfigDependencyCalculator::SetGridFormDependencies`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x19c300`

## callees

- `0x19c2c0`
- `0x19c5b0`
- `0x19c5f0`
- `0x19cb60`
- `0x19cc00`
- `0x19fb00`
- `0x1a0ff0`
- `0x1a7ec0`

## string_xrefs

- `0x19c617`: `CustomControlDefaultConfig`
- `0x19c630`: `CustomControlDefaultConfig`
- `0x19c6c7`: `CustomControlDefaultConfig`
- `0x19c6bc`: `componentstate`
- `0x19c701`: `componentstate`
- `0x19c6a3`: `eventsxml`
- `0x19c722`: `eventsxml`
- `0x19c73d`: `eventsxml`
- `0x19c63e`: `customcontroldefaultconfigid`
- `0x19c653`: `customcontroldefaultconfigid`

## pseudocode

```c

```

## disassembly

```asm
0x19c5f0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x19c5f5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x19c5fa  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_EditableGridControlJsEvents()
0x19c5ff  ldarg.s  4
0x19c601  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19c606  brfalse  loc_19C8CF
0x19c60b  ldarg.3
0x19c60c  ldc.i4.4
0x19c60d  ceq
0x19c60f  stloc.0
0x19c610  ldarg.s  4
0x19c612  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x19c617  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x19c61c  ldc.i4.0
0x19c61d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x19c622  stloc.1
0x19c623  ldloc.1
0x19c624  brtrue.s loc_19C629
0x19c626  ldc.i4.0
0x19c627  br.s     loc_19C62F
0x19c629  ldloc.1
0x19c62a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsPublishable()
0x19c62f  stloc.2
0x19c630  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x19c635  ldarg.s  4
0x19c637  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x19c63c  stloc.3
0x19c63d  ldarg.2
0x19c63e  ldstr    aCustomcontrold_4// "customcontroldefaultconfigid"
0x19c643  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19c648  brtrue.s loc_19C652
0x19c64a  ldarg.2
0x19c64b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Moniker()
0x19c650  brtrue.s loc_19C664
0x19c652  ldarg.2
0x19c653  ldstr    aCustomcontrold_4// "customcontroldefaultconfigid"
0x19c658  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19c65d  unbox.any [mscorlib]System.Guid
0x19c662  br.s     loc_19C66F
0x19c664  ldarg.2
0x19c665  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Moniker()
0x19c66a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x19c66f  stloc.s  4
0x19c671  ldloc.3
0x19c672  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x19c677  ldloc.3
0x19c678  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x19c67d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x19c682  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x19c687  ldc.i4.0
0x19c688  ldloc.s  4
0x19c68a  box      [mscorlib]System.Guid
0x19c68f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x19c694  pop
0x19c695  ldloc.3
0x19c696  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x19c69b  ldc.i4.1
0x19c69c  newarr   [mscorlib]System.String
0x19c6a1  dup
0x19c6a2  ldc.i4.0
0x19c6a3  ldstr    aEventsxml// "eventsxml"
0x19c6a8  stelem.ref
0x19c6a9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x19c6ae  ldloc.3
0x19c6af  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x19c6b4  ldc.i4.1
0x19c6b5  newarr   [mscorlib]System.String
0x19c6ba  dup
0x19c6bb  ldc.i4.0
0x19c6bc  ldstr    aComponentstate_0// "componentstate"
0x19c6c1  stelem.ref
0x19c6c2  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x19c6c7  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x19c6cc  ldarg.s  4
0x19c6ce  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19c6d3  ldloc.3
0x19c6d4  ldloc.2
0x19c6d5  ldloc.0
0x19c6d6  and
0x19c6d7  ldarg.s  4
0x19c6d9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveForDependencyCalculation(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x19c6de  stloc.s  5
0x19c6e0  ldloc.s  5
0x19c6e2  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x19c6e7  ldc.i4.0
0x19c6e8  ble      loc_19C8CF
0x19c6ed  ldsfld   string [mscorlib]System.String::Empty
0x19c6f2  stloc.s  6
0x19c6f4  ldloc.2
0x19c6f5  ldloc.0
0x19c6f6  and
0x19c6f7  brfalse.s loc_19C735
0x19c6f9  ldloc.s  5
0x19c6fb  ldc.i4.0
0x19c6fc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x19c701  ldstr    aComponentstate_0// "componentstate"
0x19c706  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19c70b  unbox.any [mscorlib]System.Int32
0x19c710  ldc.i4.1
0x19c711  beq.s    loc_19C71A
0x19c713  ldsfld   string [mscorlib]System.String::Empty
0x19c718  br.s     loc_19C731
0x19c71a  ldloc.s  5
0x19c71c  ldc.i4.0
0x19c71d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x19c722  ldstr    aEventsxml// "eventsxml"
0x19c727  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19c72c  castclass [mscorlib]System.String
0x19c731  stloc.s  6
0x19c733  br.s     loc_19C74E
0x19c735  ldloc.s  5
0x19c737  ldc.i4.0
0x19c738  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x19c73d  ldstr    aEventsxml// "eventsxml"
0x19c742  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19c747  castclass [mscorlib]System.String
0x19c74c  stloc.s  6
0x19c74e  ldloc.s  6
0x19c750  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19c755  brtrue   loc_19C8CF
0x19c75a  ldarg.0
0x19c75b  ldloc.s  6
0x19c75d  ldarg.3
0x19c75e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>>::.ctor()
0x19c763  ldarg.0
0x19c764  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.DependencyCalculator::get_LocalDependencyNode()
0x19c769  brtrue.s loc_19C777
0x19c76b  ldloca.s 8
0x19c76d  initobj  [mscorlib]System.Guid
0x19c773  ldloc.s  8
0x19c775  br.s     loc_19C78C
0x19c777  ldarg.0
0x19c778  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.ObjectModel.DependencyCalculator::get_LocalDependencyNode()
0x19c77d  ldstr    aObjectid// "objectid"
0x19c782  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x19c787  unbox.any [mscorlib]System.Guid
0x19c78c  ldarg.0
0x19c78d  ldftn    instance void Microsoft.Crm.ObjectModel.DependencyCalculator::CreateInvalidAncestorDependency(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DependencyTypes dependencyType, valuetype Microsoft.Crm.ObjectModel.MissingDependencyLookupType lookupType, object lookupInfo, int32 componentType, valuetype Microsoft.Crm.ObjectModel.InvalidDependencyExceptionOption exceptionOption, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x19c793  newobj   instance void Microsoft.Crm.ObjectModel.CreateInvalidAncestorDependencyHandler::.ctor(object object, native int method)
0x19c798  ldarg.s  4
0x19c79a  call     class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.ObjectModel.ComponentInfo> Microsoft.Crm.ObjectModel.JavaScriptLibraryDependencyCalculator::GetDependentComponentInfo(string formXml, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DependencyTypes type, class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, string>> allowedInvalidDependencies, valuetype [mscorlib]System.Guid existingComponentId, class Microsoft.Crm.ObjectModel.CreateInvalidAncestorDependencyHandler invalidAncestorHandler, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x19c79f  ldarg.3
0x19c7a0  ldarg.s  4
0x19c7a2  call     instance void Microsoft.Crm.ObjectModel.CustomControlsDefaultConfigDependencyCalculator::SetAncestorsFromList(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.ObjectModel.ComponentInfo> components, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DependencyTypes type, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x19c7a7  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x19c7ac  pop
0x19c7ad  ldloc.s  6
0x19c7af  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x19c7b4  ldstr    aEvent_0// "//event"
0x19c7b9  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x19c7be  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x19c7c3  stloc.s  7
0x19c7c5  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x19c7ca  stloc.s  9
0x19c7cc  br       loc_19C8AC
0x19c7d1  ldloc.s  9
0x19c7d3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x19c7d8  castclass [System.Xml]System.Xml.XmlNode
0x19c7dd  stloc.s  0xA
0x19c7df  ldloc.s  0xA
0x19c7e1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x19c7e6  ldstr    aAttribute_0// "attribute"
0x19c7eb  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x19c7f0  brtrue.s loc_19C7F9
0x19c7f2  ldsfld   string [mscorlib]System.String::Empty
0x19c7f7  br.s     loc_19C80F
0x19c7f9  ldloc.s  0xA
0x19c7fb  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x19c800  ldstr    aAttribute_0// "attribute"
0x19c805  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x19c80a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x19c80f  stloc.s  0xB
0x19c811  ldloc.s  0xA
0x19c813  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x19c818  ldstr    aRelationship_0// "relationship"
0x19c81d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x19c822  brtrue.s loc_19C82B
0x19c824  ldsfld   string [mscorlib]System.String::Empty
0x19c829  br.s     loc_19C841
0x19c82b  ldloc.s  0xA
0x19c82d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x19c832  ldstr    aRelationship_0// "relationship"
0x19c837  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x19c83c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x19c841  stloc.s  0xC
0x19c843  ldloc.s  0xC
0x19c845  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19c84a  brtrue.s loc_19C859
0x19c84c  ldarg.0
0x19c84d  ldloc.s  0xC
0x19c84f  ldarg.3
0x19c850  ldarg.s  4
0x19c852  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.CustomControlsDefaultConfigDependencyCalculator::GetEntityId(string logicalEntityName, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DependencyTypes type, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x19c857  br.s     loc_19C85A
0x19c859  ldarg.1
0x19c85a  stloc.s  0xD
0x19c85c  ldloc.s  0xB
0x19c85e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19c863  brtrue.s loc_19C8AC
0x19c865  ldloc.s  0xA
0x19c867  ldstr    aHandlersHandle_0// "./Handlers/Handler"
0x19c86c  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x19c871  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x19c876  ldc.i4.0
0x19c877  ble.s    loc_19C8AC
0x19c879  ldloc.s  0xD
0x19c87b  ldloc.s  0xB
0x19c87d  ldarg.3
0x19c87e  ldarg.s  4
0x19c880  call     valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.FormAttributeDependencyCalculator::GetAttributeId(valuetype [mscorlib]System.Guid entityId, string attrSchemaName, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DependencyTypes type, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x19c885  stloc.s  0xE
0x19c887  ldloc.s  0xE
0x19c889  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x19c88e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x19c893  brfalse.s loc_19C8AC
0x19c895  ldloc.s  7
0x19c897  ldloc.s  0xE
0x19c899  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x19c89e  brfalse.s loc_19C8AC
0x19c8a0  ldarg.0
0x19c8a1  ldloc.s  0xE
0x19c8a3  ldc.i4.2
0x19c8a4  ldarg.3
0x19c8a5  ldarg.s  4
0x19c8a7  callvirt instance void Microsoft.Crm.ObjectModel.DependencyCalculator::SetAncestor(valuetype [mscorlib]System.Guid id, int32 componentType, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DependencyTypes dependencyType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x19c8ac  ldloc.s  9
0x19c8ae  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19c8b3  brtrue   loc_19C7D1
0x19c8b8  leave.s  loc_19C8CF
0x19c8ba  ldloc.s  9
0x19c8bc  isinst   [mscorlib]System.IDisposable
0x19c8c1  stloc.s  0xF
0x19c8c3  ldloc.s  0xF
0x19c8c5  brfalse.s loc_19C8CE
0x19c8c7  ldloc.s  0xF
0x19c8c9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19c8ce  endfinally
0x19c8cf  ret
```
