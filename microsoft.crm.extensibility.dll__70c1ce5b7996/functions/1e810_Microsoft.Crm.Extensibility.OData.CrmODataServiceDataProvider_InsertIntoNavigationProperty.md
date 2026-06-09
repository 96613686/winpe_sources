# Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::InsertIntoNavigationProperty

- ea: `0x1e810`
- end: `0x1e926`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::InsertIntoNavigationProperty`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x11730`

## callees

- `0xf6f0`
- `0xf740`
- `0xf7c0`
- `0x133e0`
- `0x1e810`
- `0x1f820`
- `0x21370`
- `0x24c10`

## pseudocode

```c

```

## disassembly

```asm
0x1e810  ldarg.2
0x1e811  ldarg.0
0x1e812  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e817  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e81c  ldarg.s  4
0x1e81e  call     class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship> Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetRelationshipInformation(class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType edmEntityType, string propertyName)
0x1e823  stloc.0
0x1e824  ldloc.0
0x1e825  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Item1()
0x1e82a  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmLinkedEntityName(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty navigationProperty)
0x1e82f  stloc.1
0x1e830  ldloc.1
0x1e831  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EdmEntityProvider::IsContainedEntity(string)
0x1e836  brtrue.s loc_1E88B
0x1e838  ldloc.0
0x1e839  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Item1()
0x1e83e  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::DeclaringEntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty)
0x1e843  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType::get_BaseType()
0x1e848  call     string [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::FullTypeName(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType)
0x1e84d  ldstr    aMicrosoftDynam_14// "Microsoft.Dynamics.CRM.activitypointer"
0x1e852  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1e857  brtrue.s loc_1E88B
0x1e859  ldloc.0
0x1e85a  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Item1()
0x1e85f  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmProperty::get_Type()
0x1e864  call     string [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::FullName(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x1e869  ldstr    aCollectionMicr// "Collection(Microsoft.Dynamics.CRM.activ"...
0x1e86e  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1e873  brtrue.s loc_1E88B
0x1e875  ldc.i4   0x195
0x1e87a  ldstr    aPostOnNavigati// "Post on Navigation Property is only sup"...
0x1e87f  ldc.i4.0
0x1e880  newarr   [mscorlib]System.Object
0x1e885  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x1e88a  throw
0x1e88b  ldarg.2
0x1e88c  ldarg.3
0x1e88d  ldarg.0
0x1e88e  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e893  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetXrmEntityReferenceForKeys(string edmEntityName, string key, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e898  stloc.2
0x1e899  ldarg.2
0x1e89a  ldarg.0
0x1e89b  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e8a0  call     class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObject Microsoft.Crm.Extensibility.OData.EdmUtilities::CreateNewEdmEntityObject(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e8a5  ldloc.2
0x1e8a6  ldarg.0
0x1e8a7  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e8ac  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Extensibility.OData.EdmTypeConverter::ConvertToCrmEntity(class [System.Web.OData]System.Web.OData.EdmEntityObject edmEntity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference entityReference, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e8b1  stloc.3
0x1e8b2  ldloc.0
0x1e8b3  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmNavigationProperty, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship>::get_Item2()
0x1e8b8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_SchemaName()
0x1e8bd  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship::.ctor(string)
0x1e8c2  stloc.s  4
0x1e8c4  ldloc.3
0x1e8c5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelatedEntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x1e8ca  ldloc.s  4
0x1e8cc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x1e8d1  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::.ctor(class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>)
0x1e8d6  dup
0x1e8d7  ldloc.1
0x1e8d8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::set_EntityName(string)
0x1e8dd  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::set_Item(var<u1>, !!T0)
0x1e8e2  ldarg.s  5
0x1e8e4  ldnull
0x1e8e5  ldarg.0
0x1e8e6  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::edmModel
0x1e8eb  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Extensibility.OData.EdmTypeConverter::ConvertToCrmEntity(class [System.Web.OData]System.Web.OData.EdmEntityObject edmEntity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference entityReference, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1e8f0  stloc.s  5
0x1e8f2  ldloc.s  5
0x1e8f4  ldc.i4.1
0x1e8f5  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState>::.ctor(var<u1>)
0x1e8fa  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_EntityState(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState>)
0x1e8ff  ldloc.3
0x1e900  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelatedEntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x1e905  ldloc.s  4
0x1e907  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::get_Item(void)
0x1e90c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1e911  ldloc.s  5
0x1e913  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x1e918  ldarg.1
0x1e919  ldloc.3
0x1e91a  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::Update(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x1e91f  ldloc.3
0x1e920  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x1e925  ret
```
