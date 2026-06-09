# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateDataDrivenSubscriptionOperationCompleted

- ea: `0x4860`
- end: `0x4899`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateDataDrivenSubscriptionOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x4860`
- `0xd990`
- `0xd9d0`

## pseudocode

```c

```

## disassembly

```asm
0x4860  ldarg.0
0x4861  ldfld    class Microsoft.Crm.ReportingServices2010.CreateDataDrivenSubscriptionCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataDrivenSubscriptionCompleted
0x4866  brfalse.s loc_4898
0x4868  ldarg.1
0x4869  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x486e  stloc.0
0x486f  ldarg.0
0x4870  ldfld    class Microsoft.Crm.ReportingServices2010.CreateDataDrivenSubscriptionCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateDataDrivenSubscriptionCompleted
0x4875  ldarg.0
0x4876  ldloc.0
0x4877  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x487c  ldloc.0
0x487d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x4882  ldloc.0
0x4883  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x4888  ldloc.0
0x4889  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x488e  newobj   instance void Microsoft.Crm.ReportingServices2010.CreateDataDrivenSubscriptionCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x4893  callvirt instance void Microsoft.Crm.ReportingServices2010.CreateDataDrivenSubscriptionCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.CreateDataDrivenSubscriptionCompletedEventArgs e)
0x4898  ret
```
