# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateDataSourceOperationCompleted

- ea: `0x4ef0`
- end: `0x4f29`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateDataSourceOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x4ef0`
- `0xdda0`
- `0xdde0`

## pseudocode

```c

```

## disassembly

```asm
0x4ef0  ldarg.0
0x4ef1  ldfld    class Microsoft.Crm.ReportingServices2010.CreateDataSourceCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataSourceCompleted
0x4ef6  brfalse.s loc_4F28
0x4ef8  ldarg.1
0x4ef9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x4efe  stloc.0
0x4eff  ldarg.0
0x4f00  ldfld    class Microsoft.Crm.ReportingServices2010.CreateDataSourceCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataSourceCompleted
0x4f05  ldarg.0
0x4f06  ldloc.0
0x4f07  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x4f0c  ldloc.0
0x4f0d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x4f12  ldloc.0
0x4f13  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x4f18  ldloc.0
0x4f19  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x4f1e  newobj   instance void Microsoft.Crm.ReportingServices2010.CreateDataSourceCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x4f23  callvirt instance void Microsoft.Crm.ReportingServices2010.CreateDataSourceCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.CreateDataSourceCompletedEventArgs e)
0x4f28  ret
```
