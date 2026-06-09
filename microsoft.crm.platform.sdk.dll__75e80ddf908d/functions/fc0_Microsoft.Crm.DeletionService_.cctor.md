# Microsoft.Crm.DeletionService::.cctor

- ea: `0xfc0`
- end: `0x103d`
- name: `Microsoft.Crm.DeletionService::.cctor`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0xfc5`: `NumOfRecordsToBeDeletedPerExecution`
- `0xfde`: `DeletionServiceExecutionTimeoutInMinutes`
- `0xff4`: `DeletionServiceDBConnectionTimeoutInSeconds`

## pseudocode

```c

```

## disassembly

```asm
0xfc0  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xfc5  ldstr    aNumofrecordsto_0// "NumOfRecordsToBeDeletedPerExecution"
0xfca  ldc.i4   0x1324
0xfcf  callvirt T0x2B000001
0xfd4  stsfld   int32 Microsoft.Crm.DeletionService::NumOfRecordsToBeDeletedPerExecution
0xfd9  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xfde  ldstr    aDeletionservic_13// "DeletionServiceExecutionTimeoutInMinute"...
0xfe3  ldc.i4.s 0x78
0xfe5  callvirt T0x2B000001
0xfea  stsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceExecutionTimeoutInMinutes
0xfef  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xff4  ldstr    aDeletionservic_14// "DeletionServiceDBConnectionTimeoutInSec"...
0xff9  ldc.i4   0x12C
0xffe  callvirt T0x2B000001
0x1003  stsfld   int32 Microsoft.Crm.DeletionService::DeletionServiceDBConnectionTimeoutInSeconds
0x1008  call     class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmLoggerFactory::get_LoggerFactory()
0x100d  ldtoken  Microsoft.Crm.DeletionService
0x1012  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1017  callvirt instance string [mscorlib]System.Type::get_FullName()
0x101c  callvirt instance class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory::CreateLogger(string)
0x1021  stsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.DeletionService::Logger
0x1026  ldstr    aPGettablesford// "p_GetTablesForDeletion"
0x102b  stsfld   string Microsoft.Crm.DeletionService::getTablesForDeletionProcedure
0x1030  ldnull
0x1031  stsfld   class [System]System.Threading.Semaphore Microsoft.Crm.DeletionService::poolTask
0x1036  ldc.i4.0
0x1037  stsfld   bool Microsoft.Crm.DeletionService::AllowVerboseLogging
0x103c  ret
```
