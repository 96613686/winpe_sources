# Microsoft.Crm.BusinessEntities.AddressTrigger::Update

- ea: `0x7c260`
- end: `0x7c381`
- name: `Microsoft.Crm.BusinessEntities.AddressTrigger::Update`
- size: `289`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14230`
- `0x1ab10`
- `0x1ae30`
- `0x1ef80`
- `0x222b0`
- `0x5a520`
- `0x5d5d0`
- `0x7af80`
- `0x7b020`
- `0x7b060`
- `0x7c260`

## string_xrefs

- `0x7c376`: `Update`
- `0x7c280`: `addressid`

## pseudocode

```c

```

## disassembly

```asm
0x7c260  ldarg.0
0x7c261  ldfld    class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.BusinessEntities.TriggerBase::columnSet
0x7c266  callvirt instance class Microsoft.Crm.Query.AttributeExpressionCollection Microsoft.Crm.Query.ColumnSetExpression::get_Attributes()
0x7c26b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Query.AttributeExpression>::get_Count()
0x7c270  brtrue.s loc_7C273
0x7c272  ret
0x7c273  ldc.i4.1
0x7c274  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(int32)
0x7c279  stloc.0
0x7c27a  ldarg.0
0x7c27b  ldfld    string Microsoft.Crm.BusinessEntities.AddressTrigger::addressPropertyPrefix
0x7c280  ldstr    aAddressid// "addressid"
0x7c285  call     string [mscorlib]System.String::Concat(string, string)
0x7c28a  stloc.2
0x7c28b  ldloc.0
0x7c28c  ldloc.2
0x7c28d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x7c292  pop
0x7c293  ldarg.0
0x7c294  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.TriggerBase::entity
0x7c299  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x7c29e  ldarg.1
0x7c29f  ldloc.0
0x7c2a0  ldarg.0
0x7c2a1  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7c2a6  call     class [mscorlib]System.Collections.Hashtable Microsoft.Crm.BusinessEntities.BusinessProcessObject::GetValuesFromDatabase(string entityName, valuetype [mscorlib]System.Guid entityId, class [mscorlib]System.Collections.ArrayList attributes, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7c2ab  stloc.1
0x7c2ac  ldloc.1
0x7c2ad  ldloc.2
0x7c2ae  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x7c2b3  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x7c2b8  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x7c2bd  brfalse.s loc_7C2F6
0x7c2bf  ldarg.0
0x7c2c0  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.TriggerBase::entity
0x7c2c5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x7c2ca  ldstr    aContact// "Contact"
0x7c2cf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7c2d4  brfalse  loc_7C380
0x7c2d9  ldarg.0
0x7c2da  ldfld    string Microsoft.Crm.BusinessEntities.AddressTrigger::addressPropertyPrefix
0x7c2df  ldstr    aAddress3// "address3_"
0x7c2e4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7c2e9  brfalse  loc_7C380
0x7c2ee  ldarg.0
0x7c2ef  ldarg.1
0x7c2f0  callvirt instance void Microsoft.Crm.BusinessEntities.TriggerBase::Create(valuetype [mscorlib]System.Guid id)
0x7c2f5  ret
0x7c2f6  ldloc.1
0x7c2f7  ldloc.2
0x7c2f8  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x7c2fd  unbox.any [mscorlib]System.Guid
0x7c302  stloc.3
0x7c303  ldarg.0
0x7c304  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.AddressTrigger::addressEntity
0x7c309  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x7c30e  ldarg.0
0x7c30f  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7c314  newobj   instance void Microsoft.Crm.Query.FilterExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext orgContext)
0x7c319  stloc.s  4
0x7c31b  ldloc.s  4
0x7c31d  ldarg.0
0x7c31e  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.BusinessEntities.AddressTrigger::addressPrimaryKey
0x7c323  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0x7c328  ldc.i4.0
0x7c329  ldloc.3
0x7c32a  box      [mscorlib]System.Guid
0x7c32f  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x7c334  pop
0x7c335  ldarg.0
0x7c336  call     instance void Microsoft.Crm.BusinessEntities.TriggerBase::SetModifiedAttributes()
0x7c33b  ldarg.0
0x7c33c  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.AddressTrigger::addressEntity
0x7c341  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x7c346  ldarg.0
0x7c347  ldfld    class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.BusinessEntities.TriggerBase::columnSet
0x7c34c  ldloc.s  4
0x7c34e  ldarg.0
0x7c34f  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7c354  newobj   instance void Microsoft.Crm.Query.UpdatePlan::.ctor(string entityPlatformName, class Microsoft.Crm.Query.ColumnSetExpression 'cs', class Microsoft.Crm.Query.FilterExpression criteria, class Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x7c359  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x7c35e  ldarg.0
0x7c35f  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7c364  call     int32 Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7c369  pop
0x7c36a  ldarg.0
0x7c36b  ldarg.0
0x7c36c  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.AddressTrigger::addressEntity
0x7c371  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x7c376  ldstr    aUpdate// "Update"
0x7c37b  call     instance void Microsoft.Crm.BusinessEntities.TriggerBase::TryAddEntityToChangedTypes(string entityPlatformName, string messageName)
0x7c380  ret
```
