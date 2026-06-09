# Microsoft.Crm.WebServices.PublishXmlService::Publish

- ea: `0xebc0`
- end: `0xec1d`
- name: `Microsoft.Crm.WebServices.PublishXmlService::Publish`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xebc0`
- `0xec20`
- `0xedb0`

## pseudocode

```c

```

## disassembly

```asm
0xebc0  ldarg.0
0xebc1  call     instance void Microsoft.Crm.WebServices.PublishXmlService::UpdatePublishCounter()
0xebc6  ldarg.0
0xebc7  ldarg.2
0xebc8  call     instance void Microsoft.Crm.WebServices.PublishXmlService::CheckPrivileges(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xebcd  ldarg.1
0xebce  brtrue.s loc_EBDB
0xebd0  ldstr    aEntities// "entities"
0xebd5  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xebda  throw
0xebdb  ldarg.2
0xebdc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0xebe1  call     int32 [Microsoft.Crm]Microsoft.Crm.Timeouts::GetNormalTimeoutInSeconds()
0xebe6  call     class [Microsoft.Crm.Core]Microsoft.Crm.AutoConnectionTimeoutContextModifier [Microsoft.Crm.Core]Microsoft.Crm.AutoConnectionTimeoutContextModifier::SetNewTimeoutIfLonger(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, int32)
0xebeb  stloc.0
0xebec  ldarg.2
0xebed  ldc.i4.1
0xebee  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransaction(bool)
0xebf3  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PublishXml::.ctor()
0xebf8  ldarg.1
0xebf9  ldarg.2
0xebfa  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PublishXml::Publish(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xebff  ldarg.2
0xec00  ldc.i4.0
0xec01  ldc.i4.1
0xec02  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CommitTransaction(valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ProcessDependenciesOption, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.FlushCacheOption)
0xec07  leave.s  loc_EC1C
0xec09  pop
0xec0a  ldarg.2
0xec0b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0xec10  rethrow
0xec12  ldloc.0
0xec13  brfalse.s loc_EC1B
0xec15  ldloc.0
0xec16  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xec1b  endfinally
0xec1c  ret
```
