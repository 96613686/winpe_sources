# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemDataSourcePromptsOperationCompleted

- ea: `0x60d0`
- end: `0x6109`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemDataSourcePromptsOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x60d0`
- `0xe7c0`
- `0xe800`

## pseudocode

```c

```

## disassembly

```asm
0x60d0  ldarg.0
0x60d1  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemDataSourcePromptsCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemDataSourcePromptsCompleted
0x60d6  brfalse.s loc_6108
0x60d8  ldarg.1
0x60d9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x60de  stloc.0
0x60df  ldarg.0
0x60e0  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemDataSourcePromptsCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemDataSourcePromptsCompleted
0x60e5  ldarg.0
0x60e6  ldloc.0
0x60e7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x60ec  ldloc.0
0x60ed  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x60f2  ldloc.0
0x60f3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x60f8  ldloc.0
0x60f9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x60fe  newobj   instance void Microsoft.Crm.ReportingServices2010.GetItemDataSourcePromptsCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x6103  callvirt instance void Microsoft.Crm.ReportingServices2010.GetItemDataSourcePromptsCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.GetItemDataSourcePromptsCompletedEventArgs e)
0x6108  ret
```
