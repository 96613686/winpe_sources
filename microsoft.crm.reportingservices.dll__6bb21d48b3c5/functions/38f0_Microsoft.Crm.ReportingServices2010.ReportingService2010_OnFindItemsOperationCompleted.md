# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnFindItemsOperationCompleted

- ea: `0x38f0`
- end: `0x3929`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnFindItemsOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x38f0`
- `0xd080`
- `0xd0c0`

## pseudocode

```c

```

## disassembly

```asm
0x38f0  ldarg.0
0x38f1  ldfld    class Microsoft.Crm.ReportingServices2010.FindItemsCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::FindItemsCompleted
0x38f6  brfalse.s loc_3928
0x38f8  ldarg.1
0x38f9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x38fe  stloc.0
0x38ff  ldarg.0
0x3900  ldfld    class Microsoft.Crm.ReportingServices2010.FindItemsCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::FindItemsCompleted
0x3905  ldarg.0
0x3906  ldloc.0
0x3907  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x390c  ldloc.0
0x390d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x3912  ldloc.0
0x3913  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x3918  ldloc.0
0x3919  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x391e  newobj   instance void Microsoft.Crm.ReportingServices2010.FindItemsCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x3923  callvirt instance void Microsoft.Crm.ReportingServices2010.FindItemsCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.FindItemsCompletedEventArgs e)
0x3928  ret
```
