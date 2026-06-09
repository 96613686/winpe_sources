# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateSubscriptionOperationCompleted

- ea: `0x4710`
- end: `0x4749`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateSubscriptionOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x4710`
- `0xd8f0`
- `0xd930`

## pseudocode

```c

```

## disassembly

```asm
0x4710  ldarg.0
0x4711  ldfld    class Microsoft.Crm.ReportingServices2010.CreateSubscriptionCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateSubscriptionCompleted
0x4716  brfalse.s loc_4748
0x4718  ldarg.1
0x4719  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x471e  stloc.0
0x471f  ldarg.0
0x4720  ldfld    class Microsoft.Crm.ReportingServices2010.CreateSubscriptionCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateSubscriptionCompleted
0x4725  ldarg.0
0x4726  ldloc.0
0x4727  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x472c  ldloc.0
0x472d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x4732  ldloc.0
0x4733  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x4738  ldloc.0
0x4739  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x473e  newobj   instance void Microsoft.Crm.ReportingServices2010.CreateSubscriptionCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x4743  callvirt instance void Microsoft.Crm.ReportingServices2010.CreateSubscriptionCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.CreateSubscriptionCompletedEventArgs e)
0x4748  ret
```
