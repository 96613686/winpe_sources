# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetCacheRefreshPlanPropertiesOperationCompleted

- ea: `0x9aa0`
- end: `0x9ad9`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetCacheRefreshPlanPropertiesOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x9aa0`
- `0x10840`
- `0x10880`

## pseudocode

```c

```

## disassembly

```asm
0x9aa0  ldarg.0
0x9aa1  ldfld    class Microsoft.Crm.ReportingServices2010.GetCacheRefreshPlanPropertiesCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheRefreshPlanPropertiesCompleted
0x9aa6  brfalse.s loc_9AD8
0x9aa8  ldarg.1
0x9aa9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x9aae  stloc.0
0x9aaf  ldarg.0
0x9ab0  ldfld    class Microsoft.Crm.ReportingServices2010.GetCacheRefreshPlanPropertiesCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheRefreshPlanPropertiesCompleted
0x9ab5  ldarg.0
0x9ab6  ldloc.0
0x9ab7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x9abc  ldloc.0
0x9abd  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x9ac2  ldloc.0
0x9ac3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x9ac8  ldloc.0
0x9ac9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x9ace  newobj   instance void Microsoft.Crm.ReportingServices2010.GetCacheRefreshPlanPropertiesCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x9ad3  callvirt instance void Microsoft.Crm.ReportingServices2010.GetCacheRefreshPlanPropertiesCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.GetCacheRefreshPlanPropertiesCompletedEventArgs e)
0x9ad8  ret
```
