# Microsoft.Crm.WebServices.PublishXmlService::PublishAll

- ea: `0xeb70`
- end: `0xebbc`
- name: `Microsoft.Crm.WebServices.PublishXmlService::PublishAll`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xeb70`
- `0xec20`
- `0xedb0`

## pseudocode

```c

```

## disassembly

```asm
0xeb70  ldarg.0
0xeb71  call     instance void Microsoft.Crm.WebServices.PublishXmlService::UpdatePublishCounter()
0xeb76  ldarg.0
0xeb77  ldarg.1
0xeb78  call     instance void Microsoft.Crm.WebServices.PublishXmlService::CheckPrivileges(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xeb7d  ldarg.1
0xeb7e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0xeb83  call     int32 [Microsoft.Crm]Microsoft.Crm.Timeouts::GetNormalTimeoutInSeconds()
0xeb88  call     class [Microsoft.Crm.Core]Microsoft.Crm.AutoConnectionTimeoutContextModifier [Microsoft.Crm.Core]Microsoft.Crm.AutoConnectionTimeoutContextModifier::SetNewTimeoutIfLonger(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, int32)
0xeb8d  stloc.0
0xeb8e  ldarg.1
0xeb8f  ldc.i4.1
0xeb90  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransaction(bool)
0xeb95  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PublishXml::.ctor()
0xeb9a  ldarg.1
0xeb9b  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PublishXml::PublishAll(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xeba0  ldarg.1
0xeba1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction()
0xeba6  leave.s  loc_EBBB
0xeba8  pop
0xeba9  ldarg.1
0xebaa  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0xebaf  rethrow
0xebb1  ldloc.0
0xebb2  brfalse.s loc_EBBA
0xebb4  ldloc.0
0xebb5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xebba  endfinally
0xebbb  ret
```
