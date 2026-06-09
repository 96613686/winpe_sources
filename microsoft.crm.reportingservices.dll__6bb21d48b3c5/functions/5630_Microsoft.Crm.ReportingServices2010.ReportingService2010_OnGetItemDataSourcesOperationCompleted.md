# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemDataSourcesOperationCompleted

- ea: `0x5630`
- end: `0x5669`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemDataSourcesOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x5630`
- `0xe1a0`
- `0xe1e0`

## pseudocode

```c

```

## disassembly

```asm
0x5630  ldarg.0
0x5631  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemDataSourcesCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemDataSourcesCompleted
0x5636  brfalse.s loc_5668
0x5638  ldarg.1
0x5639  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x563e  stloc.0
0x563f  ldarg.0
0x5640  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemDataSourcesCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemDataSourcesCompleted
0x5645  ldarg.0
0x5646  ldloc.0
0x5647  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x564c  ldloc.0
0x564d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x5652  ldloc.0
0x5653  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x5658  ldloc.0
0x5659  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x565e  newobj   instance void Microsoft.Crm.ReportingServices2010.GetItemDataSourcesCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x5663  callvirt instance void Microsoft.Crm.ReportingServices2010.GetItemDataSourcesCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.GetItemDataSourcesCompletedEventArgs e)
0x5668  ret
```
