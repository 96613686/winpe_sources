# Microsoft.Crm.Metadata.AttributeService::Create_0

- ea: `0x1a6e0`
- end: `0x1a7a2`
- name: `Microsoft.Crm.Metadata.AttributeService::Create_0`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xdda0`

## callees

- `0x19400`
- `0x1a6e0`
- `0x1a7b0`
- `0x48b90`

## string_xrefs

- `0x1a6f2`: `The AttributeDescription of the AttributeCreateData passed to Create must contain the attribute type id`
- `0x1a72e`: `State attributes cannot be created natively through the internal metadata service`
- `0x1a754`: `Status attributes cannot be created natively through the internal metadata service`
- `0x1a771`: `The AttributeDescription of the AttributeCreateData passed to Create must contain the entity id`

## pseudocode

```c

```

## disassembly

```asm
0x1a6e0  ldarg.1
0x1a6e1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x1a6e6  ldstr    aAttributetypei// "attributetypeid"
0x1a6eb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x1a6f0  brfalse.s loc_1A6FD
0x1a6f2  ldstr    aTheAttributede// "The AttributeDescription of the Attribu"...
0x1a6f7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x1a6fc  throw
0x1a6fd  ldarg.1
0x1a6fe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x1a703  ldstr    aAttributetypei// "attributetypeid"
0x1a708  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1a70d  unbox.any [mscorlib]System.Guid
0x1a712  dup
0x1a713  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x1a718  ldstr    aState// "state"
0x1a71d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x1a722  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x1a727  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a72c  brfalse.s loc_1A739
0x1a72e  ldstr    aStateAttribute_0// "State attributes cannot be created nati"...
0x1a733  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x1a738  throw
0x1a739  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x1a73e  ldstr    aStatus// "status"
0x1a743  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x1a748  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x1a74d  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a752  brfalse.s loc_1A75F
0x1a754  ldstr    aStatusAttribut_0// "Status attributes cannot be created nat"...
0x1a759  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x1a75e  throw
0x1a75f  ldarg.1
0x1a760  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x1a765  ldstr    aEntityid// "entityid"
0x1a76a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x1a76f  brfalse.s loc_1A77C
0x1a771  ldstr    aTheAttributede_0// "The AttributeDescription of the Attribu"...
0x1a776  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x1a77b  throw
0x1a77c  ldarg.1
0x1a77d  ldarg.2
0x1a77e  call     class Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeInfoFromAttributeCreateData(class Microsoft.Crm.Metadata.AttributeCreateData createData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x1a783  stloc.0
0x1a784  ldarg.0
0x1a785  ldarg.1
0x1a786  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x1a78b  ldstr    aEntityid// "entityid"
0x1a790  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1a795  unbox.any [mscorlib]System.Guid
0x1a79a  ldloc.0
0x1a79b  ldarg.2
0x1a79c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AttributeService::Create(valuetype [mscorlib]System.Guid entityId, class Microsoft.Crm.Metadata.AttributeInfo attributeInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1a7a1  ret
```
