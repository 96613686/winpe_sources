# Microsoft.Crm.Query.OneToManyLinkEntityExpression::.ctor_0

- ea: `0x1cc30`
- end: `0x1cc70`
- name: `Microsoft.Crm.Query.OneToManyLinkEntityExpression::.ctor_0`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x189d0`
- `0x1ccc0`

## string_xrefs

- `0x1cc47`: `linkFromEntityName`
- `0x1cc52`: `linkToEntityName`
- `0x1cc5d`: `linkFromAttributeName`

## pseudocode

```c

```

## disassembly

```asm
0x1cc30  ldarg.0
0x1cc31  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1cc36  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Query.OneToManyLinkEntityExpression::_parentEntityId
0x1cc3b  ldarg.0
0x1cc3c  ldarg.s  4
0x1cc3e  ldnull
0x1cc3f  ldarg.s  5
0x1cc41  call     instance void Microsoft.Crm.Query.EntityExpression::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase query, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache dynamicCache, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x1cc46  ldarg.1
0x1cc47  ldstr    aLinkfromentity// "linkFromEntityName"
0x1cc4c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1cc51  ldarg.3
0x1cc52  ldstr    aLinktoentityna// "linkToEntityName"
0x1cc57  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1cc5c  ldarg.2
0x1cc5d  ldstr    aLinkfromattrib// "linkFromAttributeName"
0x1cc62  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1cc67  ldarg.0
0x1cc68  ldarg.3
0x1cc69  ldarg.2
0x1cc6a  call     instance void Microsoft.Crm.Query.OneToManyLinkEntityExpression::InitMetadata(string linkToEntityName, string linkFromAttributeName)
0x1cc6f  ret
```
