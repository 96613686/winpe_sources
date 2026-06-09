# Microsoft.Crm.Extensibility.EntityValidator::ValidateOrSetEntityId

- ea: `0x4b30`
- end: `0x4d59`
- name: `Microsoft.Crm.Extensibility.EntityValidator::ValidateOrSetEntityId`
- size: `553`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4920`

## callees

- `0x1360`
- `0x1370`
- `0x1490`
- `0x41b0`
- `0x41c0`
- `0x4280`
- `0x4920`
- `0x4b30`
- `0x4d60`
- `0x4e30`
- `0x4e50`

## string_xrefs

- `0x4c54`: `Entity Id must be specified for Update`

## pseudocode

```c

```

## disassembly

```asm
0x4b30  ldarg.1
0x4b31  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x4b36  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4b3b  brfalse.s loc_4B59
0x4b3d  ldarg.0
0x4b3e  ldstr    aRequiredMember_0// "Required member 'LogicalName' missing f"...
0x4b43  ldarg.2
0x4b44  ldstr    asc_372BC// "'"
0x4b49  call     string [mscorlib]System.String::Concat(string, string, string)
0x4b4e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x4b53  call     instance class [mscorlib]System.Exception Microsoft.Crm.Extensibility.EntityValidator::CreateExceptionWithValidationStack(class [mscorlib]System.Exception ex)
0x4b58  throw
0x4b59  ldarg.0
0x4b5a  ldfld    class Microsoft.Crm.Extensibility.EntityKeyProcessor Microsoft.Crm.Extensibility.EntityValidator::_entityKeyProcessor
0x4b5f  brfalse.s loc_4B6D
0x4b61  ldarg.0
0x4b62  ldfld    class Microsoft.Crm.Extensibility.EntityKeyProcessor Microsoft.Crm.Extensibility.EntityValidator::_entityKeyProcessor
0x4b67  ldarg.1
0x4b68  callvirt instance void Microsoft.Crm.Extensibility.EntityKeyProcessor::ResolveAlternateKey(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x4b6d  ldarg.3
0x4b6e  ldarg.1
0x4b6f  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState Microsoft.Crm.Extensibility.EntityActionResolver::GetEntityStateOrDefault(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity)
0x4b74  stloc.0
0x4b75  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4b7a  stloc.1
0x4b7b  ldarg.s  4
0x4b7d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4b82  ldarg.1
0x4b83  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x4b88  ldc.i4.1
0x4b89  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x4b8e  stloc.2
0x4b8f  ldloc.2
0x4b90  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x4b95  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x4b9a  stloc.3
0x4b9b  ldarg.1
0x4b9c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x4ba1  ldloc.3
0x4ba2  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x4ba7  brfalse.s loc_4BD8
0x4ba9  ldarg.1
0x4baa  ldloc.3
0x4bab  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x4bb0  isinst   [mscorlib]System.Guid
0x4bb5  brfalse.s loc_4BC6
0x4bb7  ldarg.1
0x4bb8  ldloc.3
0x4bb9  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x4bbe  unbox.any [mscorlib]System.Guid
0x4bc3  stloc.1
0x4bc4  br.s     loc_4BD8
0x4bc6  ldarg.0
0x4bc7  ldstr    aInvalidTypeFor// "Invalid type for entity id value"
0x4bcc  ldarg.2
0x4bcd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x4bd2  call     instance class [mscorlib]System.Exception Microsoft.Crm.Extensibility.EntityValidator::CreateExceptionWithValidationStack(class [mscorlib]System.Exception ex)
0x4bd7  throw
0x4bd8  ldarg.1
0x4bd9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x4bde  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4be3  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4be8  brfalse.s loc_4C17
0x4bea  ldloc.1
0x4beb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4bf0  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4bf5  brfalse.s loc_4C17
0x4bf7  ldarg.1
0x4bf8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x4bfd  ldloc.1
0x4bfe  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4c03  brfalse.s loc_4C3D
0x4c05  ldarg.0
0x4c06  ldstr    aEntityIdMustBe// "Entity Id must be the same as the value"...
0x4c0b  ldarg.2
0x4c0c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x4c11  call     instance class [mscorlib]System.Exception Microsoft.Crm.Extensibility.EntityValidator::CreateExceptionWithValidationStack(class [mscorlib]System.Exception ex)
0x4c16  throw
0x4c17  ldarg.1
0x4c18  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x4c1d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4c22  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4c27  brfalse.s loc_4C3D
0x4c29  ldloc.1
0x4c2a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4c2f  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4c34  brfalse.s loc_4C3D
0x4c36  ldarg.1
0x4c37  ldloc.1
0x4c38  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x4c3d  ldarg.1
0x4c3e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x4c43  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4c48  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4c4d  brfalse.s loc_4C74
0x4c4f  ldloc.0
0x4c50  ldc.i4.2
0x4c51  bne.un.s loc_4C65
0x4c53  ldarg.0
0x4c54  ldstr    aEntityIdMustBe_0// "Entity Id must be specified for Update"
0x4c59  ldarg.2
0x4c5a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x4c5f  call     instance class [mscorlib]System.Exception Microsoft.Crm.Extensibility.EntityValidator::CreateExceptionWithValidationStack(class [mscorlib]System.Exception ex)
0x4c64  throw
0x4c65  ldloc.0
0x4c66  ldc.i4.1
0x4c67  bne.un.s loc_4C74
0x4c69  ldarg.1
0x4c6a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x4c6f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x4c74  ldarg.3
0x4c75  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState Microsoft.Crm.Extensibility.EntityActionResolver::get_DefaultState()
0x4c7a  ldc.i4.2
0x4c7b  beq.s    loc_4C89
0x4c7d  ldarg.3
0x4c7e  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState Microsoft.Crm.Extensibility.EntityActionResolver::get_DefaultState()
0x4c83  ldc.i4.1
0x4c84  bne.un   loc_4D58
0x4c89  ldarg.1
0x4c8a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RelatedEntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_RelatedEntities()
0x4c8f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::GetEnumerator()
0x4c94  stloc.s  4
0x4c96  br       loc_4D3E
0x4c9b  ldloc.s  4
0x4c9d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>>::get_Current()
0x4ca2  stloc.s  5
0x4ca4  ldarg.0
0x4ca5  ldloca.s 5
0x4ca7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::get_Key()
0x4cac  call     instance void Microsoft.Crm.Extensibility.EntityValidator::StartRelationshipValidation(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship relationship)
0x4cb1  ldloca.s 5
0x4cb3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::get_Value()
0x4cb8  stloc.s  6
0x4cba  ldloc.s  6
0x4cbc  brfalse.s loc_4CFC
0x4cbe  ldloca.s 5
0x4cc0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::get_Key()
0x4cc5  ldarg.s  4
0x4cc7  call     class Microsoft.Crm.Extensibility.AssociateCommandBase Microsoft.Crm.Extensibility.AssociationCommandFactory::CreateInstance(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship relationship, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4ccc  stloc.s  8
0x4cce  ldloc.s  6
0x4cd0  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_EntityName()
0x4cd5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x4cda  brfalse.s loc_4CED
0x4cdc  ldloc.s  6
0x4cde  ldloc.s  8
0x4ce0  ldloc.2
0x4ce1  ldarg.s  4
0x4ce3  callvirt instance string Microsoft.Crm.Extensibility.AssociateCommandBase::FindRelatedEntityNameFromMetadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4ce8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::set_EntityName(string)
0x4ced  ldloc.s  8
0x4cef  ldloc.2
0x4cf0  ldarg.1
0x4cf1  ldarg.3
0x4cf2  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState Microsoft.Crm.Extensibility.EntityActionResolver::get_DefaultState()
0x4cf7  callvirt instance void Microsoft.Crm.Extensibility.AssociateCommandBase::SanitizeEntityForAssociation(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata primaryEntityMetadata, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity primaryEntity, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityState defaultState)
0x4cfc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4d01  ldstr    a0Relationship1// "{0}.Relationship ({1})"
0x4d06  ldc.i4.2
0x4d07  newarr   [mscorlib]System.Object
0x4d0c  dup
0x4d0d  ldc.i4.0
0x4d0e  ldarg.2
0x4d0f  stelem.ref
0x4d10  dup
0x4d11  ldc.i4.1
0x4d12  ldloca.s 5
0x4d14  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::get_Key()
0x4d19  callvirt instance string [mscorlib]System.Object::ToString()
0x4d1e  stelem.ref
0x4d1f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4d24  stloc.s  7
0x4d26  ldarg.0
0x4d27  ldloc.s  7
0x4d29  ldloca.s 5
0x4d2b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Relationship, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection>::get_Value()
0x4d30  ldarg.3
0x4d31  ldarg.s  4
0x4d33  call     instance void Microsoft.Crm.Extensibility.EntityValidator::ValidateRequiredMembers(string fieldName, object fieldValue, class Microsoft.Crm.Extensibility.EntityActionResolver entityActionResolver, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4d38  ldarg.0
0x4d39  call     instance void Microsoft.Crm.Extensibility.EntityValidator::EndRelationshipValidation()
0x4d3e  ldloc.s  4
0x4d40  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4d45  brtrue   loc_4C9B
0x4d4a  leave.s  loc_4D58
0x4d4c  ldloc.s  4
0x4d4e  brfalse.s loc_4D57
0x4d50  ldloc.s  4
0x4d52  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d57  endfinally
0x4d58  ret
```
