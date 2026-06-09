# Microsoft.Crm.Metadata.EdmAnnotationProvider::IntializeMaps

- ea: `0x616a0`
- end: `0x619a8`
- name: `Microsoft.Crm.Metadata.EdmAnnotationProvider::IntializeMaps`
- size: `776`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x61d70`

## callees

- `0x61ab0`
- `0x61ad0`
- `0x61af0`
- `0x61b10`
- `0x61b30`
- `0x61b50`
- `0x61b70`
- `0x61b90`
- `0x61bb0`
- `0x61bd0`
- `0x61bf0`
- `0x61c10`
- `0x61c30`
- `0x61c50`
- `0x61c70`
- `0x61c90`
- `0x61cb0`
- `0x61cd0`
- `0x61cf0`
- `0xac9b0`
- `0xaca00`

## string_xrefs

- `0x616c7`: `Computed`
- `0x6192d`: `application/json; odata.metadata=minimal; odata.streaming=true`
- `0x61935`: `application/json; odata.metadata=minimal; odata.streaming=false`
- `0x6193d`: `application/json; odata.metadata=minimal`
- `0x61945`: `application/json; odata.metadata=full; odata.streaming=true`
- `0x6194d`: `application/json; odata.metadata=full; odata.streaming=false`
- `0x61955`: `application/json; odata.metadata=full`
- `0x6195d`: `application/json; odata.metadata=none; odata.streaming=true`
- `0x61965`: `application/json; odata.metadata=none; odata.streaming=false`
- `0x6196d`: `application/json; odata.metadata=none`
- `0x61976`: `application/json; odata.streaming=true`
- `0x6197f`: `application/json; odata.streaming=false`
- `0x61988`: `application/json`
- `0x61991`: `application/xml`

## pseudocode

```c

