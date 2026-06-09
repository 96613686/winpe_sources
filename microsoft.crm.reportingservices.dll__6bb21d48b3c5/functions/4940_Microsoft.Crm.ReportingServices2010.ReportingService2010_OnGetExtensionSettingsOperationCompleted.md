# Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetExtensionSettingsOperationCompleted

- ea: `0x4940`
- end: `0x4979`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::OnGetExtensionSettingsOperationCompleted`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x4940`
- `0xda30`
- `0xda70`

## pseudocode

```c

```

## disassembly

```asm
0x4940  ldarg.0
0x4941  ldfld    class Microsoft.Crm.ReportingServices2010.GetExtensionSettingsCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetExtensionSettingsCompleted
0x4946  brfalse.s loc_4978
0x4948  ldarg.1
0x4949  castclass [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs
0x494e  stloc.0
0x494f  ldarg.0
0x4950  ldfld    class Microsoft.Crm.ReportingServices2010.GetExtensionSettingsCompletedEventHandler Microsoft.Crm.ReportingServices2010.ReportingService2010::GetExtensionSettingsCompleted
0x4955  ldarg.0
0x4956  ldloc.0
0x4957  callvirt instance object[] [System.Web.Services]System.Web.Services.Protocols.InvokeCompletedEventArgs::get_Results()
0x495c  ldloc.0
0x495d  callvirt instance class [mscorlib]System.Exception [System]System.ComponentModel.AsyncCompletedEventArgs::get_Error()
0x4962  ldloc.0
0x4963  callvirt instance bool [System]System.ComponentModel.AsyncCompletedEventArgs::get_Cancelled()
0x4968  ldloc.0
0x4969  callvirt instance object [System]System.ComponentModel.AsyncCompletedEventArgs::get_UserState()
0x496e  newobj   instance void Microsoft.Crm.ReportingServices2010.GetExtensionSettingsCompletedEventArgs::.ctor(object[] results, class [mscorlib]System.Exception exception, bool cancelled, object userState)
0x4973  callvirt instance void Microsoft.Crm.ReportingServices2010.GetExtensionSettingsCompletedEventHandler::Invoke(object sender, class Microsoft.Crm.ReportingServices2010.GetExtensionSettingsCompletedEventArgs e)
0x4978  ret
```
