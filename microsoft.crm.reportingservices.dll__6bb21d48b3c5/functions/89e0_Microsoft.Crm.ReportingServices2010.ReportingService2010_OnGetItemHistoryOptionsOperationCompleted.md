# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemHistoryOptionsOperationCompleted

- ea: `0x89e0`
- end: `0x8a19`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemHistoryOptionsOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x89e0`
- `0xfe00`
- `0xfe40`

## pseudocode

```c

```

## disassembly

```asm
0x89e0  ldarg.0
0x89e1  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemHistoryOptionsCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemHistoryOptionsCompleted
0x89e6  brfalse.s loc_8A18
0x89e8  ldarg.1
0x89e9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x89ee  stloc.0
0x89ef  ldarg.0
0x89f0  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemHistoryOptionsCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemHistoryOptionsCompleted
0x89f5  ldarg.0
0x89f6  ldloc.0
0x89f7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x89fc  ldloc.0
0x89fd  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x8a02  ldloc.0
0x8a03  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x8a08  ldloc.0
0x8a09  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x8a0e  newobj   instance void Microsoft.Crm.ReportingServices2010.GetItemHistoryOptionsCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x8a13  callvirt instance void Microsoft.Crm.ReportingServices2010.GetItemHistoryOptionsCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.GetItemHistoryOptionsCompletedEventArgs e)
0x8a18  ret
```
