# Microsoft.Crm.Workflow.ActivityHost::LogException

- ea: `0xb70`
- end: `0xb94`
- name: `Microsoft.Crm.Workflow.ActivityHost::LogException`
- size: `36`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x770`
- `0x910`
- `0xa50`

## pseudocode

```c

```

## disassembly

```asm
0xb70  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0xb75  ldarg.1
0xb76  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0xb7b  ldarg.2
0xb7c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0xb81  ldc.i4.s 0xA
0xb83  ldarg.1
0xb84  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OperationId()
0xb89  ldstr    aWorkflowcallba// "WorkflowCallBack"
0xb8e  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncOperationUnhandledException(valuetype [mscorlib]System.Guid, string, int32, valuetype [mscorlib]System.Guid, string)
0xb93  ret
```
