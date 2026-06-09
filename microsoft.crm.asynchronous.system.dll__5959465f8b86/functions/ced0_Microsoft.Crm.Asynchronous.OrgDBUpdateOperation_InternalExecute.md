# Microsoft.Crm.Asynchronous.OrgDBUpdateOperation::InternalExecute

- ea: `0xced0`
- end: `0xd011`
- name: `Microsoft.Crm.Asynchronous.OrgDBUpdateOperation::InternalExecute`
- size: `321`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x8f00`
- `0x8f10`
- `0x8f50`
- `0xced0`
- `0xd020`
- `0xd080`

## string_xrefs

- `0xceda`: `Operation type must be 'OrgDBUpdate'`
- `0xcf22`: `Attempting to apply dbUpdates for org {0}`
- `0xcf83`: `Applying dbUpdates for org {0} was successful.`

## pseudocode

```c

```

## disassembly

```asm
0xced0  ldarg.1
0xced1  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xced6  ldc.i4.s 0x2C
0xced8  ceq
0xceda  ldstr    aOperationTypeM_19// "Operation type must be 'OrgDBUpdate'"
0xcedf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xcee4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0xcee9  stloc.0
0xceea  ldarg.0
0xceeb  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xcef0  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationState()
0xcef5  stloc.1
0xcef6  ldloc.1
0xcef7  box      [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState
0xcefc  call     string [mscorlib]System.Convert::ToString(object)
0xcf01  stloc.2
0xcf02  ldnull
0xcf03  stloc.3
0xcf04  call     class Microsoft.Crm.Asynchronous.OrgDBUpdateEventSource Microsoft.Crm.Asynchronous.OrgDBUpdateEventSource::get_Instance()
0xcf09  ldarg.0
0xcf0a  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xcf0f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcf14  ldloc.2
0xcf15  callvirt instance void Microsoft.Crm.Asynchronous.OrgDBUpdateEventSource::OrgDBUpdateJobStart(valuetype [mscorlib]System.Guid organizationId, string organizationState)
0xcf1a  ldarg.1
0xcf1b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xcf20  ldc.i4.s 0x15
0xcf22  ldstr    aAttemptingToAp// "Attempting to apply dbUpdates for org {"...
0xcf27  ldc.i4.1
0xcf28  newarr   [mscorlib]System.Object
0xcf2d  dup
0xcf2e  ldc.i4.0
0xcf2f  ldarg.0
0xcf30  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xcf35  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcf3a  box      [mscorlib]System.Guid
0xcf3f  stelem.ref
0xcf40  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcf45  ldc.i4.3
0xcf46  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MessageReport::set_UIMode(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.UIMode)
0xcf4b  ldarg.0
0xcf4c  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xcf51  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcf56  ldc.i4.1
0xcf57  ldc.i4.0
0xcf58  newobj   instance void [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.OrganizationDBUpdateInstaller::.ctor(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateSource, valuetype [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.DMSnapinLib.Organization.OrgDbUpdateMode)
0xcf5d  stloc.s  5
0xcf5f  ldloc.s  5
0xcf61  callvirt instance void [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.OrganizationOperation::Execute()
0xcf66  call     class [mscorlib]System.Version [Microsoft.Crm.Tools.Admin.DMSnapinLib]Microsoft.Crm.Tools.Admin.DBImportHelper::GetVersionInstalled()
0xcf6b  stloc.s  4
0xcf6d  leave.s  loc_CF7B
0xcf6f  ldloc.s  5
0xcf71  brfalse.s loc_CF7A
0xcf73  ldloc.s  5
0xcf75  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcf7a  endfinally
0xcf7b  ldarg.1
0xcf7c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xcf81  ldc.i4.s 0x15
0xcf83  ldstr    aApplyingDbupda// "Applying dbUpdates for org {0} was succ"...
0xcf88  ldc.i4.1
0xcf89  newarr   [mscorlib]System.Object
0xcf8e  dup
0xcf8f  ldc.i4.0
0xcf90  ldarg.0
0xcf91  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xcf96  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcf9b  box      [mscorlib]System.Guid
0xcfa0  stelem.ref
0xcfa1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcfa6  ldarg.0
0xcfa7  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xcfac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcfb1  ldloc.s  4
0xcfb3  call     void Microsoft.Crm.Asynchronous.OrgUpdateActions::CopyUpdateActions(valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Version version)
0xcfb8  leave.s  loc_D009
0xcfba  callvirt instance string [mscorlib]System.Object::ToString()
0xcfbf  stloc.3
0xcfc0  leave.s  loc_D009
0xcfc2  ldarg.0
0xcfc3  ldarg.0
0xcfc4  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xcfc9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcfce  ldloca.s 1
0xcfd0  call     instance bool Microsoft.Crm.Asynchronous.OrgDBUpdateOperation::TryGetOrganizationState(valuetype [mscorlib]System.Guid organizationId, [out] valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState& organizationState)
0xcfd5  stloc.s  6
0xcfd7  ldloc.1
0xcfd8  box      [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState
0xcfdd  call     string [mscorlib]System.Convert::ToString(object)
0xcfe2  stloc.2
0xcfe3  call     class Microsoft.Crm.Asynchronous.OrgDBUpdateEventSource Microsoft.Crm.Asynchronous.OrgDBUpdateEventSource::get_Instance()
0xcfe8  ldloc.0
0xcfe9  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0xcfee  ldloc.3
0xcfef  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xcff4  ldloc.s  6
0xcff6  ldloc.3
0xcff7  ldarg.0
0xcff8  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xcffd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xd002  ldloc.2
0xd003  callvirt instance void Microsoft.Crm.Asynchronous.OrgDBUpdateEventSource::OrgDBUpdateJobFinish(int64 duration, bool isSuccess, bool isOrgFetchStateSuccess, string exceptionMessage, valuetype [mscorlib]System.Guid organizationId, string organizationState)
0xd008  endfinally
0xd009  ldc.i4.s 0x1E
0xd00b  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRemoveEventResult::.ctor(int32)
0xd010  ret
```
