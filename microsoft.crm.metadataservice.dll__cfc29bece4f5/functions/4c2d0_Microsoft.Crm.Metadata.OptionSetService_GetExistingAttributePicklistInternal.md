# Microsoft.Crm.Metadata.OptionSetService::GetExistingAttributePicklistInternal

- ea: `0x4c2d0`
- end: `0x4c526`
- name: `Microsoft.Crm.Metadata.OptionSetService::GetExistingAttributePicklistInternal`
- size: `598`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x416f0`
- `0x4c2b0`

## callees

- `0x42430`
- `0x4c2d0`

## string_xrefs

- `0x4c4b3`: `overwritetime`
- `0x4c4a4`: `componentstate`
- `0x4c459`: ` Id : {0}, Value : {1}, Optionsetid : {2}, SolutionId : {3} ComponentState : {4}, OverwriteTime: {5}`

## pseudocode

```c

```

## disassembly

```asm
0x4c2d0  ldstr    aAttributepickl// "AttributePicklistValue"
0x4c2d5  ldarg.3
0x4c2d6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4c2db  stloc.0
0x4c2dc  ldarg.3
0x4c2dd  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x4c2e2  ldc.i4.3
0x4c2e3  bne.un.s loc_4C2F3
0x4c2e5  ldloc.0
0x4c2e6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x4c2eb  ldc.i4.1
0x4c2ec  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddAllColumns(bool)
0x4c2f1  br.s     loc_4C2FE
0x4c2f3  ldloc.0
0x4c2f4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x4c2f9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddAllColumns()
0x4c2fe  ldloc.0
0x4c2ff  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x4c304  ldstr    aOptionsetid// "optionsetid"
0x4c309  ldc.i4.1
0x4c30a  newarr   [mscorlib]System.Guid
0x4c30f  dup
0x4c310  ldc.i4.0
0x4c311  ldarg.0
0x4c312  stelem   [mscorlib]System.Guid
0x4c317  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, class [mscorlib]System.Array)
0x4c31c  ldarga.s 2
0x4c31e  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x4c323  brfalse.s loc_4C345
0x4c325  ldloc.0
0x4c326  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x4c32b  ldstr    aValue// "value"
0x4c330  ldc.i4.1
0x4c331  newarr   [mscorlib]System.Int32
0x4c336  dup
0x4c337  ldc.i4.0
0x4c338  ldarga.s 2
0x4c33a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x4c33f  stelem.i4
0x4c340  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, class [mscorlib]System.Array)
0x4c345  ldloc.0
0x4c346  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleOrderCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Orders()
0x4c34b  ldstr    aDisplayorder// "displayorder"
0x4c350  ldc.i4.0
0x4c351  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleOrderCollection::AddOrder(string, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleOrderOperator)
0x4c356  ldloc.0
0x4c357  ldarg.3
0x4c358  ldc.i4.4
0x4c359  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataQueryLibrary::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget)
0x4c35e  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionByValueDictionary::.ctor()
0x4c363  stloc.1
0x4c364  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x4c369  stloc.2
0x4c36a  br       loc_4C50D
0x4c36f  ldloc.2
0x4c370  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x4c375  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x4c37a  stloc.3
0x4c37b  ldnull
0x4c37c  stloc.s  4
0x4c37e  ldnull
0x4c37f  stloc.s  5
0x4c381  ldnull
0x4c382  stloc.s  6
0x4c384  ldloc.3
0x4c385  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_AttributePicklistValueId()
0x4c38a  ldarg.3
0x4c38b  ldloca.s 4
0x4c38d  ldloca.s 5
0x4c38f  ldloca.s 6
0x4c391  call     void Microsoft.Crm.Metadata.EnumOptionService::GetExistingDisplayInformation(valuetype [mscorlib]System.Guid attributePicklistValueId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection& displayValues, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection& descriptions, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection& colors)
0x4c396  ldloc.3
0x4c397  ldarg.1
0x4c398  ldloc.3
0x4c399  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_AttributePicklistValueId()
0x4c39e  ldloc.s  4
0x4c3a0  ldloc.s  5
0x4c3a2  ldloc.s  6
0x4c3a4  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PreloadedEnumOptionMetadataDataProviderFull::.ctor(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection)
0x4c3a9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOptionValueFactory::CreateEnumOptionValue(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributePicklistValueDescription, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionMetadataDataProvider)
0x4c3ae  stloc.s  7
0x4c3b0  ldloc.1
0x4c3b1  ldloc.s  7
0x4c3b3  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x4c3b8  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::ContainsKey(var<u1>)
0x4c3bd  brfalse  loc_4C4FE
0x4c3c2  ldloc.1
0x4c3c3  ldloc.s  7
0x4c3c5  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x4c3ca  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Item(void)
0x4c3cf  pop
0x4c3d0  ldstr    aAttributepickl// "AttributePicklistValue"
0x4c3d5  ldarg.3
0x4c3d6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4c3db  stloc.s  8
0x4c3dd  ldloc.s  8
0x4c3df  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x4c3e4  ldc.i4.1
0x4c3e5  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddAllColumns(bool)
0x4c3ea  ldloc.s  8
0x4c3ec  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x4c3f1  ldstr    aOptionsetid// "optionsetid"
0x4c3f6  ldc.i4.1
0x4c3f7  newarr   [mscorlib]System.Guid
0x4c3fc  dup
0x4c3fd  ldc.i4.0
0x4c3fe  ldloc.s  7
0x4c400  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_OptionSetId()
0x4c405  stelem   [mscorlib]System.Guid
0x4c40a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, class [mscorlib]System.Array)
0x4c40f  ldloc.s  8
0x4c411  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x4c416  ldstr    aValue// "value"
0x4c41b  ldc.i4.1
0x4c41c  newarr   [mscorlib]System.Int32
0x4c421  dup
0x4c422  ldc.i4.0
0x4c423  ldloc.s  7
0x4c425  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x4c42a  stelem.i4
0x4c42b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, class [mscorlib]System.Array)
0x4c430  ldloc.s  8
0x4c432  ldarg.3
0x4c433  ldc.i4.0
0x4c434  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataQueryLibrary::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget)
0x4c439  ldstr    aInvaliddbstate_0// "InvalidDBStateError: Found duplicate at"...
0x4c43e  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x4c443  stloc.s  9
0x4c445  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x4c44a  stloc.s  0xA
0x4c44c  br.s     loc_4C4C9
0x4c44e  ldloc.s  0xA
0x4c450  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x4c455  stloc.s  0xB
0x4c457  ldloc.s  9
0x4c459  ldstr    aId0Value1Optio// " Id : {0}, Value : {1}, Optionsetid : {"...
0x4c45e  ldc.i4.6
0x4c45f  newarr   [mscorlib]System.Object
0x4c464  dup
0x4c465  ldc.i4.0
0x4c466  ldloc.s  0xB
0x4c468  ldstr    aAttributepickl_0// "attributepicklistvalueid"
0x4c46d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4c472  stelem.ref
0x4c473  dup
0x4c474  ldc.i4.1
0x4c475  ldloc.s  0xB
0x4c477  ldstr    aValue// "value"
0x4c47c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4c481  stelem.ref
0x4c482  dup
0x4c483  ldc.i4.2
0x4c484  ldloc.s  0xB
0x4c486  ldstr    aOptionsetid// "optionsetid"
0x4c48b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4c490  stelem.ref
0x4c491  dup
0x4c492  ldc.i4.3
0x4c493  ldloc.s  0xB
0x4c495  ldstr    aSolutionid// "solutionid"
0x4c49a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4c49f  stelem.ref
0x4c4a0  dup
0x4c4a1  ldc.i4.4
0x4c4a2  ldloc.s  0xB
0x4c4a4  ldstr    aComponentstate// "componentstate"
0x4c4a9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4c4ae  stelem.ref
0x4c4af  dup
0x4c4b0  ldc.i4.5
0x4c4b1  ldloc.s  0xB
0x4c4b3  ldstr    aOverwritetime// "overwritetime"
0x4c4b8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4c4bd  stelem.ref
0x4c4be  call     string [mscorlib]System.String::Format(string, object[])
0x4c4c3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x4c4c8  pop
0x4c4c9  ldloc.s  0xA
0x4c4cb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4c4d0  brtrue   loc_4C44E
0x4c4d5  leave.s  loc_4C4E3
0x4c4d7  ldloc.s  0xA
0x4c4d9  brfalse.s loc_4C4E2
0x4c4db  ldloc.s  0xA
0x4c4dd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c4e2  endfinally
0x4c4e3  ldnull
0x4c4e4  ldarg.3
0x4c4e5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x4c4ea  ldc.i4.s 0x19
0x4c4ec  ldloc.s  9
0x4c4ee  callvirt instance string [mscorlib]System.Object::ToString()
0x4c4f3  ldc.i4.0
0x4c4f4  newarr   [mscorlib]System.Object
0x4c4f9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4c4fe  ldloc.1
0x4c4ff  ldloc.s  7
0x4c501  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x4c506  ldloc.s  7
0x4c508  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::Add(var<u1>, !!T0)
0x4c50d  ldloc.2
0x4c50e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4c513  brtrue   loc_4C36F
0x4c518  leave.s  loc_4C524
0x4c51a  ldloc.2
0x4c51b  brfalse.s loc_4C523
0x4c51d  ldloc.2
0x4c51e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c523  endfinally
0x4c524  ldloc.1
0x4c525  ret
```
