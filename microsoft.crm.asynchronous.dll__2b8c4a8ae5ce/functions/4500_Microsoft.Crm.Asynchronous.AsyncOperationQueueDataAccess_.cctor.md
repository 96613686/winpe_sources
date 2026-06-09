# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::.cctor

- ea: `0x4500`
- end: `0x451a`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::.cctor`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x4500`: `AsyncService_app_lock`

## pseudocode

```c

```

## disassembly

```asm
0x4500  ldstr    aAsyncserviceAp// "AsyncService_app_lock"
0x4505  stsfld   string Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_asyncServiceAppLock
0x450a  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncXrmLogger [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncXrmLogger::get_Instance()
0x450f  callvirt instance class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncXrmLogger::get_Logger()
0x4514  stsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::Logger
0x4519  ret
```
