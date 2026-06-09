# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateScheduleOperationCompleted

- ea: `0x6e20`
- end: `0x6e59`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateScheduleOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x6e20`
- `0xef80`
- `0xefc0`

## pseudocode

```c

```

## disassembly

```asm
0x6e20  ldarg.0
0x6e21  ldfld    class Microsoft.Crm.ReportingServices2010.CreateScheduleCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateScheduleCompleted
0x6e26  brfalse.s loc_6E58
0x6e28  ldarg.1
0x6e29  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x6e2e  stloc.0
0x6e2f  ldarg.0
0x6e30  ldfld    class Microsoft.Crm.ReportingServices2010.CreateScheduleCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateScheduleCompleted
0x6e35  ldarg.0
0x6e36  ldloc.0
0x6e37  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x6e3c  ldloc.0
0x6e3d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x6e42  ldloc.0
0x6e43  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x6e48  ldloc.0
0x6e49  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x6e4e  newobj   instance void Microsoft.Crm.ReportingServices2010.CreateScheduleCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x6e53  callvirt instance void Microsoft.Crm.ReportingServices2010.CreateScheduleCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.CreateScheduleCompletedEventArgs e)
0x6e58  ret
```
