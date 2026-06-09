# Microsoft.Crm.Sdk.InProcessCrmService::HandleException

- ea: `0x3130`
- end: `0x3162`
- name: `Microsoft.Crm.Sdk.InProcessCrmService::HandleException`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e20`

## callees

- `0x3130`
- `0x3170`

## pseudocode

```c

```

## disassembly

```asm
0x3130  ldarg.0
0x3131  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException [Microsoft.Crm.Core.WebServices]Microsoft.Crm.WebServices.PluginExecutionExceptionHandler::RetrieveInvalidPluginExecutionException(class [mscorlib]System.Exception)
0x3136  ldarg.0
0x3137  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException [Microsoft.Crm.Core.WebServices]Microsoft.Crm.WebServices.CrmExceptionHandler::RetrieveCrmException(class [mscorlib]System.Exception)
0x313c  stloc.0
0x313d  brtrue.s loc_3148
0x313f  ldloc.0
0x3140  brtrue.s loc_3148
0x3142  ldarg.0
0x3143  call     void Microsoft.Crm.Sdk.InProcessCrmService::ReportException(class [mscorlib]System.Exception e)
0x3148  ldarg.1
0x3149  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext::CleanupSoapAndSerializationContexts(class [Microsoft.Crm.Core]Microsoft.Crm.Performance.IWebServicePerformanceCounters)
0x314e  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_TracingOn()
0x3153  brfalse.s loc_3161
0x3155  call     class [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::get_Current()
0x315a  ldc.i4.0
0x315b  ldc.i4.0
0x315c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Performance.Instrumentation.PerformanceContext::OnEndRequest(bool, int32)
0x3161  ret
```
