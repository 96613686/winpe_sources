# Microsoft.Crm.Extensibility.OData.EdmUtilities::CreateNewEdmEntityObjectCollection

- ea: `0xf7d0`
- end: `0xf87a`
- name: `Microsoft.Crm.Extensibility.OData.EdmUtilities::CreateNewEdmEntityObjectCollection`
- size: `170`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x218d0`
- `0x22320`
- `0x227e0`
- `0x24fb0`
- `0x25e90`
- `0x26dc0`
- `0x28440`

## callees

- `0xf7d0`
- `0xfae0`
- `0x291b0`

## pseudocode

```c

```

## disassembly

```asm
0xf7d0  ldarg.0
0xf7d1  ldstr    aCrmbaseentity// "crmbaseentity"
0xf7d6  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf7db  brfalse.s loc_F7FD
0xf7dd  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache::get_Instance()
0xf7e2  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache::get_BaseEntityType()
0xf7e7  ldc.i4.1
0xf7e8  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::ToEdmTypeReference(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType edmType, bool isNullable)
0xf7ed  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionType::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0xf7f2  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionType)
0xf7f7  newobj   instance void [System.Web.OData]System.Web.OData.EdmEntityObjectCollection::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionTypeReference)
0xf7fc  ret
0xf7fd  ldarg.0
0xf7fe  ldstr    aCrmmodelbaseen// "crmmodelbaseentity"
0xf803  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf808  brfalse.s loc_F82A
0xf80a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache::get_Instance()
0xf80f  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache::get_ModelBaseEntityType()
0xf814  ldc.i4.1
0xf815  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::ToEdmTypeReference(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType edmType, bool isNullable)
0xf81a  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionType::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0xf81f  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionType)
0xf824  newobj   instance void [System.Web.OData]System.Web.OData.EdmEntityObjectCollection::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionTypeReference)
0xf829  ret
0xf82a  ldarg.0
0xf82b  ldarg.1
0xf82c  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntitySet Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntitySet(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0xf831  stloc.0
0xf832  ldloc.0
0xf833  brfalse.s loc_F845
0xf835  ldloc.0
0xf836  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource::get_Type()
0xf83b  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionType
0xf840  ldnull
0xf841  cgt.un
0xf843  br.s     loc_F846
0xf845  ldc.i4.0
0xf846  ldstr    aEdmentitysetTy// "edmEntitySet.Type ({0}) should be IEdmE"...
0xf84b  ldc.i4.1
0xf84c  newarr   [mscorlib]System.Object
0xf851  dup
0xf852  ldc.i4.0
0xf853  ldloc.0
0xf854  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource::get_Type()
0xf859  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xf85e  stelem.ref
0xf85f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0xf864  ldloc.0
0xf865  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationSource::get_Type()
0xf86a  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionType
0xf86f  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionType)
0xf874  newobj   instance void [System.Web.OData]System.Web.OData.EdmEntityObjectCollection::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionTypeReference)
0xf879  ret
```
