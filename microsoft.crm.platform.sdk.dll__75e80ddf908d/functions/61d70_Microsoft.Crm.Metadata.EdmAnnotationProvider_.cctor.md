# Microsoft.Crm.Metadata.EdmAnnotationProvider::.cctor

- ea: `0x61d70`
- end: `0x6217c`
- name: `Microsoft.Crm.Metadata.EdmAnnotationProvider::.cctor`
- size: `1036`
- prototype: ``
- caller_count: `0`
- callee_count: `41`
- tags: `broker_com_uri`

## callees

- `0x5f850`
- `0x5fae0`
- `0x616a0`
- `0x619b0`
- `0x619c0`
- `0x619d0`
- `0x619e0`
- `0x619f0`
- `0x61a00`
- `0x61a10`
- `0x61a20`
- `0x61a30`
- `0x61a40`
- `0x61a50`
- `0x61a60`
- `0x61a70`
- `0x61a80`
- `0x61a90`
- `0x61aa0`
- `0x61ac0`
- `0x61ae0`
- `0x61b00`
- `0x61b20`
- `0x61b40`
- `0x61b60`
- `0x61b80`
- `0x61ba0`
- `0x61bc0`
- `0x61be0`
- `0x61c00`
- `0x61c20`
- `0x61c40`
- `0x61c60`
- `0x61c80`
- `0x61ca0`
- `0x61cc0`
- `0x61ce0`
- `0x61d00`
- `0x61d20`
- `0x61d40`
- `0x61d60`

## string_xrefs

- `0x61f1f`: `Computed`
- `0x62125`: `OData.Community.Display.V1`

## pseudocode

```c

```

## disassembly

