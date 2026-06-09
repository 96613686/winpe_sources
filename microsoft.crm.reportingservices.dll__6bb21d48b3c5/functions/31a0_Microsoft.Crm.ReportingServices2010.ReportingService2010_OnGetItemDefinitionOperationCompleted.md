# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemDefinitionOperationCompleted

- ea: `0x31a0`
- end: `0x31d9`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetItemDefinitionOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x31a0`
- `0xcc70`
- `0xccb0`

## pseudocode

```c

```

## disassembly

```asm
0x31a0  ldarg.0
0x31a1  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemDefinitionCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemDefinitionCompleted
0x31a6  brfalse.s loc_31D8
0x31a8  ldarg.1
0x31a9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x31ae  stloc.0
0x31af  ldarg.0
0x31b0  ldfld    class Microsoft.Crm.ReportingServices2010.GetItemDefinitionCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemDefinitionCompleted
0x31b5  ldarg.0
0x31b6  ldloc.0
0x31b7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x31bc  ldloc.0
0x31bd  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x31c2  ldloc.0
0x31c3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x31c8  ldloc.0
0x31c9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x31ce  newobj   instance void Microsoft.Crm.ReportingServices2010.GetItemDefinitionCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x31d3  callvirt instance void Microsoft.Crm.ReportingServices2010.GetItemDefinitionCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.GetItemDefinitionCompletedEventArgs e)
0x31d8  ret
```
