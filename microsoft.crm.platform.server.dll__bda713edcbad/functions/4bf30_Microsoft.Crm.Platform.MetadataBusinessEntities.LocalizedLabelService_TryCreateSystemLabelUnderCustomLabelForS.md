# Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::TryCreateSystemLabelUnderCustomLabelForSystemPicklistAttribute

- ea: `0x4bf30`
- end: `0x4c133`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::TryCreateSystemLabelUnderCustomLabelForSystemPicklistAttribute`
- size: `515`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x42740`
- `0x42ed0`
- `0x44510`
- `0x45fe0`
- `0x46010`
- `0x462a0`
- `0x464b0`
- `0x465f0`
- `0x46620`
- `0x46630`
- `0x46640`
- `0x46b50`
- `0x46f40`
- `0x4bf30`
- `0x4c3c0`

## string_xrefs

- `0x4c0f7`: `componentstate`
- `0x4bf68`: `overwritetime`
- `0x4bffe`: `overwritetime`
- `0x4c022`: `overwritetime`
- `0x4c074`: `overwritetime`
- `0x4c082`: `overwritetime`
- `0x4c0a9`: `overwritetime`

## pseudocode

```c

```

## disassembly

```asm
0x4bf30  ldarg.1
0x4bf31  ldstr    aLabel_2// "label"
0x4bf36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4bf3b  ldarg.2
0x4bf3c  ldstr    aContext// "context"
0x4bf41  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4bf46  ldstr    aLocalizedlabel// "LocalizedLabel"
0x4bf4b  ldarg.2
0x4bf4c  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string metadataEntityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4bf51  stloc.0
0x4bf52  ldloc.0
0x4bf53  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x4bf58  ldc.i4.2
0x4bf59  newarr   [mscorlib]System.String
0x4bf5e  dup
0x4bf5f  ldc.i4.0
0x4bf60  ldstr    aLocalizedlabel_0// "localizedlabelid"
0x4bf65  stelem.ref
0x4bf66  dup
0x4bf67  ldc.i4.1
0x4bf68  ldstr    aOverwritetime_0// "overwritetime"
0x4bf6d  stelem.ref
0x4bf6e  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumns(string[] attributeNames)
0x4bf73  ldloc.0
0x4bf74  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x4bf79  ldstr    aObjectid// "objectid"
0x4bf7e  ldarg.1
0x4bf7f  ldstr    aObjectid// "objectid"
0x4bf84  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4bf89  unbox.any [mscorlib]System.Guid
0x4bf8e  box      [mscorlib]System.Guid
0x4bf93  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string metadataAttributeName, object value)
0x4bf98  ldloc.0
0x4bf99  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x4bf9e  ldstr    aObjectcolumnna// "objectcolumnname"
0x4bfa3  ldarg.1
0x4bfa4  ldstr    aObjectcolumnna// "objectcolumnname"
0x4bfa9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4bfae  castclass [mscorlib]System.String
0x4bfb3  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string metadataAttributeName, object value)
0x4bfb8  ldloc.0
0x4bfb9  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x4bfbe  ldstr    aLanguageid_0// "languageid"
0x4bfc3  ldarg.1
0x4bfc4  ldstr    aLanguageid_0// "languageid"
0x4bfc9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4bfce  unbox.any [mscorlib]System.Int32
0x4bfd3  box      [mscorlib]System.Int32
0x4bfd8  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string metadataAttributeName, object value)
0x4bfdd  ldloc.0
0x4bfde  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x4bfe3  ldstr    aSolutionid_0// "solutionid"
0x4bfe8  ldc.i4.1
0x4bfe9  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x4bfee  box      [mscorlib]System.Guid
0x4bff3  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string metadataAttributeName, valuetype Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator conditionOperator, object value)
0x4bff8  ldloc.0
0x4bff9  callvirt instance class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleOrderCollection Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Orders()
0x4bffe  ldstr    aOverwritetime_0// "overwritetime"
0x4c003  ldc.i4.0
0x4c004  callvirt instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleOrderCollection::AddOrder(string attributeName, valuetype Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleOrderOperator orderOperator)
0x4c009  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::.ctor()
0x4c00e  ldloc.0
0x4c00f  ldarg.2
0x4c010  ldc.i4.1
0x4c011  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::RetrieveMultiple(class Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression queryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context, bool retrieveFromTable)
0x4c016  stloc.1
0x4c017  ldloc.1
0x4c018  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Count()
0x4c01d  brtrue.s loc_4C021
0x4c01f  ldc.i4.0
0x4c020  ret
0x4c021  ldarg.1
0x4c022  ldstr    aOverwritetime_0// "overwritetime"
0x4c027  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4c02c  box      [mscorlib]System.DateTime
0x4c031  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x4c036  ldc.i4.0
0x4c037  stloc.2
0x4c038  ldloc.1
0x4c039  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::GetEnumerator()
0x4c03e  stloc.3
0x4c03f  br       loc_4C0CA
0x4c044  ldloc.3
0x4c045  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity>::get_Current()
0x4c04a  stloc.s  4
0x4c04c  ldloc.2
0x4c04d  brtrue.s loc_4C072
0x4c04f  ldarg.1
0x4c050  ldstr    aLocalizedlabel_0// "localizedlabelid"
0x4c055  ldloc.s  4
0x4c057  ldstr    aLocalizedlabel_0// "localizedlabelid"
0x4c05c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4c061  unbox.any [mscorlib]System.Guid
0x4c066  box      [mscorlib]System.Guid
0x4c06b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x4c070  ldc.i4.1
0x4c071  stloc.2
0x4c072  ldloc.s  4
0x4c074  ldstr    aOverwritetime_0// "overwritetime"
0x4c079  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x4c07e  brtrue.s loc_4C093
0x4c080  ldloc.s  4
0x4c082  ldstr    aOverwritetime_0// "overwritetime"
0x4c087  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4c08c  unbox.any [mscorlib]System.DateTime
0x4c091  br.s     loc_4C098
0x4c093  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x4c098  stloc.s  5
0x4c09a  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::SolutionMinValue
0x4c09f  ldloc.s  5
0x4c0a1  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x4c0a6  brfalse.s loc_4C0CA
0x4c0a8  ldarg.1
0x4c0a9  ldstr    aOverwritetime_0// "overwritetime"
0x4c0ae  ldloca.s 5
0x4c0b0  ldc.i4.1
0x4c0b1  ldc.i4.0
0x4c0b2  ldc.i4.0
0x4c0b3  ldc.i4.0
0x4c0b4  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32, int32)
0x4c0b9  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.TimeSpan)
0x4c0be  box      [mscorlib]System.DateTime
0x4c0c3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x4c0c8  leave.s  loc_4C0E1
0x4c0ca  ldloc.3
0x4c0cb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4c0d0  brtrue   loc_4C044
0x4c0d5  leave.s  loc_4C0E1
0x4c0d7  ldloc.3
0x4c0d8  brfalse.s loc_4C0E0
0x4c0da  ldloc.3
0x4c0db  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c0e0  endfinally
0x4c0e1  ldarg.1
0x4c0e2  ldstr    aSolutionid_0// "solutionid"
0x4c0e7  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x4c0ec  box      [mscorlib]System.Guid
0x4c0f1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x4c0f6  ldarg.1
0x4c0f7  ldstr    aComponentstate// "componentstate"
0x4c0fc  ldc.i4.0
0x4c0fd  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x4c102  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x4c107  ldarg.1
0x4c108  ldstr    aIsmanaged// "ismanaged"
0x4c10d  ldc.i4.1
0x4c10e  box      [mscorlib]System.Boolean
0x4c113  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x4c118  ldarg.2
0x4c119  call     void Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataTimeStampUtility::TryRegisterEventForInsertMetadataTimestamp(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4c11e  ldarg.1
0x4c11f  ldarg.2
0x4c120  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleCreatePlan::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity entity, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4c125  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryPlan::get_Command()
0x4c12a  ldarg.2
0x4c12b  call     int32 Microsoft.Crm.Platform.MetadataBusinessEntities.DBCommandExecutor::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x4c130  pop
0x4c131  ldc.i4.1
0x4c132  ret
```
