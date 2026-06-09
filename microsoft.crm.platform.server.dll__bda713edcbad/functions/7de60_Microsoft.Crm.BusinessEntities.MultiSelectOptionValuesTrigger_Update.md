# Microsoft.Crm.BusinessEntities.MultiSelectOptionValuesTrigger::Update

- ea: `0x7de60`
- end: `0x7e011`
- name: `Microsoft.Crm.BusinessEntities.MultiSelectOptionValuesTrigger::Update`
- size: `433`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x13990`
- `0x13c30`
- `0x15a40`
- `0x1ab10`
- `0x1ae30`
- `0x1ef80`
- `0x222b0`
- `0x5d5d0`
- `0x7dce0`
- `0x7de60`

## string_xrefs

- `0x7df27`: `In MultiSelectOptionValuesTrigger Update trigger - calling Update/DeletePlan - time taken for Update = {0} in milliseconds`
- `0x7dfc6`: `In MultiSelectOptionValuesTrigger Update trigger - calling Update/UpdatePlan - time taken for Update = {0} in milliseconds`

## pseudocode

```c

```

## disassembly

```asm
0x7de60  ldarg.0
0x7de61  ldfld    bool Microsoft.Crm.BusinessEntities.MultiSelectOptionValuesTrigger::isMultiSelectOptionSetAttribute
0x7de66  brtrue.s loc_7DE69
0x7de68  ret
0x7de69  ldarg.0
0x7de6a  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype MultiSelectOptionsInfo> Microsoft.Crm.BusinessEntities.MultiSelectOptionValuesTrigger::changeList
0x7de6f  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype MultiSelectOptionsInfo>::GetEnumerator()
0x7de74  stloc.0
0x7de75  br       loc_7DFF4
0x7de7a  ldloca.s 0
0x7de7c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype MultiSelectOptionsInfo>::get_Current()
0x7de81  stloc.1
0x7de82  ldstr    aMultiselectatt// "MultiSelectAttributeOptionValues"
0x7de87  ldarg.0
0x7de88  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7de8d  newobj   instance void Microsoft.Crm.Query.FilterExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext orgContext)
0x7de92  stloc.2
0x7de93  ldloc.2
0x7de94  ldstr    aObjectid// "objectid"
0x7de99  ldc.i4.0
0x7de9a  ldarg.1
0x7de9b  box      [mscorlib]System.Guid
0x7dea0  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x7dea5  pop
0x7dea6  ldloc.2
0x7dea7  ldstr    aObjectcolumnnu_0// "objectcolumnnumber"
0x7deac  ldc.i4.0
0x7dead  ldloc.1
0x7deae  ldfld    int32 MultiSelectOptionsInfo::objectColumnNumber
0x7deb3  box      [mscorlib]System.Int32
0x7deb8  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x7debd  pop
0x7debe  ldloc.2
0x7debf  ldstr    aObjectidtypeco_0// "objectidtypecode"
0x7dec4  ldc.i4.0
0x7dec5  ldarg.0
0x7dec6  ldfld    int32 Microsoft.Crm.BusinessEntities.MultiSelectOptionValuesTrigger::objectTypeCode
0x7decb  box      [mscorlib]System.Int32
0x7ded0  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x7ded5  pop
0x7ded6  ldloc.1
0x7ded7  ldfld    object MultiSelectOptionsInfo::attributeValue
0x7dedc  isinst   [mscorlib]System.String
0x7dee1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7dee6  brfalse.s loc_7DF4F
0x7dee8  ldstr    aMultiselectatt// "MultiSelectAttributeOptionValues"
0x7deed  ldloc.2
0x7deee  newobj   instance void Microsoft.Crm.Query.DeletePlan::.ctor(string entityPlatformName, class Microsoft.Crm.Query.FilterExpression criteria)
0x7def3  ldarg.0
0x7def4  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.BusinessEntities.MultiSelectOptionValuesTrigger::sw
0x7def9  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x7defe  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x7df03  ldarg.0
0x7df04  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7df09  call     int32 Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7df0e  pop
0x7df0f  ldarg.0
0x7df10  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.BusinessEntities.MultiSelectOptionValuesTrigger::sw
0x7df15  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x7df1a  ldarg.0
0x7df1b  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7df20  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x7df25  ldc.i4.s 0x14
0x7df27  ldstr    aInMultiselecto_1// "In MultiSelectOptionValuesTrigger Updat"...
0x7df2c  ldc.i4.1
0x7df2d  newarr   [mscorlib]System.Object
0x7df32  dup
0x7df33  ldc.i4.0
0x7df34  ldarg.0
0x7df35  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.BusinessEntities.MultiSelectOptionValuesTrigger::sw
0x7df3a  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x7df3f  box      [mscorlib]System.Int64
0x7df44  stelem.ref
0x7df45  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7df4a  br       loc_7DFF4
0x7df4f  ldarg.0
0x7df50  ldstr    aMultiselectatt// "MultiSelectAttributeOptionValues"
0x7df55  ldarg.0
0x7df56  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7df5b  newobj   instance void Microsoft.Crm.Query.ColumnSetExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7df60  stfld    class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.BusinessEntities.TriggerBase::columnSet
0x7df65  ldarg.0
0x7df66  ldfld    class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.BusinessEntities.TriggerBase::columnSet
0x7df6b  ldstr    aSelectedoption_0// "selectedoptionvalues"
0x7df70  ldloc.1
0x7df71  ldfld    object MultiSelectOptionsInfo::attributeValue
0x7df76  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName, object value)
0x7df7b  ldstr    aMultiselectatt// "MultiSelectAttributeOptionValues"
0x7df80  ldarg.0
0x7df81  ldfld    class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.BusinessEntities.TriggerBase::columnSet
0x7df86  ldloc.2
0x7df87  ldarg.0
0x7df88  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7df8d  newobj   instance void Microsoft.Crm.Query.UpdatePlan::.ctor(string entityPlatformName, class Microsoft.Crm.Query.ColumnSetExpression 'cs', class Microsoft.Crm.Query.FilterExpression criteria, class Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x7df92  ldarg.0
0x7df93  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.BusinessEntities.MultiSelectOptionValuesTrigger::sw
0x7df98  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x7df9d  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x7dfa2  ldarg.0
0x7dfa3  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7dfa8  call     int32 Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7dfad  stloc.3
0x7dfae  ldarg.0
0x7dfaf  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.BusinessEntities.MultiSelectOptionValuesTrigger::sw
0x7dfb4  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x7dfb9  ldarg.0
0x7dfba  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7dfbf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x7dfc4  ldc.i4.s 0x14
0x7dfc6  ldstr    aInMultiselecto_2// "In MultiSelectOptionValuesTrigger Updat"...
0x7dfcb  ldc.i4.1
0x7dfcc  newarr   [mscorlib]System.Object
0x7dfd1  dup
0x7dfd2  ldc.i4.0
0x7dfd3  ldarg.0
0x7dfd4  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.BusinessEntities.MultiSelectOptionValuesTrigger::sw
0x7dfd9  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x7dfde  box      [mscorlib]System.Int64
0x7dfe3  stelem.ref
0x7dfe4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7dfe9  ldloc.3
0x7dfea  brtrue.s loc_7DFF4
0x7dfec  ldarg.0
0x7dfed  ldarg.1
0x7dfee  ldloc.1
0x7dfef  call     instance void Microsoft.Crm.BusinessEntities.MultiSelectOptionValuesTrigger::DoCreate(valuetype [mscorlib]System.Guid id, valuetype MultiSelectOptionsInfo info)
0x7dff4  ldloca.s 0
0x7dff6  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype MultiSelectOptionsInfo>::MoveNext()
0x7dffb  brtrue   loc_7DE7A
0x7e000  leave.s  loc_7E010
0x7e002  ldloca.s 0
0x7e004  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype MultiSelectOptionsInfo>
0x7e00a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7e00f  endfinally
0x7e010  ret
```
