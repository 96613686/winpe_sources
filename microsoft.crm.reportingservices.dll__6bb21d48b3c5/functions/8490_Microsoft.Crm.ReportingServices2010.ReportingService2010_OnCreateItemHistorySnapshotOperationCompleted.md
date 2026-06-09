# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateItemHistorySnapshotOperationCompleted

- ea: `0x8490`
- end: `0x84c9`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateItemHistorySnapshotOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x8490`
- `0xfb70`
- `0xfbb0`

## pseudocode

```c

```

## disassembly

```asm
0x8490  ldarg.0
0x8491  ldfld    class Microsoft.Crm.ReportingServices2010.CreateItemHistorySnapshotCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateItemHistorySnapshotCompleted
0x8496  brfalse.s loc_84C8
0x8498  ldarg.1
0x8499  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x849e  stloc.0
0x849f  ldarg.0
0x84a0  ldfld    class Microsoft.Crm.ReportingServices2010.CreateItemHistorySnapshotCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateItemHistorySnapshotCompleted
0x84a5  ldarg.0
0x84a6  ldloc.0
0x84a7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x84ac  ldloc.0
0x84ad  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x84b2  ldloc.0
0x84b3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x84b8  ldloc.0
0x84b9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x84be  newobj   instance void Microsoft.Crm.ReportingServices2010.CreateItemHistorySnapshotCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x84c3  callvirt instance void Microsoft.Crm.ReportingServices2010.CreateItemHistorySnapshotCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.CreateItemHistorySnapshotCompletedEventArgs e)
0x84c8  ret
```
