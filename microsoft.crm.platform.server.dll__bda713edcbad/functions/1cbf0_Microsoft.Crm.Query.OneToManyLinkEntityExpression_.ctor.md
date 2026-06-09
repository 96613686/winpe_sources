# Microsoft.Crm.Query.OneToManyLinkEntityExpression::.ctor

- ea: `0x1cbf0`
- end: `0x1cc2e`
- name: `Microsoft.Crm.Query.OneToManyLinkEntityExpression::.ctor`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18b70`
- `0x19480`

## callees

- `0x18800`
- `0x1ccc0`

## string_xrefs

- `0x1cc05`: `linkFromEntityName`
- `0x1cc10`: `linkToEntityName`
- `0x1cc1b`: `linkFromAttributeName`

## pseudocode

```c

```

## disassembly

```asm
0x1cbf0  ldarg.0
0x1cbf1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1cbf6  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Query.OneToManyLinkEntityExpression::_parentEntityId
0x1cbfb  ldarg.0
0x1cbfc  ldarg.1
0x1cbfd  ldarg.s  4
0x1cbff  call     instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x1cc04  ldarg.1
0x1cc05  ldstr    aLinkfromentity// "linkFromEntityName"
0x1cc0a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1cc0f  ldarg.3
0x1cc10  ldstr    aLinktoentityna// "linkToEntityName"
0x1cc15  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1cc1a  ldarg.2
0x1cc1b  ldstr    aLinkfromattrib// "linkFromAttributeName"
0x1cc20  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1cc25  ldarg.0
0x1cc26  ldarg.3
0x1cc27  ldarg.2
0x1cc28  call     instance void Microsoft.Crm.Query.OneToManyLinkEntityExpression::InitMetadata(string linkToEntityName, string linkFromAttributeName)
0x1cc2d  ret
```
