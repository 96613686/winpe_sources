# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetDataDrivenSubscriptionPropertiesOperationCompleted

- ea: `0x44f0`
- end: `0x4529`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetDataDrivenSubscriptionPropertiesOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x44f0`
- `0xd700`
- `0xd740`

## pseudocode

```c

```

## disassembly

```asm
0x44f0  ldarg.0
0x44f1  ldfld    class Microsoft.Crm.ReportingServices2010.GetDataDrivenSubscriptionPropertiesCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetDataDrivenSubscriptionPropertiesCompleted
0x44f6  brfalse.s loc_4528
0x44f8  ldarg.1
0x44f9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x44fe  stloc.0
0x44ff  ldarg.0
0x4500  ldfld    class Microsoft.Crm.ReportingServices2010.GetDataDrivenSubscriptionPropertiesCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetDataDrivenSubscriptionPropertiesCompleted
0x4505  ldarg.0
0x4506  ldloc.0
0x4507  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x450c  ldloc.0
0x450d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x4512  ldloc.0
0x4513  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x4518  ldloc.0
0x4519  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x451e  newobj   instance void Microsoft.Crm.ReportingServices2010.GetDataDrivenSubscriptionPropertiesCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x4523  callvirt instance void Microsoft.Crm.ReportingServices2010.GetDataDrivenSubscriptionPropertiesCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.GetDataDrivenSubscriptionPropertiesCompletedEventArgs e)
0x4528  ret
```
