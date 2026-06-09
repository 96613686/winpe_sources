# Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::Evaluate

- ea: `0x1300`
- end: `0x16e9`
- name: `Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::Evaluate`
- size: `1001`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1300`
- `0x16f0`
- `0x17a0`

## pseudocode

```c

```

## disassembly

```asm
0x1300  ldarg.1
0x1301  brfalse.s loc_130A
0x1303  ldarg.1
0x1304  ldlen
0x1305  conv.i4
0x1306  ldc.i4.s 9
0x1308  beq.s    loc_131B
0x130a  ldc.i4   0x80048506
0x130f  ldc.i4.0
0x1310  newarr   [mscorlib]System.Object
0x1315  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x131a  throw
0x131b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1320  stloc.0
0x1321  ldc.i4.0
0x1322  stloc.1
0x1323  ldc.i4.1
0x1324  stloc.2
0x1325  ldloca.s 0
0x1327  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x132c  stloc.3
0x132d  ldc.i4.0
0x132e  stloc.s  4
0x1330  ldc.i4.1
0x1331  stloc.s  5
0x1333  ldloca.s 0
0x1335  call     instance int32 [mscorlib]System.DateTime::get_Month()
0x133a  stloc.s  6
0x133c  ldc.i4.0
0x133d  stloc.s  7
0x133f  ldc.i4.1
0x1340  stloc.s  8
0x1342  ldloca.s 0
0x1344  call     instance int32 [mscorlib]System.DateTime::get_Day()
0x1349  stloc.s  9
0x134b  ldloca.s 0
0x134d  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0x1352  stloc.s  0xA
0x1354  ldloca.s 0
0x1356  call     instance int32 [mscorlib]System.DateTime::get_Minute()
0x135b  stloc.s  0xB
0x135d  ldloca.s 0
0x135f  call     instance int32 [mscorlib]System.DateTime::get_Second()
0x1364  stloc.s  0xC
0x1366  ldarg.0
0x1367  ldarg.1
0x1368  call     instance void Microsoft.Crm.Transformations.AdvancedAddToCurrentDate::PerformParameterValidations(object[] input)
0x136d  ldarg.1
0x136e  ldc.i4.0
0x136f  ldelem.ref
0x1370  brfalse.s loc_137B
0x1372  ldarg.1
0x1373  ldc.i4.0
0x1374  ldelem.ref
0x1375  unbox.any [mscorlib]System.Int32
0x137a  stloc.1
0x137b  ldarg.1
0x137c  ldc.i4.1
0x137d  ldelem.ref
0x137e  brfalse.s loc_13CB
0x1380  ldarg.1
0x1381  ldc.i4.1
0x1382  ldelem.ref
0x1383  unbox.any [mscorlib]System.Int32
0x1388  stloc.2
0x1389  ldloc.2
0x138a  ldc.i4.1
0x138b  beq.s    loc_13CB
0x138d  ldloc.2
0x138e  brfalse.s loc_13CB
0x1390  ldc.i4   0x80048510
0x1395  ldc.i4.3
0x1396  newarr   [mscorlib]System.Object
0x139b  dup
0x139c  ldc.i4.0
0x139d  ldstr    a2// "2"
0x13a2  stelem.ref
0x13a3  dup
0x13a4  ldc.i4.1
0x13a5  ldloc.2
0x13a6  box      [mscorlib]System.Int32
0x13ab  stelem.ref
0x13ac  dup
0x13ad  ldc.i4.2
0x13ae  ldc.i4.0
0x13af  box      [mscorlib]System.Int32
0x13b4  ldstr    asc_3EE2// " - "
0x13b9  ldc.i4.1
0x13ba  box      [mscorlib]System.Int32
0x13bf  call     string [mscorlib]System.String::Concat(object, object, object)
0x13c4  stelem.ref
0x13c5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x13ca  throw
0x13cb  ldarg.1
0x13cc  ldc.i4.2
0x13cd  ldelem.ref
0x13ce  brfalse.s loc_13DA
0x13d0  ldarg.1
0x13d1  ldc.i4.2
0x13d2  ldelem.ref
0x13d3  unbox.any [mscorlib]System.Int32
0x13d8  stloc.s  4
0x13da  ldarg.1
0x13db  ldc.i4.3
0x13dc  ldelem.ref
0x13dd  brfalse.s loc_142E
0x13df  ldarg.1
0x13e0  ldc.i4.3
0x13e1  ldelem.ref
0x13e2  unbox.any [mscorlib]System.Int32
0x13e7  stloc.s  5
0x13e9  ldloc.s  5
0x13eb  ldc.i4.1
0x13ec  beq.s    loc_142E
0x13ee  ldloc.s  5
0x13f0  brfalse.s loc_142E
0x13f2  ldc.i4   0x80048510
0x13f7  ldc.i4.3
0x13f8  newarr   [mscorlib]System.Object
0x13fd  dup
0x13fe  ldc.i4.0
0x13ff  ldstr    a4// "4"
0x1404  stelem.ref
0x1405  dup
0x1406  ldc.i4.1
0x1407  ldloc.s  5
0x1409  box      [mscorlib]System.Int32
0x140e  stelem.ref
0x140f  dup
0x1410  ldc.i4.2
0x1411  ldc.i4.0
0x1412  box      [mscorlib]System.Int32
0x1417  ldstr    asc_3EE2// " - "
0x141c  ldc.i4.1
0x141d  box      [mscorlib]System.Int32
0x1422  call     string [mscorlib]System.String::Concat(object, object, object)
0x1427  stelem.ref
0x1428  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x142d  throw
0x142e  ldarg.1
0x142f  ldc.i4.4
0x1430  ldelem.ref
0x1431  brfalse.s loc_143D
0x1433  ldarg.1
0x1434  ldc.i4.4
0x1435  ldelem.ref
0x1436  unbox.any [mscorlib]System.Int32
0x143b  stloc.s  7
0x143d  ldarg.1
0x143e  ldc.i4.5
0x143f  ldelem.ref
0x1440  brfalse.s loc_1491
0x1442  ldarg.1
0x1443  ldc.i4.5
0x1444  ldelem.ref
0x1445  unbox.any [mscorlib]System.Int32
0x144a  stloc.s  8
0x144c  ldloc.s  8
0x144e  ldc.i4.1
0x144f  beq.s    loc_1491
0x1451  ldloc.s  8
0x1453  brfalse.s loc_1491
0x1455  ldc.i4   0x80048510
0x145a  ldc.i4.3
0x145b  newarr   [mscorlib]System.Object
0x1460  dup
0x1461  ldc.i4.0
0x1462  ldstr    a4// "4"
0x1467  stelem.ref
0x1468  dup
0x1469  ldc.i4.1
0x146a  ldloc.s  8
0x146c  box      [mscorlib]System.Int32
0x1471  stelem.ref
0x1472  dup
0x1473  ldc.i4.2
0x1474  ldc.i4.0
0x1475  box      [mscorlib]System.Int32
0x147a  ldstr    asc_3EE2// " - "
0x147f  ldc.i4.1
0x1480  box      [mscorlib]System.Int32
0x1485  call     string [mscorlib]System.String::Concat(object, object, object)
0x148a  stelem.ref
0x148b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1490  throw
0x1491  ldarg.1
0x1492  ldc.i4.6
0x1493  ldelem.ref
0x1494  brfalse.s loc_14A0
0x1496  ldarg.1
0x1497  ldc.i4.6
0x1498  ldelem.ref
0x1499  unbox.any [mscorlib]System.Int32
0x149e  stloc.s  0xA
0x14a0  ldarg.1
0x14a1  ldc.i4.7
0x14a2  ldelem.ref
0x14a3  brfalse.s loc_14AF
0x14a5  ldarg.1
0x14a6  ldc.i4.7
0x14a7  ldelem.ref
0x14a8  unbox.any [mscorlib]System.Int32
0x14ad  stloc.s  0xB
0x14af  ldarg.1
0x14b0  ldc.i4.8
0x14b1  ldelem.ref
0x14b2  brfalse.s loc_14BE
0x14b4  ldarg.1
0x14b5  ldc.i4.8
0x14b6  ldelem.ref
0x14b7  unbox.any [mscorlib]System.Int32
0x14bc  stloc.s  0xC
0x14be  nop
0x14bf  ldloc.3
0x14c0  ldloc.s  6
0x14c2  ldloc.s  9
0x14c4  ldloc.s  0xA
0x14c6  ldloc.s  0xB
0x14c8  ldloc.s  0xC
0x14ca  newobj   instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32, int32, int32, int32)
0x14cf  stloc.s  0xD
0x14d1  leave    loc_15AE
0x14d6  stloc.s  0xF
0x14d8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14dd  ldstr    aYear0Month1Day// "Year: {0}, Month: {1}, Day: {2}, Hours:"...
0x14e2  ldc.i4.6
0x14e3  newarr   [mscorlib]System.Object
0x14e8  dup
0x14e9  ldc.i4.0
0x14ea  ldloc.3
0x14eb  box      [mscorlib]System.Int32
0x14f0  stelem.ref
0x14f1  dup
0x14f2  ldc.i4.1
0x14f3  ldloc.s  6
0x14f5  box      [mscorlib]System.Int32
0x14fa  stelem.ref
0x14fb  dup
0x14fc  ldc.i4.2
0x14fd  ldloc.s  9
0x14ff  box      [mscorlib]System.Int32
0x1504  stelem.ref
0x1505  dup
0x1506  ldc.i4.3
0x1507  ldloc.s  0xA
0x1509  box      [mscorlib]System.Int32
0x150e  stelem.ref
0x150f  dup
0x1510  ldc.i4.4
0x1511  ldloc.s  0xB
0x1513  box      [mscorlib]System.Int32
0x1518  stelem.ref
0x1519  dup
0x151a  ldc.i4.5
0x151b  ldloc.s  0xC
0x151d  box      [mscorlib]System.Int32
0x1522  stelem.ref
0x1523  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1528  stloc.s  0x10
0x152a  ldloc.s  0xF
0x152c  ldc.i4   0x80048512
0x1531  ldc.i4.1
0x1532  newarr   [mscorlib]System.Object
0x1537  dup
0x1538  ldc.i4.0
0x1539  ldloc.s  0x10
0x153b  stelem.ref
0x153c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(class [mscorlib]System.Exception, int32, object[])
0x1541  throw
0x1542  stloc.s  0x11
0x1544  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1549  ldstr    aYear0Month1Day// "Year: {0}, Month: {1}, Day: {2}, Hours:"...
0x154e  ldc.i4.6
0x154f  newarr   [mscorlib]System.Object
0x1554  dup
0x1555  ldc.i4.0
0x1556  ldloc.3
0x1557  box      [mscorlib]System.Int32
0x155c  stelem.ref
0x155d  dup
0x155e  ldc.i4.1
0x155f  ldloc.s  6
0x1561  box      [mscorlib]System.Int32
0x1566  stelem.ref
0x1567  dup
0x1568  ldc.i4.2
0x1569  ldloc.s  9
0x156b  box      [mscorlib]System.Int32
0x1570  stelem.ref
0x1571  dup
0x1572  ldc.i4.3
0x1573  ldloc.s  0xA
0x1575  box      [mscorlib]System.Int32
0x157a  stelem.ref
0x157b  dup
0x157c  ldc.i4.4
0x157d  ldloc.s  0xB
0x157f  box      [mscorlib]System.Int32
0x1584  stelem.ref
0x1585  dup
  ... truncated ...
```
