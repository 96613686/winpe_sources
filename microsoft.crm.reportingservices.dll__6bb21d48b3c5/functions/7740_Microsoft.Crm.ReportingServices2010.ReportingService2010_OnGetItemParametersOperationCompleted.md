# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemParametersOperationCompleted

- ea: `0x7740`
- end: `0x7779`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemParametersOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x7740`
- `0xf430`
- `0xf470`

## pseudocode

```c

```

## disassembly

```asm
0x7740  ldarg.0
0x7741  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemParametersCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemParametersCompleted
0x7746  brfalse.s loc_7778
0x7748  ldarg.1
0x7749  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x774e  stloc.0
0x774f  ldarg.0
0x7750  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemParametersCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemParametersCompleted
0x7755  ldarg.0
0x7756  ldloc.0
0x7757  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x775c  ldloc.0
0x775d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x7762  ldloc.0
0x7763  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x7768  ldloc.0
0x7769  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x776e  newobj   instance void Microsoft.Crm.ReportingServices2010.GetItemParametersCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x7773  callvirt instance void Microsoft.Crm.ReportingServices2010.GetItemParametersCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.GetItemParametersCompletedEventArgs e)
0x7778  ret
```
