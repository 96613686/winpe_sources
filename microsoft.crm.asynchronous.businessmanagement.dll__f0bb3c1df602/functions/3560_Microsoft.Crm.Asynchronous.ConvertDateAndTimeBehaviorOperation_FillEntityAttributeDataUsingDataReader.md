# Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::FillEntityAttributeDataUsingDataReader

- ea: `0x3560`
- end: `0x36a7`
- name: `Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::FillEntityAttributeDataUsingDataReader`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x2760`

## callees

- `0x3560`
- `0x13a10`
- `0x13a20`
- `0x13a40`
- `0x13a60`
- `0x13a70`
- `0x13aa0`
- `0x13ac0`
- `0x13ad0`

## pseudocode

```c

```

## disassembly

```asm
0x3560  newobj   instance void EntityConversionRules::.ctor()
0x3565  stloc.0
0x3566  ldloc.0
0x3567  ldarg.1
0x3568  ldarg.2
0x3569  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata EntityAttributeMetadataMap::get_EntityMetadata()
0x356e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x3573  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_TableColumnName()
0x3578  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x357d  unbox.any [mscorlib]System.Guid
0x3582  callvirt instance void EntityConversionRules::set_EntityId(valuetype [mscorlib]System.Guid value)
0x3587  ldarg.2
0x3588  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata> EntityAttributeMetadataMap::get_DateTimeAttributeMetadata()
0x358d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata>::GetEnumerator()
0x3592  stloc.1
0x3593  br.s     loc_3613
0x3595  ldloc.1
0x3596  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DateTimeAttributeMetadata>::get_Current()
0x359b  stloc.2
0x359c  ldarg.1
0x359d  ldloc.2
0x359e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x35a3  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x35a8  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x35ad  ldtoken  [mscorlib]System.DBNull
0x35b2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x35b7  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x35bc  brfalse.s loc_3613
0x35be  ldarg.1
0x35bf  ldloc.2
0x35c0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x35c5  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x35ca  unbox.any [mscorlib]System.DateTime
0x35cf  stloc.3
0x35d0  ldloca.s 4
0x35d2  initobj  [mscorlib]System.DateTime
0x35d8  ldloca.s 3
0x35da  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x35df  stloc.s  5
0x35e1  ldloca.s 5
0x35e3  ldloca.s 4
0x35e5  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x35ea  call     instance bool [mscorlib]System.TimeSpan::Equals(valuetype [mscorlib]System.TimeSpan)
0x35ef  brtrue.s loc_3613
0x35f1  ldloc.0
0x35f2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime> EntityConversionRules::get_AttributesForAutoConversion()
0x35f7  ldloc.2
0x35f8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x35fd  ldarg.1
0x35fe  ldloc.2
0x35ff  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x3604  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3609  unbox.any [mscorlib]System.DateTime
0x360e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime>::Add(var<u1>, !!T0)
0x3613  ldloc.1
0x3614  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3619  brtrue   loc_3595
0x361e  leave.s  loc_362A
0x3620  ldloc.1
0x3621  brfalse.s loc_3629
0x3623  ldloc.1
0x3624  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3629  endfinally
0x362a  ldarg.2
0x362b  callvirt instance string EntityAttributeMetadataMap::get_ConversionRuleAttributeColumnName()
0x3630  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3635  brtrue.s loc_3670
0x3637  ldarg.1
0x3638  ldarg.2
0x3639  callvirt instance string EntityAttributeMetadataMap::get_ConversionRuleAttributeColumnName()
0x363e  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3643  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3648  ldtoken  [mscorlib]System.DBNull
0x364d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3652  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3657  brfalse.s loc_3670
0x3659  ldloc.0
0x365a  ldarg.1
0x365b  ldarg.2
0x365c  callvirt instance string EntityAttributeMetadataMap::get_ConversionRuleAttributeColumnName()
0x3661  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x3666  unbox.any [mscorlib]System.Guid
0x366b  callvirt instance void EntityConversionRules::set_UserIdForConversion(valuetype [mscorlib]System.Guid value)
0x3670  ldarg.2
0x3671  callvirt instance string EntityAttributeMetadataMap::get_ConversionRuleAttributeColumnName()
0x3676  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x367b  brtrue.s loc_36A5
0x367d  ldarg.2
0x367e  callvirt instance string EntityAttributeMetadataMap::get_ConversionRuleAttributeColumnName()
0x3683  ldstr    aOwnerid_0// "OwnerId"
0x3688  call     bool [mscorlib]System.String::op_Equality(string, string)
0x368d  brfalse.s loc_36A5
0x368f  ldloc.0
0x3690  ldarg.1
0x3691  ldstr    aOwneridtype// "OwnerIdType"
0x3696  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x369b  unbox.any [mscorlib]System.Int32
0x36a0  callvirt instance void EntityConversionRules::set_OwnerIdType(int32 value)
0x36a5  ldloc.0
0x36a6  ret
```
