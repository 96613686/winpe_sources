# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemLinkOperationCompleted

- ea: `0x7cf0`
- end: `0x7d29`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemLinkOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x7cf0`
- `0xf770`
- `0xf7b0`

## pseudocode

```c

```

## disassembly

```asm
0x7cf0  ldarg.0
0x7cf1  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemLinkCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemLinkCompleted
0x7cf6  brfalse.s loc_7D28
0x7cf8  ldarg.1
0x7cf9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x7cfe  stloc.0
0x7cff  ldarg.0
0x7d00  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemLinkCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemLinkCompleted
0x7d05  ldarg.0
0x7d06  ldloc.0
0x7d07  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x7d0c  ldloc.0
0x7d0d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x7d12  ldloc.0
0x7d13  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x7d18  ldloc.0
0x7d19  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x7d1e  newobj   instance void Microsoft.Crm.ReportingServices2010.GetItemLinkCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x7d23  callvirt instance void Microsoft.Crm.ReportingServices2010.GetItemLinkCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.GetItemLinkCompletedEventArgs e)
0x7d28  ret
```
