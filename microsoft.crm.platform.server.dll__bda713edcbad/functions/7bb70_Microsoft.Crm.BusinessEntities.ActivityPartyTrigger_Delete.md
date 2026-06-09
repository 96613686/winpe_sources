# Microsoft.Crm.BusinessEntities.ActivityPartyTrigger::Delete

- ea: `0x7bb70`
- end: `0x7bc0b`
- name: `Microsoft.Crm.BusinessEntities.ActivityPartyTrigger::Delete`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x13c30`
- `0x1ab10`
- `0x1ae30`
- `0x1ef80`
- `0x222b0`
- `0x5d5d0`
- `0x7b060`

## string_xrefs

- `0x7bc00`: `Update`
- `0x7bb76`: `ispartydeleted`

## pseudocode

```c

```

## disassembly

```asm
0x7bb70  ldarg.0
0x7bb71  ldfld    class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.BusinessEntities.TriggerBase::columnSet
0x7bb76  ldstr    aIspartydeleted// "ispartydeleted"
0x7bb7b  ldc.i4.1
0x7bb7c  box      [mscorlib]System.Boolean
0x7bb81  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName, object value)
0x7bb86  ldstr    aActivityparty// "ActivityParty"
0x7bb8b  ldarg.0
0x7bb8c  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7bb91  newobj   instance void Microsoft.Crm.Query.FilterExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext orgContext)
0x7bb96  stloc.0
0x7bb97  ldloc.0
0x7bb98  ldstr    aPartyid// "partyid"
0x7bb9d  ldc.i4.0
0x7bb9e  ldarg.1
0x7bb9f  box      [mscorlib]System.Guid
0x7bba4  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x7bba9  pop
0x7bbaa  ldloc.0
0x7bbab  ldstr    aPartyobjecttyp// "partyobjecttypecode"
0x7bbb0  ldc.i4.0
0x7bbb1  ldarg.0
0x7bbb2  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.TriggerBase::entity
0x7bbb7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x7bbbc  box      [mscorlib]System.Int32
0x7bbc1  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x7bbc6  pop
0x7bbc7  ldstr    aActivityparty// "ActivityParty"
0x7bbcc  ldarg.0
0x7bbcd  ldfld    class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.BusinessEntities.TriggerBase::columnSet
0x7bbd2  ldloc.0
0x7bbd3  ldarg.0
0x7bbd4  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7bbd9  newobj   instance void Microsoft.Crm.Query.UpdatePlan::.ctor(string entityPlatformName, class Microsoft.Crm.Query.ColumnSetExpression 'cs', class Microsoft.Crm.Query.FilterExpression criteria, class Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x7bbde  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x7bbe3  ldarg.0
0x7bbe4  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7bbe9  call     int32 Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7bbee  pop
0x7bbef  ldarg.0
0x7bbf0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.BusinessEntities.ActivityPartyTrigger::emailAddresses
0x7bbf5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Clear()
0x7bbfa  ldarg.0
0x7bbfb  ldstr    aActivityparty// "ActivityParty"
0x7bc00  ldstr    aUpdate// "Update"
0x7bc05  call     instance void Microsoft.Crm.BusinessEntities.TriggerBase::TryAddEntityToChangedTypes(string entityPlatformName, string messageName)
0x7bc0a  ret
```
