# Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::RetrieveObjectsTypeAndId

- ea: `0x43f20`
- end: `0x4409b`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::RetrieveObjectsTypeAndId`
- size: `379`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x43930`
- `0x43e70`

## callees

- `0x43f20`
- `0x44630`
- `0x46030`
- `0x462a0`
- `0x465f0`
- `0x46630`
- `0x46640`

## string_xrefs

- `0x43f95`: `componentstate`
- `0x43fc0`: `componentstate`
- `0x43ff2`: `Cannot do a shallow publish of {0} with id {1} because doing so would delete the item and cause child objects to be orphaned`

## pseudocode

```c

```

## disassembly

```asm
0x43f20  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>>::.ctor()
0x43f25  stloc.0
0x43f26  ldarg.1
0x43f27  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::GetEnumerator()
0x43f2c  stloc.1
0x43f2d  br       loc_4407D
0x43f32  ldloca.s 1
0x43f34  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Current()
0x43f39  stloc.2
0x43f3a  ldloca.s 2
0x43f3c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Key()
0x43f41  stloc.3
0x43f42  ldloca.s 2
0x43f44  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Value()
0x43f49  stloc.s  4
0x43f4b  ldloc.3
0x43f4c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_Name()
0x43f51  ldarg.3
0x43f52  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string metadataEntityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x43f57  stloc.s  5
0x43f59  ldloc.s  5
0x43f5b  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x43f60  ldloc.3
0x43f61  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x43f66  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x43f6b  ldc.i4.2
0x43f6c  ldloc.s  4
0x43f6e  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x43f73  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string metadataAttributeName, valuetype Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator conditionOperator, class [mscorlib]System.Array values)
0x43f78  ldloc.s  5
0x43f7a  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x43f7f  ldc.i4.2
0x43f80  newarr   [mscorlib]System.String
0x43f85  dup
0x43f86  ldc.i4.0
0x43f87  ldloc.3
0x43f88  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x43f8d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x43f92  stelem.ref
0x43f93  dup
0x43f94  ldc.i4.1
0x43f95  ldstr    aComponentstate// "componentstate"
0x43f9a  stelem.ref
0x43f9b  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumns(string[] attributeNames)
0x43fa0  ldarg.0
0x43fa1  ldloc.s  5
0x43fa3  ldarg.3
0x43fa4  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::RetrieveMultipleAsIfPublished(class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression queryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext sqlContext)
0x43fa9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x43fae  stloc.s  6
0x43fb0  br       loc_44063
0x43fb5  ldloc.s  6
0x43fb7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x43fbc  stloc.s  7
0x43fbe  ldloc.s  7
0x43fc0  ldstr    aComponentstate// "componentstate"
0x43fc5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x43fca  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x43fcf  stloc.s  8
0x43fd1  ldarg.2
0x43fd2  brtrue.s loc_44035
0x43fd4  ldloc.s  8
0x43fd6  ldc.i4.3
0x43fd7  bne.un.s loc_44035
0x43fd9  ldloc.s  7
0x43fdb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataEntityMetadata()
0x43fe0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataRelationshipMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_RelationshipsTo()
0x43fe5  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataRelationshipMetadata>::get_Count()
0x43fea  ldc.i4.0
0x43feb  ble.s    loc_44035
0x43fed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x43ff2  ldstr    aCannotDoAShall// "Cannot do a shallow publish of {0} with"...
0x43ff7  ldc.i4.2
0x43ff8  newarr   [mscorlib]System.Object
0x43ffd  dup
0x43ffe  ldc.i4.0
0x43fff  ldloc.3
0x44000  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_Name()
0x44005  stelem.ref
0x44006  dup
0x44007  ldc.i4.1
0x44008  ldloc.s  7
0x4400a  ldloc.3
0x4400b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x44010  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x44015  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4401a  unbox.any [mscorlib]System.Guid
0x4401f  box      [mscorlib]System.Guid
0x44024  stelem.ref
0x44025  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4402a  ldc.i4   0x80040203
0x4402f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x44034  throw
0x44035  ldloc.s  7
0x44037  ldloc.3
0x44038  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x4403d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_Name()
0x44042  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x44047  unbox.any [mscorlib]System.Guid
0x4404c  stloc.s  9
0x4404e  ldloc.0
0x4404f  ldloc.s  9
0x44051  ldloc.3
0x44052  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataObjectTypeCode [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_TypeCode()
0x44057  ldloc.s  8
0x44059  newobj   instance void class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>::.ctor(var<u1>, !!T0, var<u1>)
0x4405e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>>::Add(var<u1>)
0x44063  ldloc.s  6
0x44065  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4406a  brtrue   loc_43FB5
0x4406f  leave.s  loc_4407D
0x44071  ldloc.s  6
0x44073  brfalse.s loc_4407C
0x44075  ldloc.s  6
0x44077  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4407c  endfinally
0x4407d  ldloca.s 1
0x4407f  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::MoveNext()
0x44084  brtrue   loc_43F32
0x44089  leave.s  loc_44099
0x4408b  ldloca.s 1
0x4408d  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>
0x44093  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x44098  endfinally
0x44099  ldloc.0
0x4409a  ret
```
