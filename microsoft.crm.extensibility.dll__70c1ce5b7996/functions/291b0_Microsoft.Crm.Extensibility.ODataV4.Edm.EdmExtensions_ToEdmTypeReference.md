# Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::ToEdmTypeReference

- ea: `0x291b0`
- end: `0x2923f`
- name: `Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::ToEdmTypeReference`
- size: `143`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1fe0`
- `0x21a0`
- `0x3760`
- `0xf7d0`
- `0x10630`
- `0x13540`
- `0x1e600`
- `0x28320`
- `0x339d0`

## callees

- `0x291b0`

## pseudocode

```c

```

## disassembly

```asm
0x291b0  ldarg.0
0x291b1  ldnull
0x291b2  cgt.un
0x291b4  ldstr    aEdmtypeShouldN// "EdmType should not be null"
0x291b9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x291be  ldarg.0
0x291bf  callvirt instance valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeKind [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType::get_TypeKind()
0x291c4  stloc.0
0x291c5  ldloc.0
0x291c6  ldc.i4.1
0x291c7  sub
0x291c8  switch   loc_29227, loc_29200, loc_291F3, loc_291E7, loc_2920D, loc_2921A
0x291e5  br.s     loc_29234
0x291e7  ldarg.0
0x291e8  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionType
0x291ed  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionType)
0x291f2  ret
0x291f3  ldarg.0
0x291f4  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmComplexType
0x291f9  ldarg.1
0x291fa  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmComplexTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmComplexType, bool)
0x291ff  ret
0x29200  ldarg.0
0x29201  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType
0x29206  ldarg.1
0x29207  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType, bool)
0x2920c  ret
0x2920d  ldarg.0
0x2920e  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityReferenceType
0x29213  ldarg.1
0x29214  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityReferenceTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityReferenceType, bool)
0x29219  ret
0x2921a  ldarg.0
0x2921b  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEnumType
0x29220  ldarg.1
0x29221  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEnumTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEnumType, bool)
0x29226  ret
0x29227  ldarg.0
0x29228  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmPrimitiveType
0x2922d  ldarg.1
0x2922e  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmPrimitiveType, bool)
0x29233  ret
0x29234  ldstr    aEdmtypeNotSupp// "EdmType Not Supported"
0x29239  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2923e  throw
```
