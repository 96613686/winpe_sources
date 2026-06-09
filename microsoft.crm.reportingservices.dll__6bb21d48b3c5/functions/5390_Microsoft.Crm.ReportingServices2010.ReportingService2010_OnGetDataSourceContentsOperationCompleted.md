# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetDataSourceContentsOperationCompleted

- ea: `0x5390`
- end: `0x53c9`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetDataSourceContentsOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x5390`
- `0xe010`
- `0xe050`

## pseudocode

```c

```

## disassembly

```asm
0x5390  ldarg.0
0x5391  ldfld    class Microsoft.Crm.ReportingServices2010.GetDataSourceContentsCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetDataSourceContentsCompleted
0x5396  brfalse.s loc_53C8
0x5398  ldarg.1
0x5399  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x539e  stloc.0
0x539f  ldarg.0
0x53a0  ldfld    class Microsoft.Crm.ReportingServices2010.GetDataSourceContentsCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetDataSourceContentsCompleted
0x53a5  ldarg.0
0x53a6  ldloc.0
0x53a7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x53ac  ldloc.0
0x53ad  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x53b2  ldloc.0
0x53b3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x53b8  ldloc.0
0x53b9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x53be  newobj   instance void Microsoft.Crm.ReportingServices2010.GetDataSourceContentsCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x53c3  callvirt instance void Microsoft.Crm.ReportingServices2010.GetDataSourceContentsCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.GetDataSourceContentsCompletedEventArgs e)
0x53c8  ret
```
