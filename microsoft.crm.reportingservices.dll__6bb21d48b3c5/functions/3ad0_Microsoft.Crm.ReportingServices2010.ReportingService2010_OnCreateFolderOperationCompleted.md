# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateFolderOperationCompleted

- ea: `0x3ad0`
- end: `0x3b09`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnCreateFolderOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x3ad0`
- `0xd1c0`
- `0xd200`

## pseudocode

```c

```

## disassembly

```asm
0x3ad0  ldarg.0
0x3ad1  ldfld    class Microsoft.Crm.ReportingServices2010.CreateFolderCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateFolderCompleted
0x3ad6  brfalse.s loc_3B08
0x3ad8  ldarg.1
0x3ad9  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x3ade  stloc.0
0x3adf  ldarg.0
0x3ae0  ldfld    class Microsoft.Crm.ReportingServices2010.CreateFolderCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateFolderCompleted
0x3ae5  ldarg.0
0x3ae6  ldloc.0
0x3ae7  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x3aec  ldloc.0
0x3aed  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x3af2  ldloc.0
0x3af3  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x3af8  ldloc.0
0x3af9  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x3afe  newobj   instance void Microsoft.Crm.ReportingServices2010.CreateFolderCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x3b03  callvirt instance void Microsoft.Crm.ReportingServices2010.CreateFolderCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.CreateFolderCompletedEventArgs e)
0x3b08  ret
```
