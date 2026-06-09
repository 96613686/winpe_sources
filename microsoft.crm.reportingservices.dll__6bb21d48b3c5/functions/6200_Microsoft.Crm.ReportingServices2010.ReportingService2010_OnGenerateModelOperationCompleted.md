# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGenerateModelOperationCompleted

- ea: `0x6200`
- end: `0x6239`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGenerateModelOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x6200`
- `0xe860`
- `0xe8a0`

## pseudocode

```c

```

## disassembly

```asm
0x6200  ldarg.0
0x6201  ldfld    class Microsoft.Crm.ReportingServices2010.GenerateModelCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GenerateModelCompleted
0x6206  brfalse.s loc_6238
0x6208  ldarg.1
0x6209  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x620e  stloc.0
0x620f  ldarg.0
0x6210  ldfld    class Microsoft.Crm.ReportingServices2010.GenerateModelCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GenerateModelCompleted
0x6215  ldarg.0
0x6216  ldloc.0
0x6217  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x621c  ldloc.0
0x621d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x6222  ldloc.0
0x6223  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x6228  ldloc.0
0x6229  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x622e  newobj   instance void Microsoft.Crm.ReportingServices2010.GenerateModelCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x6233  callvirt instance void Microsoft.Crm.ReportingServices2010.GenerateModelCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.GenerateModelCompletedEventArgs e)
0x6238  ret
```
