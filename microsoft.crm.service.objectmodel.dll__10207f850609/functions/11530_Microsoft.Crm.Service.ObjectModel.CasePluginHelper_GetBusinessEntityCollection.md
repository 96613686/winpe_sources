# Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntityCollection

- ea: `0x11530`
- end: `0x115ca`
- name: `Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntityCollection`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x11510`

## callees

- `0x11530`

## string_xrefs

- `0x115a2`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x11530  ldarg.3
0x11531  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x11536  stloc.0
0x11537  ldarg.0
0x11538  ldarg.3
0x11539  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1153e  stloc.1
0x1153f  ldloc.1
0x11540  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x11545  ldarg.2
0x11546  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x1154b  ldarg.1
0x1154c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Keys()
0x11551  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, string>::GetEnumerator()
0x11556  stloc.2
0x11557  br.s     loc_11576
0x11559  ldloca.s 2
0x1155b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::get_Current()
0x11560  stloc.3
0x11561  ldloc.1
0x11562  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x11567  ldloc.3
0x11568  ldc.i4.0
0x11569  ldarg.1
0x1156a  ldloc.3
0x1156b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x11570  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x11575  pop
0x11576  ldloca.s 2
0x11578  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::MoveNext()
0x1157d  brtrue.s loc_11559
0x1157f  leave.s  loc_1158F
0x11581  ldloca.s 2
0x11583  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>
0x11589  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1158e  endfinally
0x1158f  ldarg.0
0x11590  ldstr    aIncidentresolu// "IncidentResolution"
0x11595  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1159a  brfalse.s loc_115AD
0x1159c  ldloc.1
0x1159d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Order()
0x115a2  ldstr    aCreatedon// "createdon"
0x115a7  ldc.i4.1
0x115a8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.OrderExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x115ad  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::.ctor()
0x115b2  ldloc.1
0x115b3  ldarg.3
0x115b4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x115b9  stloc.s  4
0x115bb  leave.s  loc_115C7
0x115bd  ldloc.0
0x115be  brfalse.s loc_115C6
0x115c0  ldloc.0
0x115c1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x115c6  endfinally
0x115c7  ldloc.s  4
0x115c9  ret
```
