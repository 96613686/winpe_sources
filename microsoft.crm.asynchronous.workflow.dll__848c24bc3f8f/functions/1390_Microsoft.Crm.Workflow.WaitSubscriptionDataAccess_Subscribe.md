# Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::Subscribe

- ea: `0x1390`
- end: `0x1436`
- name: `Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::Subscribe`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x34f0`

## callees

- `0x1390`
- `0x1440`
- `0x14f0`
- `0x1580`

## pseudocode

```c

```

## disassembly

```asm
0x1390  ldc.i4.0
0x1391  stloc.0
0x1392  ldsfld   string [mscorlib]System.String::Empty
0x1397  stloc.1
0x1398  ldarg.0
0x1399  ldarg.2
0x139a  ldarg.s  4
0x139c  ldarg.s  5
0x139e  call     instance string Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::RetrieveWaitOnAttributeList(valuetype [mscorlib]System.Guid workflowInstanceId, string entityName, valuetype [mscorlib]System.Guid entityId)
0x13a3  stloc.1
0x13a4  ldloc.1
0x13a5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13aa  brtrue.s loc_13AE
0x13ac  ldc.i4.1
0x13ad  stloc.0
0x13ae  ldloc.0
0x13af  brtrue.s loc_13C1
0x13b1  ldarg.0
0x13b2  ldarg.1
0x13b3  ldarg.2
0x13b4  ldarg.3
0x13b5  ldarg.s  4
0x13b7  ldarg.s  5
0x13b9  ldarg.s  6
0x13bb  call     instance void Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::CreateWaitSubscriptionRecord(valuetype [mscorlib]System.Guid subscriptionId, valuetype [mscorlib]System.Guid workflowInstanceId, valuetype [mscorlib]System.Guid queueId, string entityName, valuetype [mscorlib]System.Guid entityId, string attributeName)
0x13c0  ret
0x13c1  ldloc.1
0x13c2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13c7  brtrue.s loc_1426
0x13c9  ldc.i4.0
0x13ca  stloc.2
0x13cb  ldloc.1
0x13cc  ldc.i4.1
0x13cd  newarr   [mscorlib]System.Char
0x13d2  dup
0x13d3  ldc.i4.0
0x13d4  ldc.i4.s 0x2C
0x13d6  stelem.i2
0x13d7  ldc.i4.1
0x13d8  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x13dd  stloc.3
0x13de  ldc.i4.0
0x13df  stloc.s  4
0x13e1  br.s     loc_13FB
0x13e3  ldloc.3
0x13e4  ldloc.s  4
0x13e6  ldelem.ref
0x13e7  ldarg.s  6
0x13e9  ldc.i4.5
0x13ea  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x13ef  brfalse.s loc_13F5
0x13f1  ldc.i4.1
0x13f2  stloc.2
0x13f3  br.s     loc_1402
0x13f5  ldloc.s  4
0x13f7  ldc.i4.1
0x13f8  add
0x13f9  stloc.s  4
0x13fb  ldloc.s  4
0x13fd  ldloc.3
0x13fe  ldlen
0x13ff  conv.i4
0x1400  blt.s    loc_13E3
0x1402  ldloc.2
0x1403  brtrue.s loc_1429
0x1405  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x140a  ldstr    a01// "{0},{1}"
0x140f  ldc.i4.2
0x1410  newarr   [mscorlib]System.Object
0x1415  dup
0x1416  ldc.i4.0
0x1417  ldloc.1
0x1418  stelem.ref
0x1419  dup
0x141a  ldc.i4.1
0x141b  ldarg.s  6
0x141d  stelem.ref
0x141e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1423  stloc.1
0x1424  br.s     loc_1429
0x1426  ldarg.s  6
0x1428  stloc.1
0x1429  ldarg.0
0x142a  ldarg.2
0x142b  ldarg.s  4
0x142d  ldarg.s  5
0x142f  ldloc.1
0x1430  call     instance void Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::UpdateWaitSubscriptionRecord(valuetype [mscorlib]System.Guid workflowInstanceId, string entityName, valuetype [mscorlib]System.Guid entityId, string waitOnAttributeList)
0x1435  ret
```
