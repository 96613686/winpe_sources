# Microsoft.Crm.Asynchronous.FlowNotificationService::GenerateAsyncHandlerRetryResult

- ea: `0x1770`
- end: `0x1823`
- name: `Microsoft.Crm.Asynchronous.FlowNotificationService::GenerateAsyncHandlerRetryResult`
- size: `179`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1630`
- `0x1830`

## callees

- `0x1770`
- `0x18f0`

## string_xrefs

- `0x1781`: `Maximum Async operation retries completed. {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1770  ldnull
0x1771  stloc.0
0x1772  ldarg.0
0x1773  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.FlowNotificationService::asyncEvent
0x1778  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RetryCount()
0x177d  ldc.i4.s 0xC
0x177f  ble.s    loc_17C2
0x1781  ldstr    aMaximumAsyncOp// "Maximum Async operation retries complet"...
0x1786  ldarg.2
0x1787  brfalse.s loc_1796
0x1789  ldstr    aErrormessage// "ErrorMessage: "
0x178e  ldarg.2
0x178f  call     string [mscorlib]System.String::Concat(string, string)
0x1794  br.s     loc_179B
0x1796  ldsfld   string [mscorlib]System.String::Empty
0x179b  call     string [mscorlib]System.String::Format(string, object)
0x17a0  stloc.1
0x17a1  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.FlowNotificationService::Logger
0x17a6  ldloc.1
0x17a7  ldc.i4.0
0x17a8  newarr   [mscorlib]System.Object
0x17ad  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x17b2  ldarg.1
0x17b3  ldloc.1
0x17b4  ldc.i4.0
0x17b5  newarr   [mscorlib]System.Object
0x17ba  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(int32, string, object[])
0x17bf  stloc.0
0x17c0  br.s     loc_1810
0x17c2  ldarg.2
0x17c3  brfalse.s loc_17CF
0x17c5  ldc.i4.1
0x17c6  ldarg.1
0x17c7  ldarg.2
0x17c8  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorAction::.ctor(valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorActionType, int32, string)
0x17cd  br.s     loc_17D6
0x17cf  ldc.i4.1
0x17d0  ldarg.1
0x17d1  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorAction::.ctor(valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorActionType, int32)
0x17d6  ldarg.0
0x17d7  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.FlowNotificationService::asyncEvent
0x17dc  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RetryCount()
0x17e1  call     valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.FlowNotificationService::GetPostponeUntilTime(int32 retryCount)
0x17e6  stloc.2
0x17e7  ldstr    aGoingToPostpon// "Going to postpone async operation. Curr"...
0x17ec  ldarg.0
0x17ed  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.FlowNotificationService::asyncEvent
0x17f2  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RetryCount()
0x17f7  box      [mscorlib]System.Int32
0x17fc  ldarg.2
0x17fd  ldloc.2
0x17fe  box      [mscorlib]System.DateTime
0x1803  call     string [mscorlib]System.String::Format(string, object, object, object)
0x1808  stloc.1
0x1809  ldloc.2
0x180a  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRetryResultWithPostponeUntil::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorAction, valuetype [mscorlib]System.DateTime)
0x180f  stloc.0
0x1810  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.FlowNotificationService::Logger
0x1815  ldloc.1
0x1816  ldc.i4.0
0x1817  newarr   [mscorlib]System.Object
0x181c  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x1821  ldloc.0
0x1822  ret
```
