# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemReferencesOperationCompleted

- ea: `0x3e70`
- end: `0x3ea9`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemReferencesOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x3e70`
- `0xd3a0`
- `0xd3e0`

## pseudocode

```c

```

## disassembly

```asm
0x3e70  ldarg.0
0x3e71  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemReferencesCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemReferencesCompleted
0x3e76  brfalse.s loc_3EA8
0x3e78  ldarg.1
0x3e79  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x3e7e  stloc.0
0x3e7f  ldarg.0
0x3e80  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemReferencesCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemReferencesCompleted
0x3e85  ldarg.0
0x3e86  ldloc.0
0x3e87  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x3e8c  ldloc.0
0x3e8d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x3e92  ldloc.0
0x3e93  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x3e98  ldloc.0
0x3e99  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x3e9e  newobj   instance void Microsoft.Crm.ReportingServices2010.GetItemReferencesCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x3ea3  callvirt instance void Microsoft.Crm.ReportingServices2010.GetItemReferencesCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.GetItemReferencesCompletedEventArgs e)
0x3ea8  ret
```
