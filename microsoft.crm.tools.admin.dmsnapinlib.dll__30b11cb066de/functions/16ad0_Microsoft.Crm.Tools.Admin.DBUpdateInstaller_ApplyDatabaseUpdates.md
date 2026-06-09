# Microsoft.Crm.Tools.Admin.DBUpdateInstaller::ApplyDatabaseUpdates

- ea: `0x16ad0`
- end: `0x16b77`
- name: `Microsoft.Crm.Tools.Admin.DBUpdateInstaller::ApplyDatabaseUpdates`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x16ab0`

## callees

- `0x22e0`
- `0x41c0`
- `0x41d0`
- `0x9b40`
- `0x9b60`
- `0x9d30`
- `0x169f0`
- `0x16ad0`
- `0x17000`

## string_xrefs

- `0x16b07`: `Organization.Update.Failed.Log`

## pseudocode

```c

```

## disassembly

```asm
0x16ad0  ldarg.1
0x16ad1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.IDBUpdateInfo::get_OrganizationId()
0x16ad6  ldc.i4.0
0x16ad7  ldc.i4.0
0x16ad8  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationDBUpdateInstaller::.ctor(valuetype [mscorlib]System.Guid organizationId, [opt] valuetype Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateSource source, [opt] valuetype Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateMode mode)
0x16add  stloc.0
0x16ade  ldarg.0
0x16adf  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x16ae4  dup
0x16ae5  ldvirtftn instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x16aeb  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventHandler::.ctor(object, native int)
0x16af0  stloc.1
0x16af1  ldloc.0
0x16af2  ldloc.1
0x16af3  ldarg.0
0x16af4  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_ComponentProgress()
0x16af9  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationOperation::HookProgressHandlers(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventHandler installerProgressHandler, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource componentProgress)
0x16afe  ldloc.0
0x16aff  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationOperation::Execute()
0x16b04  leave.s  loc_16B76
0x16b06  stloc.2
0x16b07  ldstr    aOrganizationUp_3// "Organization.Update.Failed.Log"
0x16b0c  ldc.i4.2
0x16b0d  newarr   [mscorlib]System.Object
0x16b12  dup
0x16b13  ldc.i4.0
0x16b14  ldarg.1
0x16b15  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.IDBUpdateInfo::get_OrganizationId()
0x16b1a  box      [mscorlib]System.Guid
0x16b1f  stelem.ref
0x16b20  dup
0x16b21  ldc.i4.1
0x16b22  ldloc.2
0x16b23  stelem.ref
0x16b24  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x16b29  stloc.3
0x16b2a  ldloc.2
0x16b2b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x16b30  ldc.i4.s 0x39
0x16b32  ldloc.3
0x16b33  ldc.i4.0
0x16b34  newarr   [mscorlib]System.Object
0x16b39  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16b3e  ldloc.3
0x16b3f  ldc.i4.0
0x16b40  newarr   [mscorlib]System.Object
0x16b45  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, object[])
0x16b4a  ldarg.0
0x16b4b  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x16b50  ldarg.0
0x16b51  ldc.i4.1
0x16b52  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::.ctor(bool)
0x16b57  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x16b5c  ldloc.3
0x16b5d  ldloc.2
0x16b5e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x16b63  throw
0x16b64  ldloc.0
0x16b65  ldloc.1
0x16b66  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationOperation::UnhookProgressHandlers(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventHandler installerProgressHandler)
0x16b6b  endfinally
0x16b6c  ldloc.0
0x16b6d  brfalse.s loc_16B75
0x16b6f  ldloc.0
0x16b70  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16b75  endfinally
0x16b76  ret
```
