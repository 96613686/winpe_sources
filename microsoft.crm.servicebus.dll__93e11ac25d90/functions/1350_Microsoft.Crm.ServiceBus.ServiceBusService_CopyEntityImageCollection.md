# Microsoft.Crm.ServiceBus.ServiceBusService::CopyEntityImageCollection

- ea: `0x1350`
- end: `0x1384`
- name: `Microsoft.Crm.ServiceBus.ServiceBusService::CopyEntityImageCollection`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xfe0`

## callees

- `0x1350`

## pseudocode

```c

```

## disassembly

```asm
0x1350  ldarg.0
0x1351  brtrue.s loc_1354
0x1353  ret
0x1354  ldarg.1
0x1355  brtrue.s loc_1358
0x1357  ret
0x1358  ldarg.0
0x1359  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x135e  stloc.0
0x135f  br.s     loc_136F
0x1361  ldloc.0
0x1362  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>>::get_Current()
0x1367  stloc.1
0x1368  ldarg.1
0x1369  ldloc.1
0x136a  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>)
0x136f  ldloc.0
0x1370  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1375  brtrue.s loc_1361
0x1377  leave.s  loc_1383
0x1379  ldloc.0
0x137a  brfalse.s loc_1382
0x137c  ldloc.0
0x137d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1382  endfinally
0x1383  ret
```
