# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCancelJobOperationCompleted

- ea: `0x9720`
- end: `0x9759`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCancelJobOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x9720`
- `0x106b0`
- `0x106f0`

## pseudocode

```c

```

## disassembly

```asm
0x9720  ldarg.0
0x9721  ldfld    class Microsoft.Crm.ReportingServices2010.CancelJobCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CancelJobCompleted
0x9726  brfalse.s loc_9758
0x9728  ldarg.1
0x9729  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x972e  stloc.0
0x972f  ldarg.0
0x9730  ldfld    class Microsoft.Crm.ReportingServices2010.CancelJobCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CancelJobCompleted
0x9735  ldarg.0
0x9736  ldloc.0
0x9737  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x973c  ldloc.0
0x973d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x9742  ldloc.0
0x9743  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x9748  ldloc.0
0x9749  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x974e  newobj   instance void Microsoft.Crm.ReportingServices2010.CancelJobCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x9753  callvirt instance void Microsoft.Crm.ReportingServices2010.CancelJobCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.CancelJobCompletedEventArgs e)
0x9758  ret
```
