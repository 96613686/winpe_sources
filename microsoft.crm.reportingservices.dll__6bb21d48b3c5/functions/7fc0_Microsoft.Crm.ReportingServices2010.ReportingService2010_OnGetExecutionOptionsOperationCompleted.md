# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetExecutionOptionsOperationCompleted

- ea: `0x7fc0`
- end: `0x7ff9`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetExecutionOptionsOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x7fc0`
- `0xf900`
- `0xf940`

## pseudocode

```c

```

## disassembly

```asm
0x7fc0  ldarg.0
0x7fc1  ldfld    class Microsoft.Crm.ReportingServices2010.GetExecutionOptionsCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetExecutionOptionsCompleted
0x7fc6  brfalse.s loc_7FF8
0x7fc8  ldarg.1
0x7fc9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x7fce  stloc.0
0x7fcf  ldarg.0
0x7fd0  ldfld    class Microsoft.Crm.ReportingServices2010.GetExecutionOptionsCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetExecutionOptionsCompleted
0x7fd5  ldarg.0
0x7fd6  ldloc.0
0x7fd7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x7fdc  ldloc.0
0x7fdd  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x7fe2  ldloc.0
0x7fe3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x7fe8  ldloc.0
0x7fe9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x7fee  newobj   instance void Microsoft.Crm.ReportingServices2010.GetExecutionOptionsCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x7ff3  callvirt instance void Microsoft.Crm.ReportingServices2010.GetExecutionOptionsCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.GetExecutionOptionsCompletedEventArgs e)
0x7ff8  ret
```
