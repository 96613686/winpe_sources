# Microsoft.Crm.Asynchronous.EmailConnector.OperationFactories.MailboxOperationsFactory::ShouldScheduleTestOperations

- ea: `0x7a260`
- end: `0x7a2f0`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.OperationFactories.MailboxOperationsFactory::ShouldScheduleTestOperations`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7a220`

## callees

- `0x77a30`
- `0x77c40`
- `0x7a260`

## string_xrefs

- `0x7a263`: `postponetestemailconfigurationuntil`
- `0x7a274`: `testemailconfigurationscheduled`

## pseudocode

```c

```

## disassembly

```asm
0x7a260  ldc.i4.0
0x7a261  stloc.0
0x7a262  ldarg.1
0x7a263  ldstr    aPostponetestem// "postponetestemailconfigurationuntil"
0x7a268  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x7a26d  unbox.any [mscorlib]System.DateTime
0x7a272  stloc.1
0x7a273  ldarg.1
0x7a274  ldstr    aTestemailconfi_1// "testemailconfigurationscheduled"
0x7a279  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x7a27e  unbox.any [mscorlib]System.Boolean
0x7a283  brfalse.s loc_7A2EE
0x7a285  ldloc.1
0x7a286  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x7a28b  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x7a290  brfalse.s loc_7A2C5
0x7a292  ldc.i4.1
0x7a293  stloc.0
0x7a294  call     class Microsoft.Crm.Asynchronous.EmailConnector.ServerSideSyncTelemetryEventSource Microsoft.Crm.Asynchronous.EmailConnector.ServerSideSyncTelemetryEventSource::get_Instance()
0x7a299  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x7a29e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x7a2a3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7a2a8  ldarg.1
0x7a2a9  ldstr    aMailboxid// "mailboxid"
0x7a2ae  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x7a2b3  unbox.any [mscorlib]System.Guid
0x7a2b8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7a2bd  ldc.i4.2
0x7a2be  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ServerSideSyncTelemetryEventSource::TraceTestAndEnableProcess(valuetype [mscorlib]System.Guid scaleGroupId, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid mailboxId, valuetype [mscorlib]System.Guid asyncEventId, int32 testAndEnableState)
0x7a2c3  br.s     loc_7A2EE
0x7a2c5  ldloc.1
0x7a2c6  ldarg.1
0x7a2c7  ldstr    aPostponemailbo// "postponemailboxprocessinguntil"
0x7a2cc  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x7a2d1  unbox.any [mscorlib]System.DateTime
0x7a2d6  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x7a2db  brfalse.s loc_7A2EE
0x7a2dd  ldarg.1
0x7a2de  ldstr    aPostponemailbo// "postponemailboxprocessinguntil"
0x7a2e3  ldloc.1
0x7a2e4  box      [mscorlib]System.DateTime
0x7a2e9  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x7a2ee  ldloc.0
0x7a2ef  ret
```
