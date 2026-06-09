# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetCacheOptionsOperationCompleted

- ea: `0x82b0`
- end: `0x82e9`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetCacheOptionsOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x82b0`
- `0xfa60`
- `0xfaa0`

## pseudocode

```c

```

## disassembly

```asm
0x82b0  ldarg.0
0x82b1  ldfld    class Microsoft.Crm.ReportingServices2010.GetCacheOptionsCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheOptionsCompleted
0x82b6  brfalse.s loc_82E8
0x82b8  ldarg.1
0x82b9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x82be  stloc.0
0x82bf  ldarg.0
0x82c0  ldfld    class Microsoft.Crm.ReportingServices2010.GetCacheOptionsCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheOptionsCompleted
0x82c5  ldarg.0
0x82c6  ldloc.0
0x82c7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x82cc  ldloc.0
0x82cd  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x82d2  ldloc.0
0x82d3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x82d8  ldloc.0
0x82d9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x82de  newobj   instance void Microsoft.Crm.ReportingServices2010.GetCacheOptionsCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x82e3  callvirt instance void Microsoft.Crm.ReportingServices2010.GetCacheOptionsCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.GetCacheOptionsCompletedEventArgs e)
0x82e8  ret
```
