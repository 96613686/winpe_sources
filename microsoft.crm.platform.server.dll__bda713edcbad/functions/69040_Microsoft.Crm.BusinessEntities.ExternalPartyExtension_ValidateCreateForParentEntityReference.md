# Microsoft.Crm.BusinessEntities.ExternalPartyExtension::ValidateCreateForParentEntityReference

- ea: `0x69040`
- end: `0x691a9`
- name: `Microsoft.Crm.BusinessEntities.ExternalPartyExtension::ValidateCreateForParentEntityReference`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x68f40`

## callees

- `0x66b60`
- `0x688c0`
- `0x68910`
- `0x69040`
- `0x69c10`

## string_xrefs

- `0x690b0`: `Invalid Owner Attribute Value to create new record. RegardingObject '{0}' of type '{1}' can't create entity '{2}'`
- `0x69159`: `ExternalParty '{0}' with  RegardingObject '{1}' does not have create access for entity '{2}'`

## pseudocode

```c

```

## disassembly

```asm
0x69040  ldarg.2
0x69041  ldfld    string LocalContextData::ParentEntityReferenceAttribute
0x69046  brtrue.s loc_69089
0x69048  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6904d  ldstr    aOrganizationSe// "Organization Settings for External Part"...
0x69052  ldc.i4.2
0x69053  newarr   [mscorlib]System.Object
0x69058  dup
0x69059  ldc.i4.0
0x6905a  ldarg.2
0x6905b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata LocalContextData::RegardingObjectMetadata
0x69060  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x69065  stelem.ref
0x69066  dup
0x69067  ldc.i4.1
0x69068  ldarg.1
0x69069  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x6906e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x69073  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x69078  stelem.ref
0x69079  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6907e  ldc.i4   0x8006110D
0x69083  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x69088  throw
0x69089  ldarg.2
0x6908a  ldfld    string LocalContextData::ParentEntityReferenceAttribute
0x6908f  stloc.0
0x69090  ldloc.0
0x69091  brfalse.s loc_690A6
0x69093  ldarg.1
0x69094  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x69099  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0x6909e  ldloc.0
0x6909f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x690a4  br.s     loc_690A7
0x690a6  ldnull
0x690a7  stloc.1
0x690a8  ldloc.1
0x690a9  brtrue.s loc_690FA
0x690ab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x690b0  ldstr    aInvalidOwnerAt// "Invalid Owner Attribute Value to create"...
0x690b5  ldc.i4.3
0x690b6  newarr   [mscorlib]System.Object
0x690bb  dup
0x690bc  ldc.i4.0
0x690bd  ldarg.2
0x690be  ldfld    valuetype [mscorlib]System.Guid LocalContextData::RegardingObjectId
0x690c3  box      [mscorlib]System.Guid
0x690c8  stelem.ref
0x690c9  dup
0x690ca  ldc.i4.1
0x690cb  ldarg.2
0x690cc  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata LocalContextData::RegardingObjectMetadata
0x690d1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x690d6  stelem.ref
0x690d7  dup
0x690d8  ldc.i4.2
0x690d9  ldarg.1
0x690da  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x690df  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x690e4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x690e9  stelem.ref
0x690ea  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x690ef  ldc.i4   0x8006110A
0x690f4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x690f9  throw
0x690fa  ldarg.0
0x690fb  ldarg.2
0x690fc  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata LocalContextData::RegardingObjectParentAttributeMetadata
0x69101  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x69106  ldarg.2
0x69107  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata LocalContextData::RegardingObjectMetadata
0x6910c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x69111  ldarg.2
0x69112  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata LocalContextData::RegardingObjectMetadata
0x69117  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x6911c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x69121  ldarg.2
0x69122  ldfld    valuetype [mscorlib]System.Guid LocalContextData::RegardingObjectId
0x69127  ldarg.1
0x69128  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x6912d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExternalPartyExtension::RetrieveParentId(string parentAttributeName, string entityName, string primaryKeyAttributeName, valuetype [mscorlib]System.Guid regardingObjectid, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x69132  ldloc.1
0x69133  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x69138  unbox.any [mscorlib]System.Guid
0x6913d  stloc.2
0x6913e  ldloc.2
0x6913f  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x69144  brfalse.s loc_691A8
0x69146  ldarg.2
0x69147  ldfld    valuetype [mscorlib]System.Guid LocalContextData::RegardingObjectId
0x6914c  ldloc.2
0x6914d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x69152  brfalse.s loc_691A8
0x69154  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x69159  ldstr    aExternalparty0// "ExternalParty '{0}' with  RegardingObje"...
0x6915e  ldc.i4.3
0x6915f  newarr   [mscorlib]System.Object
0x69164  dup
0x69165  ldc.i4.0
0x69166  ldarg.1
0x69167  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x6916c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_ExternalPartyId()
0x69171  box      [mscorlib]System.Guid
0x69176  stelem.ref
0x69177  dup
0x69178  ldc.i4.1
0x69179  ldarg.2
0x6917a  ldfld    valuetype [mscorlib]System.Guid LocalContextData::RegardingObjectId
0x6917f  box      [mscorlib]System.Guid
0x69184  stelem.ref
0x69185  dup
0x69186  ldc.i4.2
0x69187  ldarg.1
0x69188  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x6918d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x69192  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x69197  stelem.ref
0x69198  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6919d  ldc.i4   0x8006110A
0x691a2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x691a7  throw
0x691a8  ret
```
