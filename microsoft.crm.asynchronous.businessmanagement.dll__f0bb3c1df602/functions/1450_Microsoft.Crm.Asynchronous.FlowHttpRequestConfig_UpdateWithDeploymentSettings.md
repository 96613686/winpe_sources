# Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::UpdateWithDeploymentSettings

- ea: `0x1450`
- end: `0x15c4`
- name: `Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::UpdateWithDeploymentSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1630`

## callees

- `0x13b0`
- `0x13d0`
- `0x13f0`
- `0x1410`
- `0x1450`

## pseudocode

```c

```

## disassembly

```asm
0x1450  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x1455  ldarg.1
0x1456  ldsfld   string [mscorlib]System.String::Empty
0x145b  callvirt T0x2B000002
0x1460  stloc.0
0x1461  ldloc.0
0x1462  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1467  brfalse.s loc_146E
0x1469  leave    loc_15C3
0x146e  ldloc.0
0x146f  callvirt instance string [mscorlib]System.String::Trim()
0x1474  stloc.0
0x1475  ldloc.0
0x1476  ldc.i4.1
0x1477  newarr   [mscorlib]System.Char
0x147c  dup
0x147d  ldc.i4.0
0x147e  ldc.i4.s 0x3B
0x1480  stelem.i2
0x1481  ldc.i4.1
0x1482  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x1487  stloc.1
0x1488  ldloc.1
0x1489  ldlen
0x148a  brfalse  loc_159A
0x148f  ldloc.1
0x1490  stloc.2
0x1491  ldc.i4.0
0x1492  stloc.3
0x1493  br       loc_1591
0x1498  ldloc.2
0x1499  ldloc.3
0x149a  ldelem.ref
0x149b  ldc.i4.1
0x149c  newarr   [mscorlib]System.Char
0x14a1  dup
0x14a2  ldc.i4.0
0x14a3  ldc.i4.s 0x3D
0x14a5  stelem.i2
0x14a6  ldc.i4.1
0x14a7  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x14ac  stloc.s  4
0x14ae  ldloc.s  4
0x14b0  ldlen
0x14b1  conv.i4
0x14b2  ldc.i4.2
0x14b3  bne.un   loc_1570
0x14b8  ldloc.s  4
0x14ba  ldc.i4.0
0x14bb  ldelem.ref
0x14bc  callvirt instance string [mscorlib]System.String::ToLower()
0x14c1  stloc.s  5
0x14c3  ldloc.s  4
0x14c5  ldc.i4.1
0x14c6  ldelem.ref
0x14c7  stloc.s  6
0x14c9  ldloc.s  5
0x14cb  ldstr    aConnectionlimi// "connectionlimit"
0x14d0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14d5  brtrue.s loc_1503
0x14d7  ldloc.s  5
0x14d9  ldstr    aConnectionleas// "connectionleasetimeoutinsecs"
0x14de  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14e3  brtrue.s loc_1512
0x14e5  ldloc.s  5
0x14e7  ldstr    aMaxidletimeins// "maxidletimeinsecs"
0x14ec  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14f1  brtrue.s loc_1527
0x14f3  ldloc.s  5
0x14f5  ldstr    aHttprequesttim// "httprequesttimeoutinsecs"
0x14fa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14ff  brtrue.s loc_153C
0x1501  br.s     loc_1551
0x1503  ldarg.0
0x1504  ldloc.s  6
0x1506  call     int32 [mscorlib]System.Int32::Parse(string)
0x150b  call     instance void Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::set_ConnectionLimit(int32 value)
0x1510  br.s     loc_158D
0x1512  ldarg.0
0x1513  ldloc.s  6
0x1515  call     int32 [mscorlib]System.Int32::Parse(string)
0x151a  ldc.i4   0x3E8
0x151f  mul
0x1520  call     instance void Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::set_ConnectionLeaseTimeoutInMilliSeconds(int32 value)
0x1525  br.s     loc_158D
0x1527  ldarg.0
0x1528  ldloc.s  6
0x152a  call     int32 [mscorlib]System.Int32::Parse(string)
0x152f  ldc.i4   0x3E8
0x1534  mul
0x1535  call     instance void Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::set_MaxIdleTimeInMilliSeconds(int32 value)
0x153a  br.s     loc_158D
0x153c  ldarg.0
0x153d  ldloc.s  6
0x153f  call     int32 [mscorlib]System.Int32::Parse(string)
0x1544  ldc.i4   0x3E8
0x1549  mul
0x154a  call     instance void Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::set_HttpRequestTimeoutInMilliSeconds(int32 value)
0x154f  br.s     loc_158D
0x1551  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::Logger
0x1556  ldstr    aInvalidKeySpec// "Invalid key specified in setting:{0}, v"...
0x155b  ldc.i4.2
0x155c  newarr   [mscorlib]System.Object
0x1561  dup
0x1562  ldc.i4.0
0x1563  ldarg.1
0x1564  stelem.ref
0x1565  dup
0x1566  ldc.i4.1
0x1567  ldloc.0
0x1568  stelem.ref
0x1569  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x156e  br.s     loc_158D
0x1570  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::Logger
0x1575  ldstr    aInvalidKeyvalu// "Invalid keyvalue pair specified for set"...
0x157a  ldc.i4.2
0x157b  newarr   [mscorlib]System.Object
0x1580  dup
0x1581  ldc.i4.0
0x1582  ldarg.1
0x1583  stelem.ref
0x1584  dup
0x1585  ldc.i4.1
0x1586  ldloc.0
0x1587  stelem.ref
0x1588  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x158d  ldloc.3
0x158e  ldc.i4.1
0x158f  add
0x1590  stloc.3
0x1591  ldloc.3
0x1592  ldloc.2
0x1593  ldlen
0x1594  conv.i4
0x1595  blt      loc_1498
0x159a  leave.s  loc_15C3
0x159c  stloc.s  7
0x159e  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::Logger
0x15a3  ldstr    aHitExceptionWh// "Hit exception when trying to fetch depl"...
0x15a8  ldc.i4.2
0x15a9  newarr   [mscorlib]System.Object
0x15ae  dup
0x15af  ldc.i4.0
0x15b0  ldarg.1
0x15b1  stelem.ref
0x15b2  dup
0x15b3  ldc.i4.1
0x15b4  ldloc.s  7
0x15b6  callvirt instance string [mscorlib]System.Object::ToString()
0x15bb  stelem.ref
0x15bc  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x15c1  leave.s  loc_15C3
0x15c3  ret
```
