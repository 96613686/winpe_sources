# Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity

- ea: `0x11470`
- end: `0x11505`
- name: `Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity`
- size: `149`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x10bc0`
- `0x111d0`
- `0x115d0`
- `0x11890`
- `0x119d0`
- `0x11c70`
- `0x11f70`
- `0x121a0`
- `0x12520`
- `0x12ca0`

## callees

- `0x11470`

## pseudocode

```c

```

## disassembly

```asm
0x11470  ldarg.s  4
0x11472  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x11477  stloc.0
0x11478  ldarg.0
0x11479  ldarg.1
0x1147a  ldarg.s  4
0x1147c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11481  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x11486  stloc.1
0x11487  ldarg.1
0x11488  ldarg.s  4
0x1148a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1148f  stloc.2
0x11490  ldloc.2
0x11491  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x11496  ldarg.3
0x11497  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x1149c  ldarg.2
0x1149d  brfalse.s loc_114E6
0x1149f  ldarg.2
0x114a0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Keys()
0x114a5  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, string>::GetEnumerator()
0x114aa  stloc.3
0x114ab  br.s     loc_114CD
0x114ad  ldloca.s 3
0x114af  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::get_Current()
0x114b4  stloc.s  4
0x114b6  ldloc.2
0x114b7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x114bc  ldloc.s  4
0x114be  ldc.i4.0
0x114bf  ldarg.2
0x114c0  ldloc.s  4
0x114c2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x114c7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x114cc  pop
0x114cd  ldloca.s 3
0x114cf  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>::MoveNext()
0x114d4  brtrue.s loc_114AD
0x114d6  leave.s  loc_114E6
0x114d8  ldloca.s 3
0x114da  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, string>
0x114e0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x114e5  endfinally
0x114e6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::.ctor()
0x114eb  ldloc.1
0x114ec  ldloc.2
0x114ed  ldarg.s  4
0x114ef  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x114f4  stloc.s  5
0x114f6  leave.s  loc_11502
0x114f8  ldloc.0
0x114f9  brfalse.s loc_11501
0x114fb  ldloc.0
0x114fc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11501  endfinally
0x11502  ldloc.s  5
0x11504  ret
```
