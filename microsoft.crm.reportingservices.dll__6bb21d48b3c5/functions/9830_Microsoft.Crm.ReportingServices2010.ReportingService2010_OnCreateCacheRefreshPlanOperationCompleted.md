# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateCacheRefreshPlanOperationCompleted

- ea: `0x9830`
- end: `0x9869`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateCacheRefreshPlanOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x9830`
- `0x10750`
- `0x10790`

## pseudocode

```c

```

## disassembly

```asm
0x9830  ldarg.0
0x9831  ldfld    class Microsoft.Crm.ReportingServices2010.CreateCacheRefreshPlanCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCacheRefreshPlanCompleted
0x9836  brfalse.s loc_9868
0x9838  ldarg.1
0x9839  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x983e  stloc.0
0x983f  ldarg.0
0x9840  ldfld    class Microsoft.Crm.ReportingServices2010.CreateCacheRefreshPlanCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCacheRefreshPlanCompleted
0x9845  ldarg.0
0x9846  ldloc.0
0x9847  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x984c  ldloc.0
0x984d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x9852  ldloc.0
0x9853  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x9858  ldloc.0
0x9859  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x985e  newobj   instance void Microsoft.Crm.ReportingServices2010.CreateCacheRefreshPlanCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x9863  callvirt instance void Microsoft.Crm.ReportingServices2010.CreateCacheRefreshPlanCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.CreateCacheRefreshPlanCompletedEventArgs e)
0x9868  ret
```
