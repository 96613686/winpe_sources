# Microsoft.Crm.BusinessEntities.OrganizationEmailConnectionChannelTrigger::Update

- ea: `0x7db50`
- end: `0x7dc1b`
- name: `Microsoft.Crm.BusinessEntities.OrganizationEmailConnectionChannelTrigger::Update`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x13c30`
- `0x1ab10`
- `0x1ab50`
- `0x1ae30`
- `0x1afa0`
- `0x1ef80`
- `0x222b0`
- `0x5d5d0`
- `0x7b060`
- `0x7db50`

## string_xrefs

- `0x7dc10`: `Update`
- `0x7db90`: `incomingemaildeliverymethod`

## pseudocode

```c

```

## disassembly

```asm
0x7db50  ldarg.0
0x7db51  ldfld    bool Microsoft.Crm.BusinessEntities.OrganizationEmailConnectionChannelTrigger::performUpdate
0x7db56  brtrue.s loc_7DB59
0x7db58  ret
0x7db59  ldstr    aMailbox// "Mailbox"
0x7db5e  ldarg.0
0x7db5f  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7db64  newobj   instance void Microsoft.Crm.Query.FilterExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext orgContext)
0x7db69  stloc.0
0x7db6a  ldloc.0
0x7db6b  ldstr    aStatecode// "statecode"
0x7db70  ldc.i4.0
0x7db71  ldc.i4.0
0x7db72  box      [mscorlib]System.Int32
0x7db77  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x7db7c  pop
0x7db7d  ldstr    aMailbox// "Mailbox"
0x7db82  ldc.i4.1
0x7db83  ldarg.0
0x7db84  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7db89  newobj   instance void Microsoft.Crm.Query.FilterExpression::.ctor(string entityPlatformName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator filterOperator, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7db8e  stloc.1
0x7db8f  ldloc.1
0x7db90  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x7db95  ldc.i4.0
0x7db96  ldc.i4.2
0x7db97  box      [mscorlib]System.Int32
0x7db9c  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x7dba1  pop
0x7dba2  ldloc.1
0x7dba3  ldstr    aActdeliverymet// "actdeliverymethod"
0x7dba8  ldc.i4.0
0x7dba9  ldc.i4.1
0x7dbaa  box      [mscorlib]System.Int32
0x7dbaf  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x7dbb4  pop
0x7dbb5  ldloc.0
0x7dbb6  ldloc.1
0x7dbb7  callvirt instance void Microsoft.Crm.Query.FilterExpression::AddFilter(class Microsoft.Crm.Query.FilterExpression childFilter)
0x7dbbc  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalNow()
0x7dbc1  stloc.2
0x7dbc2  ldloc.2
0x7dbc3  ldc.i4.0
0x7dbc4  ldc.i4.1
0x7dbc5  ldc.i4.0
0x7dbc6  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x7dbcb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::op_Addition(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime, valuetype [mscorlib]System.TimeSpan)
0x7dbd0  stloc.2
0x7dbd1  ldarg.0
0x7dbd2  ldfld    class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.BusinessEntities.TriggerBase::columnSet
0x7dbd7  ldstr    aPostponemailbo// "postponemailboxprocessinguntil"
0x7dbdc  ldloc.2
0x7dbdd  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName, object value)
0x7dbe2  ldstr    aMailbox// "Mailbox"
0x7dbe7  ldarg.0
0x7dbe8  ldfld    class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.BusinessEntities.TriggerBase::columnSet
0x7dbed  ldloc.0
0x7dbee  ldarg.0
0x7dbef  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7dbf4  newobj   instance void Microsoft.Crm.Query.UpdatePlan::.ctor(string entityPlatformName, class Microsoft.Crm.Query.ColumnSetExpression 'cs', class Microsoft.Crm.Query.FilterExpression criteria, class Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x7dbf9  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x7dbfe  ldarg.0
0x7dbff  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7dc04  call     int32 Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7dc09  pop
0x7dc0a  ldarg.0
0x7dc0b  ldstr    aMailbox// "Mailbox"
0x7dc10  ldstr    aUpdate// "Update"
0x7dc15  call     instance void Microsoft.Crm.BusinessEntities.TriggerBase::TryAddEntityToChangedTypes(string entityPlatformName, string messageName)
0x7dc1a  ret
```
