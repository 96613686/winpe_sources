# Microsoft.Crm.Asynchronous.FlowNotificationService::LogServicePointCapacityStatus

- ea: `0x1710`
- end: `0x176e`
- name: `Microsoft.Crm.Asynchronous.FlowNotificationService::LogServicePointCapacityStatus`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1630`

## string_xrefs

- `0x171c`: `ServicePoint details for Url: {0} - maxConnectionLimit: {1}, maxIdleTime: {2} connectionLeaseTimeout: {3}, currentConnections: {4}`

## pseudocode

```c

```

## disassembly

```asm
0x1710  ldarg.1
0x1711  call     class [System]System.Net.ServicePoint [System]System.Net.ServicePointManager::FindServicePoint(class [System]System.Uri)
0x1716  stloc.0
0x1717  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.FlowNotificationService::Logger
0x171c  ldstr    aServicepointDe// "ServicePoint details for Url: {0} - max"...
0x1721  ldc.i4.5
0x1722  newarr   [mscorlib]System.Object
0x1727  dup
0x1728  ldc.i4.0
0x1729  ldarg.1
0x172a  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x172f  stelem.ref
0x1730  dup
0x1731  ldc.i4.1
0x1732  ldloc.0
0x1733  callvirt instance int32 [System]System.Net.ServicePoint::get_ConnectionLimit()
0x1738  box      [mscorlib]System.Int32
0x173d  stelem.ref
0x173e  dup
0x173f  ldc.i4.2
0x1740  ldloc.0
0x1741  callvirt instance int32 [System]System.Net.ServicePoint::get_MaxIdleTime()
0x1746  box      [mscorlib]System.Int32
0x174b  stelem.ref
0x174c  dup
0x174d  ldc.i4.3
0x174e  ldloc.0
0x174f  callvirt instance int32 [System]System.Net.ServicePoint::get_ConnectionLeaseTimeout()
0x1754  box      [mscorlib]System.Int32
0x1759  stelem.ref
0x175a  dup
0x175b  ldc.i4.4
0x175c  ldloc.0
0x175d  callvirt instance int32 [System]System.Net.ServicePoint::get_CurrentConnections()
0x1762  box      [mscorlib]System.Int32
0x1767  stelem.ref
0x1768  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x176d  ret
```