```asm
0x61d70  ldstr    aOrgOdataCoreV1// "Org.OData.Core.V1"
0x61d75  ldstr    aTag// "Tag"
0x61d7a  ldc.i4.2
0x61d7b  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinition::.ctor(string, string, valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind)
0x61d80  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CoreTagType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinition value)
0x61d85  ldstr    aOrgOdataCoreV1// "Org.OData.Core.V1"
0x61d8a  ldtoken  PermissionType
0x61d8f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x61d94  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEnumType Microsoft.Crm.Metadata.EdmEnumProvider::GetEdmEnumType(string targetNamespace, class [mscorlib]System.Type type)
0x61d99  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CorePermissionType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEnumType value)
0x61d9e  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x61da3  ldtoken  NavigationType
0x61da8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x61dad  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEnumType Microsoft.Crm.Metadata.EdmEnumProvider::GetEdmEnumType(string targetNamespace, class [mscorlib]System.Type type)
0x61db2  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesNavigationType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEnumType value)
0x61db7  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x61dbc  ldtoken  ConformanceLevelType
0x61dc1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x61dc6  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEnumType Microsoft.Crm.Metadata.EdmEnumProvider::GetEdmEnumType(string targetNamespace, class [mscorlib]System.Type type)
0x61dcb  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesConformanceLevelType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEnumType value)
0x61dd0  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x61dd5  ldstr    aChangetracking_1// "ChangeTracking"
0x61dda  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference>::.ctor()
0x61ddf  dup
0x61de0  ldstr    aSupported// "Supported"
0x61de5  ldsfld   class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel::Instance
0x61dea  ldc.i4.2
0x61deb  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmPrimitiveType [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel::GetPrimitiveType(valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind)
0x61df0  ldc.i4.1
0x61df1  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmPrimitiveType, bool)
0x61df6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference>::Add(var<u1>, !!T0)
0x61dfb  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexType Microsoft.Crm.Metadata.EdmComplexTypeProvider::GetEdmComplexType(string namespaceName, string typeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference> properties)
0x61e00  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesChangeTrackingType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexType value)
0x61e05  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x61e0a  ldstr    aCountrestricti// "CountRestrictions"
0x61e0f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference>::.ctor()
0x61e14  dup
0x61e15  ldstr    aCountable// "Countable"
0x61e1a  ldsfld   class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel::Instance
0x61e1f  ldc.i4.2
0x61e20  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmPrimitiveType [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel::GetPrimitiveType(valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind)
0x61e25  ldc.i4.1
0x61e26  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmPrimitiveType, bool)
0x61e2b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference>::Add(var<u1>, !!T0)
0x61e30  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexType Microsoft.Crm.Metadata.EdmComplexTypeProvider::GetEdmComplexType(string namespaceName, string typeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference> properties)
0x61e35  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesCountRestrictionsType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexType value)
0x61e3a  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x61e3f  ldstr    aSearchrestrict// "SearchRestrictions"
0x61e44  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference>::.ctor()
0x61e49  dup
0x61e4a  ldstr    aSearchable// "Searchable"
0x61e4f  ldsfld   class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel::Instance
0x61e54  ldc.i4.2
0x61e55  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmPrimitiveType [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel::GetPrimitiveType(valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind)
0x61e5a  ldc.i4.1
0x61e5b  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmPrimitiveType, bool)
0x61e60  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference>::Add(var<u1>, !!T0)
0x61e65  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexType Microsoft.Crm.Metadata.EdmComplexTypeProvider::GetEdmComplexType(string namespaceName, string typeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference> properties)
0x61e6a  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesSearchRestrictionsType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexType value)
0x61e6f  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x61e74  ldstr    aCountrestricti// "CountRestrictions"
0x61e79  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference>::.ctor()
0x61e7e  dup
0x61e7f  ldstr    aNavigability// "Navigability"
0x61e84  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEnumType Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesNavigationType()
0x61e89  ldc.i4.0
0x61e8a  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEnumTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEnumType, bool)
0x61e8f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference>::Add(var<u1>, !!T0)
0x61e94  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexType Microsoft.Crm.Metadata.EdmComplexTypeProvider::GetEdmComplexType(string namespaceName, string typeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference> properties)
0x61e99  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesNavigationRestrictionsType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexType value)
0x61e9e  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x61ea3  ldstr    aIndexablebykey// "IndexableByKey"
0x61ea8  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinition Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CoreTagType()
0x61ead  ldc.i4.0
0x61eae  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinitionReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeDefinition, bool)
0x61eb3  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x61eb8  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesIndexableByKeyTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x61ebd  ldstr    aOrgOdataCoreV1// "Org.OData.Core.V1"
0x61ec2  ldstr    aPermissions// "Permissions"
0x61ec7  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEnumType Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CorePermissionType()
0x61ecc  ldc.i4.0
0x61ecd  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEnumTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEnumType, bool)
0x61ed2  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x61ed7  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CorePermissionsTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x61edc  ldstr    aOrgOdataCoreV1// "Org.OData.Core.V1"
0x61ee1  ldstr    aDereferenceabl_0// "DereferenceableIDs"
0x61ee6  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinition Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CoreTagType()
0x61eeb  ldc.i4.0
0x61eec  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinitionReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeDefinition, bool)
0x61ef1  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x61ef6  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CoreDereferenceableIdsTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x61efb  ldstr    aOrgOdataCoreV1// "Org.OData.Core.V1"
0x61f00  ldstr    aConventionalid_0// "ConventionalIDs"
0x61f05  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinition Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CoreTagType()
0x61f0a  ldc.i4.0
0x61f0b  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinitionReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeDefinition, bool)
0x61f10  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x61f15  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CoreConventionalIdsTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x61f1a  ldstr    aOrgOdataCoreV1// "Org.OData.Core.V1"
0x61f1f  ldstr    aComputed// "Computed"
0x61f24  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinition Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CoreTagType()
0x61f29  ldc.i4.0
0x61f2a  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinitionReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeDefinition, bool)
0x61f2f  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x61f34  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CoreComputedTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x61f39  ldstr    aOrgOdataCoreV1// "Org.OData.Core.V1"
0x61f3e  ldstr    aDescription_0// "Description"
0x61f43  ldsfld   class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel::Instance
0x61f48  ldc.i4.s 0xD
0x61f4a  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmPrimitiveType [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel::GetPrimitiveType(valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind)
0x61f4f  ldc.i4.1
0x61f50  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmPrimitiveType, bool)
0x61f55  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x61f5a  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CoreDescriptionTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x61f5f  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x61f64  ldstr    aOptimisticconc// "OptimisticConcurrency"
0x61f69  ldsfld   class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel::Instance
0x61f6e  ldc.i4.s 0xD
0x61f70  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmPrimitiveType [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel::GetPrimitiveType(valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind)
0x61f75  ldc.i4.1
0x61f76  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmPrimitiveType, bool)
0x61f7b  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionType::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x61f80  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionType)
0x61f85  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x61f8a  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CoreOptimisticConcurrencyTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x61f8f  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x61f94  ldstr    aCountrestricti// "CountRestrictions"
0x61f99  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexType Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesCountRestrictionsType()
0x61f9e  ldc.i4.0
0x61f9f  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmComplexType, bool)
0x61fa4  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x61fa9  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesCountRestrictionsTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x61fae  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x61fb3  ldstr    aNavigationrest// "NavigationRestrictions"
0x61fb8  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexType Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesNavigationRestrictionsType()
0x61fbd  ldc.i4.0
0x61fbe  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmComplexType, bool)
0x61fc3  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x61fc8  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesNavigationRestrictionsTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x61fcd  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x61fd2  ldstr    aSearchrestrict// "SearchRestrictions"
0x61fd7  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexType Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesSearchRestrictionsType()
0x61fdc  ldc.i4.0
0x61fdd  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmComplexType, bool)
0x61fe2  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x61fe7  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesSearchRestrictionsTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x61fec  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x61ff1  ldstr    aChangetracking_1// "ChangeTracking"
0x61ff6  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexType Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesChangeTrackingType()
0x61ffb  ldc.i4.0
0x61ffc  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmComplexType, bool)
0x62001  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x62006  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesChangeTrackingTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x6200b  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x62010  ldstr    aConformancelev// "ConformanceLevel"
0x62015  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEnumType Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesConformanceLevelType()
0x6201a  ldc.i4.0
0x6201b  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEnumTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEnumType, bool)
0x62020  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x62025  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesConformanceLevelTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x6202a  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x6202f  ldstr    aFilterfunction// "FilterFunctions"
0x62034  ldsfld   class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel::Instance
0x62039  ldc.i4.s 0xD
0x6203b  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmPrimitiveType [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel::GetPrimitiveType(valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind)
0x62040  ldc.i4.1
0x62041  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmPrimitiveType, bool)
0x62046  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionType::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x6204b  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionType)
0x62050  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x62055  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesFilterFunctionsTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x6205a  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x6205f  ldstr    aBatchsupported// "BatchSupported"
0x62064  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinition Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CoreTagType()
0x62069  ldc.i4.0
0x6206a  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinitionReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeDefinition, bool)
0x6206f  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x62074  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesBatchSupportedTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x62079  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x6207e  ldstr    aSupportedforma// "SupportedFormats"
0x62083  ldsfld   class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel::Instance
0x62088  ldc.i4.s 0xD
0x6208a  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmPrimitiveType [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCoreModel::GetPrimitiveType(valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind)
0x6208f  ldc.i4.1
0x62090  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmPrimitiveType, bool)
0x62095  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionType::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x6209a  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionType)
0x6209f  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x620a4  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesSupportedFormatsTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x620a9  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x620ae  ldstr    aSkipsupported// "SkipSupported"
0x620b3  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinition Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CoreTagType()
0x620b8  ldc.i4.0
0x620b9  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinitionReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeDefinition, bool)
0x620be  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x620c3  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesSkipSupportedTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x620c8  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x620cd  ldstr    aAsynchronousre// "AsynchronousRequestsSupported"
0x620d2  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinition Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CoreTagType()
0x620d7  ldc.i4.0
0x620d8  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinitionReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeDefinition, bool)
0x620dd  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x620e2  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesAsynchronousRequestsSupportedTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x620e7  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x620ec  ldstr    aBatchcontinueo// "BatchContinueOnErrorSupported"
0x620f1  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinition Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CoreTagType()
0x620f6  ldc.i4.1
0x620f7  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinitionReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeDefinition, bool)
0x620fc  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x62101  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesBatchContinueOnErrorSupportedTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x62106  ldstr    aOrgOdataCapabi// "Org.OData.Capabilities.V1"
0x6210b  ldstr    aCrossjoinsuppo// "CrossJoinSupported"
0x62110  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinition Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CoreTagType()
0x62115  ldc.i4.0
0x62116  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinitionReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeDefinition, bool)
0x6211b  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x62120  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CapabilitiesCrossJoinSupportedTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x62125  ldstr    aOdataCommunity// "OData.Community.Display.V1"
0x6212a  ldstr    aFormattedvalue// "FormattedValue"
0x6212f  ldc.i4.s 0xD
0x62131  ldstr    aPropertyvalue// "PropertyValue"
0x62136  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind, string)
0x6213b  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CrmFormattedValueTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x62140  ldstr    aMicrosoftDynam// "Microsoft.Dynamics.CRM"
0x62145  ldstr    aLookuplogicaln// "lookuplogicalname"
0x6214a  ldc.i4.s 0xD
0x6214c  ldstr    aPropertyvalue// "PropertyValue"
0x62151  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind, string)
0x62156  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CrmLookupEntityLogicalNameTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x6215b  ldstr    aMicrosoftDynam// "Microsoft.Dynamics.CRM"
0x62160  ldstr    aAssociatednavi// "associatednavigationproperty"
0x62165  ldc.i4.s 0xD
0x62167  ldstr    aPropertyvalue// "PropertyValue"
0x6216c  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind, string)
0x62171  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::set_CrmAssociatedNavigationPropertyNameTerm(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm value)
0x62176  call     void Microsoft.Crm.Metadata.EdmAnnotationProvider::IntializeMaps()
0x6217b  ret
```
