# Microsoft.Crm.Tools.Admin.UpgradeOrganizationInstaller::Upgrade

- ea: `0x16600`
- end: `0x16697`
- name: `Microsoft.Crm.Tools.Admin.UpgradeOrganizationInstaller::Upgrade`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x165e0`

## callees

- `0x22e0`
- `0x41c0`
- `0x41d0`
- `0x9b40`
- `0x9b60`
- `0x9d70`
- `0x164f0`
- `0x16600`
- `0x166a0`
- `0x16720`

## pseudocode

```c

```

## disassembly

```asm
0x16600  ldarg.1
0x16601  castclass Microsoft.Crm.Tools.Admin.OrganizationInfo
0x16606  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x1660b  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationUpgrader::.ctor(class [mscorlib]System.Collections.IDictionary parameters)
0x16610  stloc.0
0x16611  ldarg.0
0x16612  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x16617  dup
0x16618  ldvirtftn instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x1661e  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventHandler::.ctor(object, native int)
0x16623  stloc.1
0x16624  ldloc.0
0x16625  ldloc.1
0x16626  ldarg.0
0x16627  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_ComponentProgress()
0x1662c  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationOperation::HookProgressHandlers(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventHandler installerProgressHandler, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource componentProgress)
0x16631  ldloc.0
0x16632  ldarg.0
0x16633  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState Microsoft.Crm.Tools.Admin.UpgradeOrganizationInstaller::get_StateToSetOnSuccess()
0x16638  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationOperation::Execute(valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState postOperationState)
0x1663d  leave.s  loc_16696
0x1663f  stloc.2
0x16640  ldstr    aOrganizationUp// "Organization.Upgrade.Failed.Log"
0x16645  ldc.i4.2
0x16646  newarr   [mscorlib]System.Object
0x1664b  dup
0x1664c  ldc.i4.0
0x1664d  ldarg.1
0x1664e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.IUpgradeOrganizationInfo::get_OrganizationId()
0x16653  box      [mscorlib]System.Guid
0x16658  stelem.ref
0x16659  dup
0x1665a  ldc.i4.1
0x1665b  ldloc.2
0x1665c  stelem.ref
0x1665d  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x16662  stloc.3
0x16663  ldloc.3
0x16664  ldc.i4.0
0x16665  newarr   [mscorlib]System.Object
0x1666a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, object[])
0x1666f  ldarg.0
0x16670  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x16675  ldarg.0
0x16676  ldc.i4.1
0x16677  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::.ctor(bool)
0x1667c  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x16681  ldloc.3
0x16682  ldloc.2
0x16683  ldc.i4   0x8004B014
0x16688  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0x1668d  throw
0x1668e  ldloc.0
0x1668f  ldloc.1
0x16690  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationOperation::UnhookProgressHandlers(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventHandler installerProgressHandler)
0x16695  endfinally
0x16696  ret
```
