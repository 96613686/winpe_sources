# Microsoft.Crm.Asynchronous.FlowNotificationService::GenerateAsyncHandlerResultForHttpStatusCode

- ea: `0x1830`
- end: `0x18eb`
- name: `Microsoft.Crm.Asynchronous.FlowNotificationService::GenerateAsyncHandlerResultForHttpStatusCode`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1630`

## callees

- `0x1770`
- `0x1830`
- `0x1970`

## string_xrefs

- `0x186d`: `Non Success http status code during Flow notification send - {0}, RetryCount: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1830  ldnull
0x1831  stloc.0
0x1832  ldarg.1
0x1833  call     bool Microsoft.Crm.Asynchronous.FlowNotificationService::IsSuccessHttpStatusCode(int32 statusCode)
0x1838  brfalse.s loc_1868
0x183a  ldstr    aSuccessfullySe// "Successfully sent flow notification wit"...
0x183f  ldarg.1
0x1840  box      [mscorlib]System.Int32
0x1845  call     string [mscorlib]System.String::Concat(object, object)
0x184a  stloc.1
0x184b  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.FlowNotificationService::Logger
0x1850  ldloc.1
0x1851  ldc.i4.0
0x1852  newarr   [mscorlib]System.Object
0x1857  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x185c  ldloc.1
0x185d  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor(string)
0x1862  stloc.0
0x1863  br       loc_18E9
0x1868  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.FlowNotificationService::Logger
0x186d  ldstr    aNonSuccessHttp// "Non Success http status code during Flo"...
0x1872  ldc.i4.2
0x1873  newarr   [mscorlib]System.Object
0x1878  dup
0x1879  ldc.i4.0
0x187a  ldarg.1
0x187b  box      [mscorlib]System.Int32
0x1880  stelem.ref
0x1881  dup
0x1882  ldc.i4.1
0x1883  ldarg.0
0x1884  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.FlowNotificationService::asyncEvent
0x1889  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RetryCount()
0x188e  box      [mscorlib]System.Int32
0x1893  stelem.ref
0x1894  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x1899  ldstr    aFailedWithNonS// "Failed with non-success Http response s"...
0x189e  ldarg.1
0x189f  box      [mscorlib]System.Int32
0x18a4  call     string [mscorlib]System.String::Concat(object, object)
0x18a9  stloc.2
0x18aa  ldc.i4   0x80072341
0x18af  stloc.3
0x18b0  ldarg.1
0x18b1  ldc.i4   0x198
0x18b6  beq.s    loc_18D0
0x18b8  ldarg.1
0x18b9  ldc.i4   0x1AD
0x18be  beq.s    loc_18D0
0x18c0  ldarg.1
0x18c1  ldc.i4   0x1F4
0x18c6  blt.s    loc_18DB
0x18c8  ldarg.1
0x18c9  ldc.i4   0x258
0x18ce  bge.s    loc_18DB
0x18d0  ldarg.0
0x18d1  ldloc.3
0x18d2  ldloc.2
0x18d3  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.FlowNotificationService::GenerateAsyncHandlerRetryResult(int32 errorCode, string errorMessage)
0x18d8  stloc.0
0x18d9  br.s     loc_18E9
0x18db  ldloc.3
0x18dc  ldloc.2
0x18dd  ldc.i4.0
0x18de  newarr   [mscorlib]System.Object
0x18e3  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(int32, string, object[])
0x18e8  stloc.0
0x18e9  ldloc.0
0x18ea  ret
```
