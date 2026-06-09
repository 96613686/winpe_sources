# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::SetValueForPartyListAttribute

- ea: `0x1fe00`
- end: `0x1ff85`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::SetValueForPartyListAttribute`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x25fc0`

## callees

- `0xf690`
- `0xfae0`
- `0x13540`
- `0x175f0`
- `0x1fd90`
- `0x1fe00`

## string_xrefs

- `0x1fe06`: `Partylist attributes only supported for communication activities.`

## pseudocode

```c

```

## disassembly

```asm
0x1fe00  ldarg.1
0x1fe01  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsCommunicationActivity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata)
0x1fe06  ldstr    aPartylistAttri// "Partylist attributes only supported for"...
0x1fe0b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1fe10  ldarg.1
0x1fe11  ldarg.2
0x1fe12  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x1fe17  stloc.0
0x1fe18  ldloc.0
0x1fe19  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsLogical()
0x1fe1e  brfalse.s loc_1FE37
0x1fe20  ldloc.0
0x1fe21  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x1fe26  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x1fe2b  ldstr    aPartylist// "partylist"
0x1fe30  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1fe35  brfalse.s loc_1FE38
0x1fe37  ret
0x1fe38  ldarg.s  4
0x1fe3a  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection
0x1fe3f  stloc.1
0x1fe40  ldloc.1
0x1fe41  brfalse.s loc_1FE50
0x1fe43  ldloc.1
0x1fe44  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x1fe49  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x1fe4e  brtrue.s loc_1FE51
0x1fe50  ret
0x1fe51  ldloc.1
0x1fe52  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_EntityName()
0x1fe57  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityNameFromCrmEntityName(string entityName)
0x1fe5c  stloc.2
0x1fe5d  ldarg.0
0x1fe5e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x1fe63  ldarg.s  6
0x1fe65  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntitySet Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntitySet(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1fe6a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationPropertyBinding> [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource::get_NavigationPropertyBindings()
0x1fe6f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationPropertyBinding>::GetEnumerator()
0x1fe74  stloc.3
0x1fe75  br       loc_1FF6D
0x1fe7a  ldloc.3
0x1fe7b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationPropertyBinding>::get_Current()
0x1fe80  stloc.s  4
0x1fe82  ldloc.s  4
0x1fe84  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationPropertyBinding::get_NavigationProperty()
0x1fe89  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x1fe8e  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference::get_Definition()
0x1fe93  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionType
0x1fe98  brfalse  loc_1FF6D
0x1fe9d  ldloc.s  4
0x1fe9f  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationPropertyBinding::get_Target()
0x1fea4  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::EntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource)
0x1fea9  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x1feae  ldloc.2
0x1feaf  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1feb4  brfalse  loc_1FF6D
0x1feb9  ldloc.1
0x1feba  ldloc.2
0x1febb  ldarg.s  6
0x1febd  ldc.i4.0
0x1febe  ldarg.s  5
0x1fec0  ldc.i4.0
0x1fec1  ldnull
0x1fec2  call     class [System.Web.OData]System.Web.OData.EdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.EdmTypeConverter::ConvertToEdmEntityObjectCollection(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection xrmEntityCollection, string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] bool fillDerivedEntityProperties, [opt] bool fillAllProperties, [opt] bool noLock, [opt] class [mscorlib]System.Collections.Generic.List`1<string> navigationPropertyNames)
0x1fec7  ldloc.1
0x1fec8  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_TotalRecordCount()
0x1fecd  ldloc.1
0x1fece  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_TotalRecordCountLimitExceeded()
0x1fed3  ldnull
0x1fed4  ldc.i4.0
0x1fed5  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::.ctor(class [System.Web.OData]System.Web.OData.EdmEntityObjectCollection edmEntityCollection, int32 totalRecordCount, bool totalRecordCountLimitExceeded, string pagingCookie, bool hasMoreRecords)
0x1feda  stloc.s  5
0x1fedc  ldnull
0x1fedd  stloc.s  6
0x1fedf  ldarg.3
0x1fee0  ldloc.s  4
0x1fee2  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationPropertyBinding::get_NavigationProperty()
0x1fee7  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x1feec  ldloca.s 6
0x1feee  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x1fef3  brfalse.s loc_1FF58
0x1fef5  ldloc.s  6
0x1fef7  castclass [System.Web.OData]System.Web.OData.EdmEntityObjectCollection
0x1fefc  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Web.OData]System.Web.OData.IEdmEntityObject>::get_Count()
0x1ff01  brtrue.s loc_1FF1A
0x1ff03  ldarg.3
0x1ff04  ldloc.s  4
0x1ff06  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationPropertyBinding::get_NavigationProperty()
0x1ff0b  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x1ff10  ldloc.s  5
0x1ff12  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TrySetPropertyValue(string, object)
0x1ff17  pop
0x1ff18  br.s     loc_1FF6D
0x1ff1a  ldloc.s  5
0x1ff1c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Web.OData]System.Web.OData.IEdmEntityObject>::GetEnumerator()
0x1ff21  stloc.s  7
0x1ff23  br.s     loc_1FF41
0x1ff25  ldloc.s  7
0x1ff27  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Web.OData]System.Web.OData.IEdmEntityObject>::get_Current()
0x1ff2c  castclass [System.Web.OData]System.Web.OData.EdmEntityObject
0x1ff31  stloc.s  8
0x1ff33  ldloc.s  6
0x1ff35  castclass Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection
0x1ff3a  ldloc.s  8
0x1ff3c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Web.OData]System.Web.OData.IEdmEntityObject>::Add(var<u1>)
0x1ff41  ldloc.s  7
0x1ff43  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1ff48  brtrue.s loc_1FF25
0x1ff4a  leave.s  loc_1FF6D
0x1ff4c  ldloc.s  7
0x1ff4e  brfalse.s loc_1FF57
0x1ff50  ldloc.s  7
0x1ff52  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ff57  endfinally
0x1ff58  ldarg.3
0x1ff59  ldloc.s  4
0x1ff5b  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationPropertyBinding::get_NavigationProperty()
0x1ff60  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x1ff65  ldloc.s  5
0x1ff67  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TrySetPropertyValue(string, object)
0x1ff6c  pop
0x1ff6d  ldloc.3
0x1ff6e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1ff73  brtrue   loc_1FE7A
0x1ff78  leave.s  loc_1FF84
0x1ff7a  ldloc.3
0x1ff7b  brfalse.s loc_1FF83
0x1ff7d  ldloc.3
0x1ff7e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ff83  endfinally
0x1ff84  ret
```
