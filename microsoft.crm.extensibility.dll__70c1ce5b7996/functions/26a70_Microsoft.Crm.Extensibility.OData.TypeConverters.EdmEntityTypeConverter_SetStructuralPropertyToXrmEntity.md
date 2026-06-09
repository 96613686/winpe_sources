# Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::SetStructuralPropertyToXrmEntity

- ea: `0x26a70`
- end: `0x26b68`
- name: `Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::SetStructuralPropertyToXrmEntity`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x26710`

## callees

- `0x133a0`
- `0x1f7e0`
- `0x1f800`
- `0x26a70`
- `0x26b70`
- `0x2bf50`

## string_xrefs

- `0x26a9e`: `Property {0} is not valid for write`

## pseudocode

```c

```

## disassembly

```asm
0x26a70  ldarg.1
0x26a71  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x26a76  ldarg.3
0x26a77  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::CheckIfPropertyIsOwnerEntityPrimaryKey(string crmEntityName, string propertyName)
0x26a7c  brfalse.s loc_26A8B
0x26a7e  ldarg.2
0x26a7f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x26a84  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x26a89  starg.s  3
0x26a8b  ldarg.1
0x26a8c  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x26a91  ldarg.3
0x26a92  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::CheckIfPropertyIsAvailableOnEntity(string crmEntityName, string crmAttributeName)
0x26a97  brtrue.s loc_26AB9
0x26a99  ldc.i4   0x190
0x26a9e  ldstr    aProperty0IsNot// "Property {0} is not valid for write"
0x26aa3  ldc.i4.1
0x26aa4  newarr   [mscorlib]System.Object
0x26aa9  dup
0x26aaa  ldc.i4.0
0x26aab  ldarg.s  4
0x26aad  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x26ab2  stelem.ref
0x26ab3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x26ab8  throw
0x26ab9  ldarg.1
0x26aba  ldarg.3
0x26abb  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x26ac0  brfalse.s loc_26ACB
0x26ac2  ldarg.s  4
0x26ac4  call     bool Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::ShouldUpdateInConflict(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty)
0x26ac9  brfalse.s loc_26AE6
0x26acb  ldarg.1
0x26acc  ldarg.3
0x26acd  ldarg.0
0x26ace  ldfld    class Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext Microsoft.Crm.Extensibility.OData.TypeConverters.EdmEntityTypeConverter::edmEntityConversionContext
0x26ad3  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.ODataV4.Converters.TypeConverters.EdmEntityConversionContext::get_EdmModel()
0x26ad8  ldarg.s  4
0x26ada  ldarg.s  5
0x26adc  call     object Microsoft.Crm.Extensibility.OData.EdmTypeConverter::ConvertToCrmAttributeValue(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty, object propertyValue)
0x26ae1  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x26ae6  ldarg.3
0x26ae7  ldarg.2
0x26ae8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x26aed  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x26af2  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x26af7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x26afc  brfalse.s loc_26B67
0x26afe  ldarg.s  5
0x26b00  brfalse.s loc_26B67
0x26b02  ldarg.s  5
0x26b04  unbox.any [mscorlib]System.Guid
0x26b09  stloc.0
0x26b0a  ldarg.1
0x26b0b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x26b10  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x26b15  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x26b1a  brfalse.s loc_26B60
0x26b1c  ldloc.0
0x26b1d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x26b22  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x26b27  brtrue.s loc_26B37
0x26b29  ldloc.0
0x26b2a  ldarg.1
0x26b2b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x26b30  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x26b35  br.s     loc_26B38
0x26b37  ldc.i4.1
0x26b38  ldstr    aUnmatchedEntit// "Unmatched Entity Id, Provided:{0}, in p"...
0x26b3d  ldc.i4.2
0x26b3e  newarr   [mscorlib]System.Object
0x26b43  dup
0x26b44  ldc.i4.0
0x26b45  ldloc.0
0x26b46  box      [mscorlib]System.Guid
0x26b4b  stelem.ref
0x26b4c  dup
0x26b4d  ldc.i4.1
0x26b4e  ldarg.1
0x26b4f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x26b54  box      [mscorlib]System.Guid
0x26b59  stelem.ref
0x26b5a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x26b5f  ret
0x26b60  ldarg.1
0x26b61  ldloc.0
0x26b62  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x26b67  ret
```
