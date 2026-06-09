# Microsoft.Crm.Asynchronous.ConfigurationFactory::Create

- ea: `0x1fc0`
- end: `0x200d`
- name: `Microsoft.Crm.Asynchronous.ConfigurationFactory::Create`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe20`

## callees

- `0xc40`
- `0x1fc0`
- `0x2010`

## string_xrefs

- `0x1fc1`: `service`
- `0x2002`: `service`
- `0x1ffd`: `Invalid context on the service`

## pseudocode

```c

```

## disassembly

```asm
0x1fc0  ldarg.0
0x1fc1  ldstr    aService// "service"
0x1fc6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1fcb  ldarg.1
0x1fcc  ldstr    aQueuestatistic// "queueStatisticsHelper"
0x1fd1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1fd6  ldarg.0
0x1fd7  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::get_Context()
0x1fdc  stloc.0
0x1fdd  ldloc.0
0x1fde  switch   loc_1FF5, loc_1FF5, loc_1FFD, loc_1FF5
0x1ff3  br.s     loc_1FFD
0x1ff5  ldarg.0
0x1ff6  ldarg.1
0x1ff7  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.ServerConfiguration Microsoft.Crm.Asynchronous.ConfigurationFactory::CreateConfigurationInternal(class Microsoft.Crm.Asynchronous.AsyncService service, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.QueueStatisticsHelper queueStatisticsHelper)
0x1ffc  ret
0x1ffd  ldstr    aInvalidContext// "Invalid context on the service"
0x2002  ldstr    aService// "service"
0x2007  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x200c  throw
```
