# Microsoft.Crm.Sandbox.SandboxHostManager::RetrieveReadyClientInternal

- ea: `0x12c0`
- end: `0x1467`
- name: `Microsoft.Crm.Sandbox.SandboxHostManager::RetrieveReadyClientInternal`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1230`

## callees

- `0x560`
- `0x1160`
- `0x12c0`

## string_xrefs

- `0x12dc`: `SandboxHostManager.RetrieveReadyClientInternal: no ready clients`
- `0x1319`: `readyClients`
- `0x133b`: `_readyClients.Count`
- `0x13d8`: `_readyClients.Count`
- `0x1362`: `clientIndex >= _readyClients.Count`
- `0x13f8`: `clientIndex >= _readyClients.Count`
- `0x1379`: `SandboxHostManager.RetrieveReadyClientInternal: clientIndex: {0}`
- `0x13a0`: `readyClient`
- `0x13b8`: `SandboxHostManager.RetrieveReadyClientInternal: found ready client`
- `0x141d`: `SandboxHostManager.RetrieveReadyClientInternal: no clients are ready`
- `0x1449`: `SandboxHostManager.RetrieveReadyClientInternal: out: _nextClientIndex: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x12c0  ldnull
0x12c1  stloc.0
0x12c2  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxHostManager::_listsLock
0x12c7  ldc.i4.0
0x12c8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x12cd  stloc.1
0x12ce  ldarg.1
0x12cf  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::get_Count()
0x12d4  ldc.i4.0
0x12d5  bgt.s    loc_12F8
0x12d7  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHostManager::Logger
0x12dc  ldstr    aSandboxhostman_31// "SandboxHostManager.RetrieveReadyClientI"...
0x12e1  ldc.i4.0
0x12e2  newarr   [mscorlib]System.Object
0x12e7  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x12ec  ldarg.0
0x12ed  call     class Microsoft.Crm.Sandbox.SandboxClient Microsoft.Crm.Sandbox.SandboxHostManager::GetNewClient(bool useDrawBridgeIsolation)
0x12f2  stloc.3
0x12f3  leave    loc_1465
0x12f8  ldstr    aUsedrawbridgei// "useDrawBridgeIsolation"
0x12fd  ldarga.s 0
0x12ff  call     instance string [mscorlib]System.Boolean::ToString()
0x1304  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x1309  ldstr    aNextclientinde// "nextClientIndex"
0x130e  ldarg.2
0x130f  call     instance string [mscorlib]System.Int32::ToString()
0x1314  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x1319  ldstr    aReadyclients// "readyClients"
0x131e  ldarg.1
0x131f  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::get_Count()
0x1324  stloc.s  4
0x1326  ldloca.s 4
0x1328  call     instance string [mscorlib]System.Int32::ToString()
0x132d  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x1332  ldarg.1
0x1333  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::get_Count()
0x1338  ldc.i4.0
0x1339  cgt
0x133b  ldstr    aReadyclientsCo// "_readyClients.Count"
0x1340  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1345  ldarg.2
0x1346  ldarg.2
0x1347  ldind.i4
0x1348  ldc.i4.1
0x1349  add
0x134a  stloc.s  4
0x134c  ldloc.s  4
0x134e  stind.i4
0x134f  ldloc.s  4
0x1351  ldarg.1
0x1352  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::get_Count()
0x1357  rem
0x1358  stloc.2
0x1359  ldloc.2
0x135a  ldarg.1
0x135b  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::get_Count()
0x1360  clt
0x1362  ldstr    aClientindexRea// "clientIndex >= _readyClients.Count"
0x1367  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x136c  ldc.i4.0
0x136d  stloc.s  5
0x136f  br       loc_1408
0x1374  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHostManager::Logger
0x1379  ldstr    aSandboxhostman_32// "SandboxHostManager.RetrieveReadyClientI"...
0x137e  ldc.i4.1
0x137f  newarr   [mscorlib]System.Object
0x1384  dup
0x1385  ldc.i4.0
0x1386  ldloc.2
0x1387  box      [mscorlib]System.Int32
0x138c  stelem.ref
0x138d  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x1392  ldarg.1
0x1393  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::get_Values()
0x1398  ldloc.2
0x1399  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Sandbox.SandboxClient>::get_Item(!!T0)
0x139e  stloc.0
0x139f  ldloc.0
0x13a0  ldstr    aReadyclient// "readyClient"
0x13a5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x13aa  ldloc.0
0x13ab  callvirt instance valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxClient::get_HostStatus()
0x13b0  ldc.i4.3
0x13b1  bne.un.s loc_13CD
0x13b3  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHostManager::Logger
0x13b8  ldstr    aSandboxhostman_33// "SandboxHostManager.RetrieveReadyClientI"...
0x13bd  ldc.i4.0
0x13be  newarr   [mscorlib]System.Object
0x13c3  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x13c8  ldarg.2
0x13c9  ldloc.2
0x13ca  stind.i4
0x13cb  br.s     loc_1415
0x13cd  ldnull
0x13ce  stloc.0
0x13cf  ldarg.1
0x13d0  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::get_Count()
0x13d5  ldc.i4.0
0x13d6  cgt
0x13d8  ldstr    aReadyclientsCo// "_readyClients.Count"
0x13dd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x13e2  ldloc.2
0x13e3  ldc.i4.1
0x13e4  add
0x13e5  dup
0x13e6  stloc.2
0x13e7  ldarg.1
0x13e8  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::get_Count()
0x13ed  rem
0x13ee  stloc.2
0x13ef  ldloc.2
0x13f0  ldarg.1
0x13f1  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::get_Count()
0x13f6  clt
0x13f8  ldstr    aClientindexRea// "clientIndex >= _readyClients.Count"
0x13fd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1402  ldloc.s  5
0x1404  ldc.i4.1
0x1405  add
0x1406  stloc.s  5
0x1408  ldloc.s  5
0x140a  ldarg.1
0x140b  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::get_Count()
0x1410  blt      loc_1374
0x1415  ldloc.0
0x1416  brtrue.s loc_1436
0x1418  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHostManager::Logger
0x141d  ldstr    aSandboxhostman_34// "SandboxHostManager.RetrieveReadyClientI"...
0x1422  ldc.i4.0
0x1423  newarr   [mscorlib]System.Object
0x1428  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x142d  ldarg.0
0x142e  call     class Microsoft.Crm.Sandbox.SandboxClient Microsoft.Crm.Sandbox.SandboxHostManager::GetNewClient(bool useDrawBridgeIsolation)
0x1433  stloc.3
0x1434  leave.s  loc_1465
0x1436  leave.s  loc_1442
0x1438  ldloc.1
0x1439  brfalse.s loc_1441
0x143b  ldloc.1
0x143c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1441  endfinally
0x1442  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1447  ldc.i4.s 0x23
0x1449  ldstr    aSandboxhostman_35// "SandboxHostManager.RetrieveReadyClientI"...
0x144e  ldc.i4.1
0x144f  newarr   [mscorlib]System.Object
0x1454  dup
0x1455  ldc.i4.0
0x1456  ldarg.2
0x1457  ldind.i4
0x1458  box      [mscorlib]System.Int32
0x145d  stelem.ref
0x145e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1463  ldloc.0
0x1464  ret
0x1465  ldloc.3
0x1466  ret
```
