# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateReportEditSessionOperationCompleted

- ea: `0x7a20`
- end: `0x7a59`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateReportEditSessionOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x7a20`
- `0xf610`
- `0xf650`

## pseudocode

```c

```

## disassembly

```asm
0x7a20  ldarg.0
0x7a21  ldfld    class Microsoft.Crm.ReportingServices2010.CreateReportEditSessionCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateReportEditSessionCompleted
0x7a26  brfalse.s loc_7A58
0x7a28  ldarg.1
0x7a29  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x7a2e  stloc.0
0x7a2f  ldarg.0
0x7a30  ldfld    class Microsoft.Crm.ReportingServices2010.CreateReportEditSessionCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateReportEditSessionCompleted
0x7a35  ldarg.0
0x7a36  ldloc.0
0x7a37  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x7a3c  ldloc.0
0x7a3d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x7a42  ldloc.0
0x7a43  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x7a48  ldloc.0
0x7a49  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x7a4e  newobj   instance void Microsoft.Crm.ReportingServices2010.CreateReportEditSessionCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x7a53  callvirt instance void Microsoft.Crm.ReportingServices2010.CreateReportEditSessionCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.CreateReportEditSessionCompletedEventArgs e)
0x7a58  ret
```
