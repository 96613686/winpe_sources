# Microsoft.Crm.Tools.Admin.CreateOrganizationInstaller::Create

- ea: `0x12000`
- end: `0x120d5`
- name: `Microsoft.Crm.Tools.Admin.CreateOrganizationInstaller::Create`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x11fe0`

## callees

- `0x22e0`
- `0x41c0`
- `0x41d0`
- `0x4490`
- `0x8470`
- `0x8630`
- `0x9890`
- `0x9a90`
- `0x9b40`
- `0x9b60`
- `0x9d30`
- `0x11db0`
- `0x11ec0`
- `0x11ee0`
- `0x12000`
- `0x120e0`
- `0x12150`

## string_xrefs

- `0x12065`: `Organization.Create.Failed.Log`

## pseudocode

```c

```

## disassembly

```asm
0x12000  ldarg.1
0x12001  ldc.i4.1
0x12002  callvirt instance void Microsoft.Crm.Tools.Admin.ICreateOrganizationInfo::set_CreateDatabase(bool value)
0x12007  ldarg.1
0x12008  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Tools.Admin.IOrganizationInfo::get_Data()
0x1200d  ldstr    aOrganizationin_9// "OrganizationInfo.OrganizationCollation"
0x12012  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x12017  brtrue.s loc_12029
0x12019  ldarg.1
0x1201a  call     int32 Microsoft.Crm.Tools.Admin.DMSnapInLibCache::get_LanguageId()
0x1201f  call     string [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseUtility::GetSupportedCollationName(int32)
0x12024  callvirt instance void Microsoft.Crm.Tools.Admin.ICreateOrganizationInfo::set_OrganizationCollation(string value)
0x12029  ldarg.1
0x1202a  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationCreator::.ctor(class Microsoft.Crm.Tools.Admin.ICreateOrganizationInfo organizationInfo)
0x1202f  stloc.0
0x12030  ldloc.0
0x12031  ldarg.0
0x12032  call     instance bool Microsoft.Crm.Tools.Admin.CreateOrganizationInstaller::get_PromptOnError()
0x12037  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationOperation::set_PromptOnError(bool value)
0x1203c  ldarg.0
0x1203d  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x12042  dup
0x12043  ldvirtftn instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x12049  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventHandler::.ctor(object, native int)
0x1204e  stloc.1
0x1204f  ldloc.0
0x12050  ldloc.1
0x12051  ldarg.0
0x12052  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_ComponentProgress()
0x12057  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationOperation::HookProgressHandlers(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventHandler installerProgressHandler, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource componentProgress)
0x1205c  ldloc.0
0x1205d  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationOperation::Execute()
0x12062  leave.s  loc_120D4
0x12064  stloc.2
0x12065  ldstr    aOrganizationCr// "Organization.Create.Failed.Log"
0x1206a  ldc.i4.3
0x1206b  newarr   [mscorlib]System.Object
0x12070  dup
0x12071  ldc.i4.0
0x12072  ldarg.1
0x12073  castclass Microsoft.Crm.Tools.Admin.OrganizationInfo
0x12078  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x1207d  box      [mscorlib]System.Guid
0x12082  stelem.ref
0x12083  dup
0x12084  ldc.i4.1
0x12085  ldarg.1
0x12086  callvirt instance string Microsoft.Crm.Tools.Admin.ICreateOrganizationInfo::get_OrganizationUniqueName()
0x1208b  callvirt instance string [mscorlib]System.Object::ToString()
0x12090  stelem.ref
0x12091  dup
0x12092  ldc.i4.2
0x12093  ldloc.2
0x12094  stelem.ref
0x12095  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x1209a  stloc.3
0x1209b  ldloc.3
0x1209c  ldc.i4.0
0x1209d  newarr   [mscorlib]System.Object
0x120a2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, object[])
0x120a7  ldarg.0
0x120a8  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource Microsoft.Crm.Tools.Admin.ProgressExecution::get_OverallProgress()
0x120ad  ldarg.0
0x120ae  ldc.i4.1
0x120af  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs::.ctor(bool)
0x120b4  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IProgressEventSource::RaiseProgressChanged(object, class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventArgs)
0x120b9  ldloc.3
0x120ba  ldloc.2
0x120bb  ldc.i4   0x8004B001
0x120c0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0x120c5  throw
0x120c6  ldloc.0
0x120c7  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationOperation::SetCompletionMessage()
0x120cc  ldloc.0
0x120cd  ldloc.1
0x120ce  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationOperation::UnhookProgressHandlers(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProgressEventHandler installerProgressHandler)
0x120d3  endfinally
0x120d4  ret
```
