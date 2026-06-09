# Microsoft.Crm.ServiceBus.ServiceBusService::CopyParameterCollection

- ea: `0x1190`
- end: `0x12a3`
- name: `Microsoft.Crm.ServiceBus.ServiceBusService::CopyParameterCollection`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xfe0`

## callees

- `0x1190`
- `0x12b0`
- `0x1310`

## pseudocode

```c

```

## disassembly

```asm
0x1190  ldarg.0
0x1191  brtrue.s loc_1194
0x1193  ret
0x1194  ldarg.1
0x1195  brtrue.s loc_1198
0x1197  ret
0x1198  ldarg.0
0x1199  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::GetEnumerator()
0x119e  stloc.0
0x119f  br       loc_128B
0x11a4  ldloc.0
0x11a5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>>::get_Current()
0x11aa  stloc.1
0x11ab  ldloca.s 1
0x11ad  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x11b2  brfalse.s loc_11F4
0x11b4  ldloca.s 1
0x11b6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x11bb  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x11c0  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequestCollection
0x11c5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11ca  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x11cf  brfalse.s loc_11F4
0x11d1  ldarg.1
0x11d2  ldloca.s 1
0x11d4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x11d9  ldloca.s 1
0x11db  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x11e0  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequestCollection
0x11e5  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequestCollection Microsoft.Crm.ServiceBus.ServiceBusService::GetOrganizationRequestCollectionWithKnownTypes(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequestCollection inputRequestCollection)
0x11ea  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x11ef  br       loc_128B
0x11f4  ldloca.s 1
0x11f6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x11fb  brfalse.s loc_1210
0x11fd  ldloca.s 1
0x11ff  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x1204  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1209  call     bool Microsoft.Crm.ServiceBus.ServiceBusService::IsKnownType(class [mscorlib]System.Type valueType)
0x120e  brfalse.s loc_1226
0x1210  ldarg.1
0x1211  ldloca.s 1
0x1213  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x1218  ldloca.s 1
0x121a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x121f  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x1224  br.s     loc_128B
0x1226  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x122b  ldc.i4.s 0x2F
0x122d  ldstr    a0// "{0}"
0x1232  ldc.i4.1
0x1233  newarr   [mscorlib]System.Object
0x1238  dup
0x1239  ldc.i4.0
0x123a  ldstr    aSkippingParame// "Skipping parameter: {0} with value type"...
0x123f  ldc.i4.4
0x1240  newarr   [mscorlib]System.Object
0x1245  dup
0x1246  ldc.i4.0
0x1247  ldloca.s 1
0x1249  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x124e  stelem.ref
0x124f  dup
0x1250  ldc.i4.1
0x1251  ldloca.s 1
0x1253  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x1258  brfalse.s loc_126D
0x125a  ldloca.s 1
0x125c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x1261  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1266  callvirt instance string [mscorlib]System.Object::ToString()
0x126b  br.s     loc_1272
0x126d  ldstr    aNull// "null"
0x1272  stelem.ref
0x1273  dup
0x1274  ldc.i4.2
0x1275  ldarg.2
0x1276  stelem.ref
0x1277  dup
0x1278  ldc.i4.3
0x1279  ldarg.3
0x127a  box      [mscorlib]System.Guid
0x127f  stelem.ref
0x1280  call     string [mscorlib]System.String::Format(string, object[])
0x1285  stelem.ref
0x1286  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x128b  ldloc.0
0x128c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1291  brtrue   loc_11A4
0x1296  leave.s  loc_12A2
0x1298  ldloc.0
0x1299  brfalse.s loc_12A1
0x129b  ldloc.0
0x129c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12a1  endfinally
0x12a2  ret
```
