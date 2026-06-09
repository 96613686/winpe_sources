# Microsoft.Crm.Asynchronous.FlowNotificationService::Run

- ea: `0x1630`
- end: `0x1708`
- name: `Microsoft.Crm.Asynchronous.FlowNotificationService::Run`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e60`

## callees

- `0x1320`
- `0x1420`
- `0x1450`
- `0x1630`
- `0x1710`
- `0x1770`
- `0x1830`
- `0x1920`
- `0x1990`

## string_xrefs

- `0x16ef`: `Hit unknown exception during Flow notification send. Exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1630  ldnull
0x1631  stloc.0
0x1632  ldarg.0
0x1633  call     instance bool Microsoft.Crm.Asynchronous.FlowNotificationService::IsFlowNotificationFCBEnabled()
0x1638  brtrue.s loc_1671
0x163a  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.FlowNotificationService::Logger
0x163f  ldstr    aFlowNotificati// "Flow notifications are disabled for thi"...
0x1644  ldc.i4.1
0x1645  newarr   [mscorlib]System.Object
0x164a  dup
0x164b  ldc.i4.0
0x164c  ldarg.0
0x164d  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.FlowNotificationService::asyncEvent
0x1652  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RetryCount()
0x1657  box      [mscorlib]System.Int32
0x165c  stelem.ref
0x165d  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x1662  ldarg.0
0x1663  ldc.i4   0x80072342
0x1668  ldnull
0x1669  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.FlowNotificationService::GenerateAsyncHandlerRetryResult(int32 errorCode, string errorMessage)
0x166e  stloc.0
0x166f  br.s     loc_16E6
0x1671  ldarg.0
0x1672  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.Crm.Asynchronous.FlowNotificationService::GetTabularEntity()
0x1677  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0x167c  stloc.1
0x167d  newobj   instance void Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::.ctor()
0x1682  stloc.2
0x1683  ldloc.2
0x1684  ldstr    aFlownotificati// "FlowNotificationSettings"
0x1689  callvirt instance void Microsoft.Crm.Asynchronous.FlowHttpRequestConfig::UpdateWithDeploymentSettings(string deploymentSettingKey)
0x168e  ldarg.0
0x168f  ldfld    class [Microsoft.Crm]Microsoft.Crm.FlowNotificationOperationData Microsoft.Crm.Asynchronous.FlowNotificationService::asyncOperationData
0x1694  callvirt instance string [Microsoft.Crm]Microsoft.Crm.FlowNotificationOperationData::get_FlowNotificationUrl()
0x1699  newobj   instance void [System]System.Uri::.ctor(string)
0x169e  stloc.3
0x169f  ldsfld   class Microsoft.Crm.Asynchronous.WebApiClient Microsoft.Crm.Asynchronous.FlowNotificationService::webApiClient
0x16a4  ldloc.3
0x16a5  ldloc.2
0x16a6  ldloc.1
0x16a7  ldarg.0
0x16a8  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.FlowNotificationService::asyncEvent
0x16ad  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RequestId()
0x16b2  stloc.s  5
0x16b4  ldloca.s 5
0x16b6  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x16bc  callvirt instance string [mscorlib]System.Object::ToString()
0x16c1  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<valuetype [System]System.Net.HttpStatusCode> Microsoft.Crm.Asynchronous.WebApiClient::SendAsync(class [System]System.Uri url, class Microsoft.Crm.Asynchronous.FlowHttpRequestConfig httpConfig, string jsonPayload, string requestId)
0x16c6  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<valuetype [System]System.Net.HttpStatusCode>::get_Result()
0x16cb  stloc.s  4
0x16cd  ldloc.s  4
0x16cf  ldc.i4   0x198
0x16d4  bne.un.s loc_16DD
0x16d6  ldarg.0
0x16d7  ldloc.3
0x16d8  call     instance void Microsoft.Crm.Asynchronous.FlowNotificationService::LogServicePointCapacityStatus(class [System]System.Uri uri)
0x16dd  ldarg.0
0x16de  ldloc.s  4
0x16e0  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.FlowNotificationService::GenerateAsyncHandlerResultForHttpStatusCode(int32 httpStatusCode)
0x16e5  stloc.0
0x16e6  leave.s  loc_1706
0x16e8  stloc.s  6
0x16ea  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.FlowNotificationService::Logger
0x16ef  ldstr    aHitUnknownExce// "Hit unknown exception during Flow notif"...
0x16f4  ldc.i4.1
0x16f5  newarr   [mscorlib]System.Object
0x16fa  dup
0x16fb  ldc.i4.0
0x16fc  ldloc.s  6
0x16fe  stelem.ref
0x16ff  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x1704  rethrow
0x1706  ldloc.0
0x1707  ret
```
