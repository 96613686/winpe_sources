# Microsoft.Crm.WebServices.LangProvisioningService::ProvisionLanguage

- ea: `0xe7b0`
- end: `0xe7e5`
- name: `Microsoft.Crm.WebServices.LangProvisioningService::ProvisionLanguage`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xe7b0`
- `0xe870`
- `0xe8a0`

## pseudocode

```c

```

## disassembly

```asm
0xe7b0  ldarg.0
0xe7b1  ldarg.2
0xe7b2  call     instance void Microsoft.Crm.WebServices.LangProvisioningService::CheckPrivileges(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xe7b7  ldarg.2
0xe7b8  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe7bd  ldarg.1
0xe7be  callvirt instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProvisionLanguage(int32)
0xe7c3  leave.s  loc_E7E4
0xe7c5  stloc.0
0xe7c6  ldarg.0
0xe7c7  ldc.i4.1
0xe7c8  ldc.i4   0xC0004C02
0xe7cd  conv.u8
0xe7ce  ldc.i4.1
0xe7cf  newarr   [mscorlib]System.Object
0xe7d4  dup
0xe7d5  ldc.i4.0
0xe7d6  ldloc.0
0xe7d7  callvirt instance string [mscorlib]System.Exception::get_Message()
0xe7dc  stelem.ref
0xe7dd  call     instance void Microsoft.Crm.WebServices.LangProvisioningService::WriteSystemEventLog(valuetype [System]System.Diagnostics.EventLogEntryType eventLogEntryType, int64 crmEventLogId, object[] arguments)
0xe7e2  rethrow
0xe7e4  ret
```
