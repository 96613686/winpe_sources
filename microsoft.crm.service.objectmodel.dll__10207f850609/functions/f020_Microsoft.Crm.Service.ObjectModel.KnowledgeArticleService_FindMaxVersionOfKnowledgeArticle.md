# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::FindMaxVersionOfKnowledgeArticle

- ea: `0xf020`
- end: `0xf117`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::FindMaxVersionOfKnowledgeArticle`
- size: `247`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xd4b0`
- `0xd6f0`
- `0xd960`

## callees

- `0xf020`

## pseudocode

```c

```

## disassembly

```asm
0xf020  ldnull
0xf021  stloc.0
0xf022  ldstr    aKnowledgeartic// "KnowledgeArticle"
0xf027  ldarg.3
0xf028  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xf02d  stloc.1
0xf02e  ldloc.1
0xf02f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xf034  ldc.i4.4
0xf035  newarr   [mscorlib]System.String
0xf03a  dup
0xf03b  ldc.i4.0
0xf03c  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xf041  stelem.ref
0xf042  dup
0xf043  ldc.i4.1
0xf044  ldstr    aMajorversionnu// "majorversionnumber"
0xf049  stelem.ref
0xf04a  dup
0xf04b  ldc.i4.2
0xf04c  ldstr    aMinorversionnu// "minorversionnumber"
0xf051  stelem.ref
0xf052  dup
0xf053  ldc.i4.3
0xf054  ldstr    aLanguagelocale// "languagelocaleid"
0xf059  stelem.ref
0xf05a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xf05f  ldloc.1
0xf060  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xf065  ldstr    aArticlepublicn// "articlepublicnumber"
0xf06a  ldc.i4.0
0xf06b  ldarg.1
0xf06c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xf071  pop
0xf072  ldloc.1
0xf073  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xf078  ldstr    aLanguagelocale// "languagelocaleid"
0xf07d  ldc.i4.0
0xf07e  ldarg.2
0xf07f  box      [mscorlib]System.Guid
0xf084  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xf089  pop
0xf08a  ldloc.1
0xf08b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Order()
0xf090  ldstr    aMajorversionnu// "majorversionnumber"
0xf095  ldc.i4.1
0xf096  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0xf09b  ldloc.1
0xf09c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Order()
0xf0a1  ldstr    aMinorversionnu// "minorversionnumber"
0xf0a6  ldc.i4.1
0xf0a7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0xf0ac  ldloc.1
0xf0ad  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.TopExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Top()
0xf0b2  ldc.i4.1
0xf0b3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.TopExpression::set_Count(int32)
0xf0b8  ldarg.0
0xf0b9  ldloc.1
0xf0ba  ldarg.3
0xf0bb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf0c0  stloc.2
0xf0c1  ldloc.2
0xf0c2  brfalse.s loc_F115
0xf0c4  ldloc.2
0xf0c5  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xf0ca  ldc.i4.0
0xf0cb  ble.s    loc_F115
0xf0cd  ldloc.2
0xf0ce  ldc.i4.0
0xf0cf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0xf0d4  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xf0d9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xf0de  unbox.any [mscorlib]System.Guid
0xf0e3  ldloc.2
0xf0e4  ldc.i4.0
0xf0e5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0xf0ea  ldstr    aMajorversionnu// "majorversionnumber"
0xf0ef  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xf0f4  unbox.any [mscorlib]System.Int32
0xf0f9  ldloc.2
0xf0fa  ldc.i4.0
0xf0fb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0xf100  ldstr    aMinorversionnu// "minorversionnumber"
0xf105  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xf10a  unbox.any [mscorlib]System.Int32
0xf10f  newobj   instance void class [mscorlib]System.Tuple`3<valuetype [mscorlib]System.Guid, int32, int32>::.ctor(var<u1>, !!T0, var<u1>)
0xf114  stloc.0
0xf115  ldloc.0
0xf116  ret
```
