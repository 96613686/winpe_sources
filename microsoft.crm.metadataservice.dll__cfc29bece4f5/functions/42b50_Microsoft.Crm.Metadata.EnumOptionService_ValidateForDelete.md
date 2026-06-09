# Microsoft.Crm.Metadata.EnumOptionService::ValidateForDelete

- ea: `0x42b50`
- end: `0x42eae`
- name: `Microsoft.Crm.Metadata.EnumOptionService::ValidateForDelete`
- size: `862`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x41a30`

## callees

- `0x42b50`

## string_xrefs

- `0x42bd2`: `Option of type {0} cannot be deleted. Only Picklist and Status options can be deleted.`
- `0x42c59`: `Each Status OptionSet must be linked to one and only one Status Attribute. Status OptionSet with Id = {0} is linked to a number of {1} Attributes.`
- `0x42e10`: `Each Status Option must be linked to one and only one State Option. Status Option with Id = {0} is linked to a number of {1} State Options having Value = {2}.`
- `0x42e74`: `Default Status options cannot be deleted. State option with Id {0} and Value {1} has this Status option as Default.`

## pseudocode

```c

```

## disassembly

```asm
0x42b50  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x42b55  ldarg.1
0x42b56  ldstr    aAttributepickl// "AttributePicklistValue"
0x42b5b  ldc.i4.3
0x42b5c  newarr   [mscorlib]System.String
0x42b61  dup
0x42b62  ldc.i4.0
0x42b63  ldstr    aValue// "value"
0x42b68  stelem.ref
0x42b69  dup
0x42b6a  ldc.i4.1
0x42b6b  ldstr    aOptionsetid// "optionsetid"
0x42b70  stelem.ref
0x42b71  dup
0x42b72  ldc.i4.2
0x42b73  ldstr    aStateStatusVal// "state_status_value"
0x42b78  stelem.ref
0x42b79  ldarg.2
0x42b7a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x42b7f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x42b84  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x42b89  stloc.0
0x42b8a  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x42b8f  ldloc.0
0x42b90  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_OptionSetId()
0x42b95  ldstr    aOptionset_0// "OptionSet"
0x42b9a  ldc.i4.2
0x42b9b  newarr   [mscorlib]System.String
0x42ba0  dup
0x42ba1  ldc.i4.0
0x42ba2  ldstr    aOptionsetid// "optionsetid"
0x42ba7  stelem.ref
0x42ba8  dup
0x42ba9  ldc.i4.1
0x42baa  ldstr    aOptionsettype// "optionsettype"
0x42baf  stelem.ref
0x42bb0  ldarg.2
0x42bb1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x42bb6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x42bbb  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x42bc0  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetType()
0x42bc5  stloc.1
0x42bc6  ldloc.1
0x42bc7  brfalse.s loc_42BF6
0x42bc9  ldc.i4.2
0x42bca  ldloc.1
0x42bcb  beq.s    loc_42BF6
0x42bcd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x42bd2  ldstr    aOptionOfType0C// "Option of type {0} cannot be deleted. O"...
0x42bd7  ldc.i4.1
0x42bd8  newarr   [mscorlib]System.Object
0x42bdd  dup
0x42bde  ldc.i4.0
0x42bdf  ldloc.1
0x42be0  box      [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType
0x42be5  stelem.ref
0x42be6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x42beb  ldc.i4   0x80044323
0x42bf0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x42bf5  throw
0x42bf6  ldc.i4.2
0x42bf7  ldloc.1
0x42bf8  bne.un   loc_42EAD
0x42bfd  ldloc.0
0x42bfe  stloc.2
0x42bff  ldstr    aAttribute// "Attribute"
0x42c04  ldarg.2
0x42c05  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42c0a  stloc.3
0x42c0b  ldloc.3
0x42c0c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x42c11  ldstr    aEntityid// "entityid"
0x42c16  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x42c1b  ldloc.3
0x42c1c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x42c21  ldstr    aOptionsetid// "optionsetid"
0x42c26  ldc.i4.0
0x42c27  ldloc.2
0x42c28  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_OptionSetId()
0x42c2d  box      [mscorlib]System.Guid
0x42c32  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator, object)
0x42c37  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x42c3c  ldloc.3
0x42c3d  ldarg.2
0x42c3e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x42c43  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x42c48  stloc.s  4
0x42c4a  ldc.i4.1
0x42c4b  ldloc.s  4
0x42c4d  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x42c52  beq.s    loc_42C91
0x42c54  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x42c59  ldstr    aEachStatusOpti// "Each Status OptionSet must be linked to"...
0x42c5e  ldc.i4.2
0x42c5f  newarr   [mscorlib]System.Object
0x42c64  dup
0x42c65  ldc.i4.0
0x42c66  ldloc.2
0x42c67  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_OptionSetId()
0x42c6c  box      [mscorlib]System.Guid
0x42c71  stelem.ref
0x42c72  dup
0x42c73  ldc.i4.1
0x42c74  ldloc.s  4
0x42c76  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x42c7b  box      [mscorlib]System.Int32
0x42c80  stelem.ref
0x42c81  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x42c86  ldc.i4   0x80040216
0x42c8b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x42c90  throw
0x42c91  ldloc.s  4
0x42c93  ldc.i4.0
0x42c94  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x42c99  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x42c9e  stloc.s  5
0x42ca0  ldstr    aAttribute// "Attribute"
0x42ca5  ldarg.2
0x42ca6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42cab  stloc.s  6
0x42cad  ldloc.s  6
0x42caf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x42cb4  ldstr    aOptionsetid// "optionsetid"
0x42cb9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x42cbe  ldloc.s  6
0x42cc0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x42cc5  ldstr    aEntityid// "entityid"
0x42cca  ldc.i4.0
0x42ccb  ldloc.s  5
0x42ccd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_EntityId()
0x42cd2  box      [mscorlib]System.Guid
0x42cd7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator, object)
0x42cdc  ldloc.s  6
0x42cde  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x42ce3  ldstr    aAttributetypei// "attributetypeid"
0x42ce8  ldc.i4.0
0x42ce9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesByName()
0x42cee  ldstr    aState// "state"
0x42cf3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x42cf8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Id()
0x42cfd  box      [mscorlib]System.Guid
0x42d02  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator, object)
0x42d07  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x42d0c  ldloc.s  6
0x42d0e  ldarg.2
0x42d0f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x42d14  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x42d19  stloc.s  7
0x42d1b  ldc.i4.1
0x42d1c  ldloc.s  7
0x42d1e  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x42d23  beq.s    loc_42D63
0x42d25  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x42d2a  ldstr    aEachEntityMust// "Each Entity must contain one and only o"...
0x42d2f  ldc.i4.2
0x42d30  newarr   [mscorlib]System.Object
0x42d35  dup
0x42d36  ldc.i4.0
0x42d37  ldloc.s  5
0x42d39  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_EntityId()
0x42d3e  box      [mscorlib]System.Guid
0x42d43  stelem.ref
0x42d44  dup
0x42d45  ldc.i4.1
0x42d46  ldloc.s  7
0x42d48  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x42d4d  box      [mscorlib]System.Int32
0x42d52  stelem.ref
0x42d53  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x42d58  ldc.i4   0x80040216
0x42d5d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x42d62  throw
0x42d63  ldloc.s  7
0x42d65  ldc.i4.0
0x42d66  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x42d6b  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x42d70  stloc.s  8
0x42d72  ldstr    aAttributepickl// "AttributePicklistValue"
0x42d77  ldarg.2
0x42d78  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x42d7d  stloc.s  9
0x42d7f  ldloc.s  9
0x42d81  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x42d86  ldstr    aStateStatusVal// "state_status_value"
0x42d8b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x42d90  ldloc.s  9
0x42d92  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x42d97  ldstr    aAttributepickl_0// "attributepicklistvalueid"
0x42d9c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x42da1  ldloc.s  9
0x42da3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x42da8  ldstr    aValue// "value"
0x42dad  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x42db2  ldloc.s  9
0x42db4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x42db9  ldstr    aOptionsetid// "optionsetid"
0x42dbe  ldc.i4.0
0x42dbf  ldloc.s  8
0x42dc1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_OptionSetId()
0x42dc6  box      [mscorlib]System.Guid
0x42dcb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator, object)
0x42dd0  ldloc.s  9
0x42dd2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x42dd7  ldstr    aValue// "value"
0x42ddc  ldc.i4.0
0x42ddd  ldloc.2
0x42dde  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_StateOrStatusValue()
0x42de3  box      [mscorlib]System.Int32
0x42de8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator, object)
0x42ded  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x42df2  ldloc.s  9
0x42df4  ldarg.2
0x42df5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x42dfa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x42dff  stloc.s  0xA
0x42e01  ldc.i4.1
0x42e02  ldloc.s  0xA
0x42e04  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x42e09  beq.s    loc_42E51
0x42e0b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x42e10  ldstr    aEachStatusOpti_0// "Each Status Option must be linked to on"...
0x42e15  ldc.i4.3
0x42e16  newarr   [mscorlib]System.Object
0x42e1b  dup
0x42e1c  ldc.i4.0
0x42e1d  ldarg.1
0x42e1e  box      [mscorlib]System.Guid
0x42e23  stelem.ref
0x42e24  dup
0x42e25  ldc.i4.1
0x42e26  ldloc.s  0xA
0x42e28  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x42e2d  box      [mscorlib]System.Int32
0x42e32  stelem.ref
0x42e33  dup
0x42e34  ldc.i4.2
0x42e35  ldloc.2
0x42e36  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_StateOrStatusValue()
0x42e3b  box      [mscorlib]System.Int32
0x42e40  stelem.ref
0x42e41  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x42e46  ldc.i4   0x80040216
0x42e4b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x42e50  throw
0x42e51  ldloc.s  0xA
0x42e53  ldc.i4.0
0x42e54  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Item(!!T0)
0x42e59  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x42e5e  stloc.s  0xB
0x42e60  ldloc.s  0xB
0x42e62  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_StateOrStatusValue()
0x42e67  ldloc.2
0x42e68  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_Value()
0x42e6d  bne.un.s loc_42EAD
0x42e6f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x42e74  ldstr    aDefaultStatusO// "Default Status options cannot be delete"...
0x42e79  ldc.i4.2
0x42e7a  newarr   [mscorlib]System.Object
0x42e7f  dup
0x42e80  ldc.i4.0
0x42e81  ldloc.s  0xB
0x42e83  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_AttributePicklistValueId()
0x42e88  box      [mscorlib]System.Guid
0x42e8d  stelem.ref
0x42e8e  dup
0x42e8f  ldc.i4.1
0x42e90  ldloc.s  0xB
0x42e92  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_Value()
0x42e97  box      [mscorlib]System.Int32
0x42e9c  stelem.ref
0x42e9d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x42ea2  ldc.i4   0x80044341
0x42ea7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x42eac  throw
0x42ead  ret
```
