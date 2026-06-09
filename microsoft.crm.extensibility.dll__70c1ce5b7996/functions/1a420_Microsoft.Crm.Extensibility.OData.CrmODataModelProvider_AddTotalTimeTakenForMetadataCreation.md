# Microsoft.Crm.Extensibility.OData.CrmODataModelProvider::AddTotalTimeTakenForMetadataCreation

- ea: `0x1a420`
- end: `0x1a474`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataModelProvider::AddTotalTimeTakenForMetadataCreation`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1a480`

## string_xrefs

- `0x1a420`: `OData.Community.Display.V1`

## pseudocode

```c

```

## disassembly

```asm
0x1a420  ldstr    aOdataCommunity_1// "OData.Community.Display.V1"
0x1a425  ldstr    aModelgeneratio// "ModelGenerationTime"
0x1a42a  ldstr    aOrgOdataCoreV1// "Org.OData.Core.V1"
0x1a42f  ldstr    aTag// "Tag"
0x1a434  ldc.i4.s 0xD
0x1a436  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinition::.ctor(string, string, valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind)
0x1a43b  ldc.i4.0
0x1a43c  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeDefinitionReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeDefinition, bool)
0x1a441  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm::.ctor(string, string, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x1a446  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmTerm [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EdmAnnotationProvider::get_CoreDescriptionTerm()
0x1a44b  ldstr    a01_4// "{0} {1}"
0x1a450  ldarga.s 1
0x1a452  call     instance string [mscorlib]System.Double::ToString()
0x1a457  ldstr    aSeconds// "seconds"
0x1a45c  call     string [mscorlib]System.String::Format(string, object, object)
0x1a461  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmStringConstant::.ctor(string)
0x1a466  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.EdmVocabularyAnnotation::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotatable, class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmTerm, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmExpression)
0x1a46b  stloc.0
0x1a46c  ldarg.0
0x1a46d  ldloc.0
0x1a46e  callvirt instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmModel::AddVocabularyAnnotation(class [Microsoft.OData.Edm]Microsoft.OData.Edm.Vocabularies.IEdmVocabularyAnnotation)
0x1a473  ret
```