```

## disassembly

```asm
0x616a0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::.ctor()
0x616a5  dup
0x616a6  ldstr    aDescription_0// "Description"
0x616ab  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CoreDescriptionTerm()
0x616b0  ldnull
0x616b1  ldftn    class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmVocabularyAnnotation Microsoft.Crm.Metadata.EdmAnnotationProvider::CreateAnnotationForMetadataProperty(string propertyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotatable target, object metadata, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm term)
0x616b7  newobj   instance void CreateAnnotationDelegate::.ctor(object object, native int method)
0x616bc  call     T0x2B0000B1
0x616c1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x616c6  dup
0x616c7  ldstr    aComputed// "Computed"
0x616cc  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CoreComputedTerm()
0x616d1  ldnull
0x616d2  ldftn    class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmVocabularyAnnotation Microsoft.Crm.Metadata.EdmAnnotationProvider::CreateComputedAnnotationForAttributeProperty(string propertyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotatable target, object metadata, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm term)
0x616d8  newobj   instance void CreateAnnotationDelegate::.ctor(object object, native int method)
0x616dd  call     T0x2B0000B1
0x616e2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x616e7  dup
0x616e8  ldstr    aPermissions// "Permissions"
0x616ed  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CorePermissionsTerm()
0x616f2  ldnull
0x616f3  ldftn    class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmVocabularyAnnotation Microsoft.Crm.Metadata.EdmAnnotationProvider::CreatePermissionAnnotationForAttributeProperty(string propertyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotatable target, object metadata, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm term)
0x616f9  newobj   instance void CreateAnnotationDelegate::.ctor(object object, native int method)
0x616fe  call     T0x2B0000B1
0x61703  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x61708  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>> Microsoft.Crm.Metadata.EdmAnnotationProvider::_edmAttibuteAnnotationMap
0x6170d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::.ctor()
0x61712  dup
0x61713  ldstr    aDescription_0// "Description"
0x61718  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CoreDescriptionTerm()
0x6171d  ldnull
0x6171e  ldftn    class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmVocabularyAnnotation Microsoft.Crm.Metadata.EdmAnnotationProvider::CreateAnnotationForMetadataProperty(string propertyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotatable target, object metadata, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm term)
0x61724  newobj   instance void CreateAnnotationDelegate::.ctor(object object, native int method)
0x61729  call     T0x2B0000B1
0x6172e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x61733  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>> Microsoft.Crm.Metadata.EdmAnnotationProvider::_edmEntityAnnotationMap
0x61738  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::.ctor()
0x6173d  dup
0x6173e  ldstr    aIndexablebykey// "IndexableByKey"
0x61743  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesIndexableByKeyTerm()
0x61748  ldc.i4.1
0x61749  box      [mscorlib]System.Boolean
0x6174e  call     T0x2B0000B1
0x61753  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x61758  dup
0x61759  ldstr    aSkipsupported// "SkipSupported"
0x6175e  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesSkipSupportedTerm()
0x61763  ldc.i4.0
0x61764  box      [mscorlib]System.Boolean
0x61769  call     T0x2B0000B1
0x6176e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x61773  dup
0x61774  ldstr    aSearchrestrict// "SearchRestrictions"
0x61779  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesSearchRestrictionsTerm()
0x6177e  ldnull
0x6177f  ldftn    class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmVocabularyAnnotation Microsoft.Crm.Metadata.EdmAnnotationProvider::CreateAnnotationForSearchRestriction(string propertyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotatable target, object metadata, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm term)
0x61785  newobj   instance void CreateAnnotationDelegate::.ctor(object object, native int method)
0x6178a  call     T0x2B0000B1
0x6178f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x61794  dup
0x61795  ldstr    aCountrestricti// "CountRestrictions"
0x6179a  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesCountRestrictionsTerm()
0x6179f  ldnull
0x617a0  ldftn    class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmVocabularyAnnotation Microsoft.Crm.Metadata.EdmAnnotationProvider::CreateAnnotationForCountRestriction(string propertyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotatable target, object metadata, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm term)
0x617a6  newobj   instance void CreateAnnotationDelegate::.ctor(object object, native int method)
0x617ab  call     T0x2B0000B1
0x617b0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x617b5  dup
0x617b6  ldstr    aNavigationrest// "NavigationRestrictions"
0x617bb  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesNavigationRestrictionsTerm()
0x617c0  ldnull
0x617c1  ldftn    class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmVocabularyAnnotation Microsoft.Crm.Metadata.EdmAnnotationProvider::CreateAnnotationForNavigationRestriction(string propertyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotatable target, object metadata, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm term)
0x617c7  newobj   instance void CreateAnnotationDelegate::.ctor(object object, native int method)
0x617cc  call     T0x2B0000B1
0x617d1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x617d6  dup
0x617d7  ldstr    aChangetracking_1// "ChangeTracking"
0x617dc  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesChangeTrackingTerm()
0x617e1  ldnull
0x617e2  ldftn    class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmVocabularyAnnotation Microsoft.Crm.Metadata.EdmAnnotationProvider::CreateAnnotationForChangeTracking(string propertyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotatable target, object metadata, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm term)
0x617e8  newobj   instance void CreateAnnotationDelegate::.ctor(object object, native int method)
0x617ed  call     T0x2B0000B1
0x617f2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x617f7  dup
0x617f8  ldstr    aOptimisticconc// "OptimisticConcurrency"
0x617fd  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CoreOptimisticConcurrencyTerm()
0x61802  ldnull
0x61803  ldftn    class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmVocabularyAnnotation Microsoft.Crm.Metadata.EdmAnnotationProvider::CreateAnnotationForOptimisticConcurrency(string propertyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotatable target, object metadata, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm term, valuetype Microsoft.Crm.Metadata.ModelVersion modelVersion)
0x61809  newobj   instance void CreateAnnotationForOptimisticConcurrencyDelegate::.ctor(object object, native int method)
0x6180e  call     T0x2B0000B1
0x61813  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x61818  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>> Microsoft.Crm.Metadata.EdmAnnotationProvider::_edmEntitySetAnnotationMap
0x6181d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::.ctor()
0x61822  stloc.0
0x61823  ldloc.0
0x61824  ldstr    aConformancelev// "ConformanceLevel"
0x61829  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesConformanceLevelTerm()
0x6182e  ldnull
0x6182f  ldftn    class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmVocabularyAnnotation Microsoft.Crm.Metadata.EdmAnnotationProvider::CreateAnnotationForConformanceLevel(string propertyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotatable target, object metadata, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm term)
0x61835  newobj   instance void CreateAnnotationDelegate::.ctor(object object, native int method)
0x6183a  call     T0x2B0000B1
0x6183f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x61844  ldloc.0
0x61845  ldstr    aFilterfunction// "FilterFunctions"
0x6184a  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesFilterFunctionsTerm()
0x6184f  ldc.i4.3
0x61850  newarr   [mscorlib]System.String
0x61855  dup
0x61856  ldc.i4.0
0x61857  ldstr    aContains// "contains"
0x6185c  stelem.ref
0x6185d  dup
0x6185e  ldc.i4.1
0x6185f  ldstr    aEndswith// "endswith"
0x61864  stelem.ref
0x61865  dup
0x61866  ldc.i4.2
0x61867  ldstr    aStartswith// "startswith"
0x6186c  stelem.ref
0x6186d  call     T0x2B0000B1
0x61872  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x61877  ldloc.0
0x61878  ldstr    aDereferenceabl// "DereferenceableID"
0x6187d  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CoreDereferenceableIdsTerm()
0x61882  ldc.i4.1
0x61883  box      [mscorlib]System.Boolean
0x61888  call     T0x2B0000B1
0x6188d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x61892  ldloc.0
0x61893  ldstr    aConventionalid// "ConventionalID"
0x61898  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CoreConventionalIdsTerm()
0x6189d  ldc.i4.1
0x6189e  box      [mscorlib]System.Boolean
0x618a3  call     T0x2B0000B1
0x618a8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x618ad  ldloc.0
0x618ae  ldstr    aBatchsupported// "BatchSupported"
0x618b3  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesBatchSupportedTerm()
0x618b8  ldc.i4.1
0x618b9  box      [mscorlib]System.Boolean
0x618be  call     T0x2B0000B1
0x618c3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x618c8  ldloc.0
0x618c9  ldstr    aAsynchronousre// "AsynchronousRequestsSupported"
0x618ce  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesAsynchronousRequestsSupportedTerm()
0x618d3  ldc.i4.0
0x618d4  box      [mscorlib]System.Boolean
0x618d9  call     T0x2B0000B1
0x618de  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x618e3  ldloc.0
0x618e4  ldstr    aBatchcontinueo// "BatchContinueOnErrorSupported"
0x618e9  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesBatchContinueOnErrorSupportedTerm()
0x618ee  ldc.i4.1
0x618ef  box      [mscorlib]System.Boolean
0x618f4  call     T0x2B0000B1
0x618f9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x618fe  ldloc.0
0x618ff  ldstr    aCrossjoinsuppo// "CrossJoinSupported"
0x61904  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesCrossJoinSupportedTerm()
0x61909  ldc.i4.0
0x6190a  box      [mscorlib]System.Boolean
0x6190f  call     T0x2B0000B1
0x61914  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x61919  ldloc.0
0x6191a  ldstr    aSupportedforma// "SupportedFormats"
0x6191f  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CapabilitiesSupportedFormatsTerm()
0x61924  ldc.i4.s 0xD
0x61926  newarr   [mscorlib]System.String
0x6192b  dup
0x6192c  ldc.i4.0
0x6192d  ldstr    aApplicationJso// "application/json; odata.metadata=minima"...
0x61932  stelem.ref
0x61933  dup
0x61934  ldc.i4.1
0x61935  ldstr    aApplicationJso_0// "application/json; odata.metadata=minima"...
0x6193a  stelem.ref
0x6193b  dup
0x6193c  ldc.i4.2
0x6193d  ldstr    aApplicationJso_1// "application/json; odata.metadata=minima"...
0x61942  stelem.ref
0x61943  dup
0x61944  ldc.i4.3
0x61945  ldstr    aApplicationJso_2// "application/json; odata.metadata=full; "...
0x6194a  stelem.ref
0x6194b  dup
0x6194c  ldc.i4.4
0x6194d  ldstr    aApplicationJso_3// "application/json; odata.metadata=full; "...
0x61952  stelem.ref
0x61953  dup
0x61954  ldc.i4.5
0x61955  ldstr    aApplicationJso_4// "application/json; odata.metadata=full"
0x6195a  stelem.ref
0x6195b  dup
0x6195c  ldc.i4.6
0x6195d  ldstr    aApplicationJso_5// "application/json; odata.metadata=none; "...
0x61962  stelem.ref
0x61963  dup
0x61964  ldc.i4.7
0x61965  ldstr    aApplicationJso_6// "application/json; odata.metadata=none; "...
0x6196a  stelem.ref
0x6196b  dup
0x6196c  ldc.i4.8
0x6196d  ldstr    aApplicationJso_7// "application/json; odata.metadata=none"
0x61972  stelem.ref
0x61973  dup
0x61974  ldc.i4.s 9
0x61976  ldstr    aApplicationJso_8// "application/json; odata.streaming=true"
0x6197b  stelem.ref
0x6197c  dup
0x6197d  ldc.i4.s 0xA
0x6197f  ldstr    aApplicationJso_9// "application/json; odata.streaming=false"
0x61984  stelem.ref
0x61985  dup
0x61986  ldc.i4.s 0xB
0x61988  ldstr    aApplicationJso_10// "application/json"
0x6198d  stelem.ref
0x6198e  dup
0x6198f  ldc.i4.s 0xC
0x61991  ldstr    aApplicationXml// "application/xml"
0x61996  stelem.ref
0x61997  call     T0x2B0000B1
0x6199c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>>::Add(var<u1>, !!T0)
0x619a1  ldloc.0
0x619a2  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, object>> Microsoft.Crm.Metadata.EdmAnnotationProvider::_edmEntityContainerAnnotationMap
0x619a7  ret
```
