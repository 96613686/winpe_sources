# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemHistoryLimitOperationCompleted

- ea: `0x87a0`
- end: `0x87d9`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemHistoryLimitOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x87a0`
- `0xfcd0`
- `0xfd10`

## pseudocode

```c

```

## disassembly

```asm
0x87a0  ldarg.0
0x87a1  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemHistoryLimitCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemHistoryLimitCompleted
0x87a6  brfalse.s loc_87D8
0x87a8  ldarg.1
0x87a9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x87ae  stloc.0
0x87af  ldarg.0
0x87b0  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemHistoryLimitCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemHistoryLimitCompleted
0x87b5  ldarg.0
0x87b6  ldloc.0
0x87b7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x87bc  ldloc.0
0x87bd  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x87c2  ldloc.0
0x87c3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x87c8  ldloc.0
0x87c9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x87ce  newobj   instance void Microsoft.Crm.ReportingServices2010.GetItemHistoryLimitCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x87d3  callvirt instance void Microsoft.Crm.ReportingServices2010.GetItemHistoryLimitCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.GetItemHistoryLimitCompletedEventArgs e)
0x87d8  ret
```
