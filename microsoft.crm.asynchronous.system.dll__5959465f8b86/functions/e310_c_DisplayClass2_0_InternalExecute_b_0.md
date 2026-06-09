# <>c__DisplayClass2_0::<InternalExecute>b__0

- ea: `0xe310`
- end: `0xe6b6`
- name: `<>c__DisplayClass2_0::<InternalExecute>b__0`
- size: `934`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x5880`
- `0x9070`
- `0x9080`
- `0x90a0`
- `0x9370`
- `0x9630`
- `0x98d0`
- `0xe310`

## string_xrefs

- `0xe633`: `p_ReindexAll could not update all statistics due to time constraint. {0}`

## pseudocode

```c

```

## disassembly

```asm
0xe310  ldarg.0
0xe311  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass2_0::asyncEvent
0xe316  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xe31b  ldc.i4.s 0x1E
0xe31d  ceq
0xe31f  ldstr    aOperationTypeM_22// "Operation type must be 'Reindex All'"
0xe324  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xe329  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0xe32e  ldarg.0
0xe32f  ldfld    class Microsoft.Crm.Asynchronous.ReindexAllOperation <>c__DisplayClass2_0::<>4__this
0xe334  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xe339  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xe33e  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsBackedByXdb(valuetype [mscorlib]System.Guid)
0xe343  brfalse.s loc_E3AD
0xe345  ldarg.0
0xe346  ldfld    class Microsoft.Crm.Asynchronous.ReindexAllOperation <>c__DisplayClass2_0::<>4__this
0xe34b  ldarg.0
0xe34c  ldfld    class Microsoft.Crm.Asynchronous.ReindexAllOperation <>c__DisplayClass2_0::<>4__this
0xe351  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xe356  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xe35b  call     instance bool Microsoft.Crm.Asynchronous.ReindexAllOperation::OrgXdbUseLegacyReindexJob(valuetype [mscorlib]System.Guid organizationId)
0xe360  brtrue.s loc_E3AD
0xe362  ldstr    aReindexJobIsNo// "Reindex Job is not supported because th"...
0xe367  stloc.2
0xe368  ldloc.2
0xe369  ldc.i4.1
0xe36a  newarr   [mscorlib]System.Object
0xe36f  dup
0xe370  ldc.i4.0
0xe371  ldarg.0
0xe372  ldfld    class Microsoft.Crm.Asynchronous.ReindexAllOperation <>c__DisplayClass2_0::<>4__this
0xe377  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xe37c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xe381  box      [mscorlib]System.Guid
0xe386  stelem.ref
0xe387  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Warning(string, object[])
0xe38c  ldloc.2
0xe38d  ldarg.0
0xe38e  ldfld    class Microsoft.Crm.Asynchronous.ReindexAllOperation <>c__DisplayClass2_0::<>4__this
0xe393  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xe398  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xe39d  box      [mscorlib]System.Guid
0xe3a2  call     string [mscorlib]System.String::Format(string, object)
0xe3a7  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncCanceledResult::.ctor(string)
0xe3ac  ret
0xe3ad  call     class Microsoft.Crm.Asynchronous.ReindexAllEventSource Microsoft.Crm.Asynchronous.ReindexAllEventSource::get_Instance()
0xe3b2  ldarg.0
0xe3b3  ldfld    class Microsoft.Crm.Asynchronous.ReindexAllOperation <>c__DisplayClass2_0::<>4__this
0xe3b8  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xe3bd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xe3c2  callvirt instance void Microsoft.Crm.Asynchronous.ReindexAllEventSource::ReindexAllStart(valuetype [mscorlib]System.Guid organizationId)
0xe3c7  ldarg.0
0xe3c8  ldfld    class Microsoft.Crm.Asynchronous.ReindexAllOperation <>c__DisplayClass2_0::<>4__this
0xe3cd  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xe3d2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xe3d7  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ShrinkDatabaseUtility::ReindexAll_2(valuetype [mscorlib]System.Guid)
0xe3dc  stloc.0
0xe3dd  ldstr    aResultcode// "ResultCode"
0xe3e2  ldloc.0
0xe3e3  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ResultCode()
0xe3e8  stloc.3
0xe3e9  ldloca.s 3
0xe3eb  call     instance string [mscorlib]System.Int32::ToString()
0xe3f0  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperty(string, string)
0xe3f5  ldstr    aReindexallinfo// "ReindexAllInfo"
0xe3fa  ldloc.0
0xe3fb  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0xe400  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperty(string, string)
0xe405  ldloc.0
0xe406  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ExceptionCode()
0xe40b  brfalse  loc_E4D0
0xe410  ldloc.0
0xe411  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ExceptionCode()
0xe416  ldc.i4.s 0xFE
0xe418  bne.un.s loc_E435
0xe41a  call     class Microsoft.Crm.Asynchronous.ReindexAllEventSource Microsoft.Crm.Asynchronous.ReindexAllEventSource::get_Instance()
0xe41f  ldarg.0
0xe420  ldfld    class Microsoft.Crm.Asynchronous.ReindexAllOperation <>c__DisplayClass2_0::<>4__this
0xe425  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xe42a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xe42f  ldloc.0
0xe430  callvirt instance void Microsoft.Crm.Asynchronous.ReindexAllEventSource::ReindexAllTimeout(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo reindexInfo)
0xe435  call     class Microsoft.Crm.Asynchronous.ReindexAllEventSource Microsoft.Crm.Asynchronous.ReindexAllEventSource::get_Instance()
0xe43a  ldarg.0
0xe43b  ldfld    class Microsoft.Crm.Asynchronous.ReindexAllOperation <>c__DisplayClass2_0::<>4__this
0xe440  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xe445  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xe44a  ldloc.0
0xe44b  callvirt instance void Microsoft.Crm.Asynchronous.ReindexAllEventSource::ReindexAllError(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo reindexInfo)
0xe450  ldnull
0xe451  ldarg.0
0xe452  ldfld    class Microsoft.Crm.Asynchronous.ReindexAllOperation <>c__DisplayClass2_0::<>4__this
0xe457  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xe45c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xe461  ldc.i4.s 0x15
0xe463  ldstr    a0// "{0}"
0xe468  ldc.i4.1
0xe469  newarr   [mscorlib]System.Object
0xe46e  dup
0xe46f  ldc.i4.0
0xe470  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe475  ldstr    aPReindexallFai// "p_ReindexAll failed with result: {0}. M"...
0xe47a  ldc.i4.2
0xe47b  newarr   [mscorlib]System.Object
0xe480  dup
0xe481  ldc.i4.0
0xe482  ldloc.0
0xe483  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ExceptionCode()
0xe488  box      [mscorlib]System.Int32
0xe48d  stelem.ref
0xe48e  dup
0xe48f  ldc.i4.1
0xe490  ldloc.0
0xe491  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ExceptionMessage()
0xe496  stelem.ref
0xe497  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe49c  stelem.ref
0xe49d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xe4a2  ldloc.0
0xe4a3  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ExceptionCode()
0xe4a8  ldstr    aPReindexallFai// "p_ReindexAll failed with result: {0}. M"...
0xe4ad  ldc.i4.2
0xe4ae  newarr   [mscorlib]System.Object
0xe4b3  dup
0xe4b4  ldc.i4.0
0xe4b5  ldloc.0
0xe4b6  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ExceptionCode()
0xe4bb  box      [mscorlib]System.Int32
0xe4c0  stelem.ref
0xe4c1  dup
0xe4c2  ldc.i4.1
0xe4c3  ldloc.0
0xe4c4  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ExceptionMessage()
0xe4c9  stelem.ref
0xe4ca  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(int32, string, object[])
0xe4cf  ret
0xe4d0  ldloc.0
0xe4d1  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ResultCode()
0xe4d6  brfalse  loc_E58E
0xe4db  ldloc.0
0xe4dc  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ResultCode()
0xe4e1  ldc.i4.1
0xe4e2  beq      loc_E58E
0xe4e7  ldloc.0
0xe4e8  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ResultCode()
0xe4ed  ldc.i4.2
0xe4ee  beq      loc_E58E
0xe4f3  call     class Microsoft.Crm.Asynchronous.ReindexAllEventSource Microsoft.Crm.Asynchronous.ReindexAllEventSource::get_Instance()
0xe4f8  ldarg.0
0xe4f9  ldfld    class Microsoft.Crm.Asynchronous.ReindexAllOperation <>c__DisplayClass2_0::<>4__this
0xe4fe  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xe503  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xe508  ldloc.0
0xe509  callvirt instance void Microsoft.Crm.Asynchronous.ReindexAllEventSource::ReindexAllError(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo reindexInfo)
0xe50e  ldnull
0xe50f  ldarg.0
0xe510  ldfld    class Microsoft.Crm.Asynchronous.ReindexAllOperation <>c__DisplayClass2_0::<>4__this
0xe515  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xe51a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xe51f  ldc.i4.s 0x15
0xe521  ldstr    a0// "{0}"
0xe526  ldc.i4.1
0xe527  newarr   [mscorlib]System.Object
0xe52c  dup
0xe52d  ldc.i4.0
0xe52e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe533  ldstr    aPReindexallFai// "p_ReindexAll failed with result: {0}. M"...
0xe538  ldc.i4.2
0xe539  newarr   [mscorlib]System.Object
0xe53e  dup
0xe53f  ldc.i4.0
0xe540  ldloc.0
0xe541  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ResultCode()
0xe546  box      [mscorlib]System.Int32
0xe54b  stelem.ref
0xe54c  dup
0xe54d  ldc.i4.1
0xe54e  ldloc.0
0xe54f  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_Output()
0xe554  stelem.ref
0xe555  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe55a  stelem.ref
0xe55b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xe560  ldloc.0
0xe561  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ResultCode()
0xe566  ldstr    aPReindexallFai// "p_ReindexAll failed with result: {0}. M"...
0xe56b  ldc.i4.2
0xe56c  newarr   [mscorlib]System.Object
0xe571  dup
0xe572  ldc.i4.0
0xe573  ldloc.0
0xe574  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ResultCode()
0xe579  box      [mscorlib]System.Int32
0xe57e  stelem.ref
0xe57f  dup
0xe580  ldc.i4.1
0xe581  ldloc.0
0xe582  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_Output()
0xe587  stelem.ref
0xe588  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(int32, string, object[])
0xe58d  ret
0xe58e  ldloc.0
0xe58f  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ResultCode()
0xe594  ldc.i4.1
0xe595  bne.un.s loc_E5F0
0xe597  call     class Microsoft.Crm.Asynchronous.ReindexAllEventSource Microsoft.Crm.Asynchronous.ReindexAllEventSource::get_Instance()
0xe59c  ldarg.0
0xe59d  ldfld    class Microsoft.Crm.Asynchronous.ReindexAllOperation <>c__DisplayClass2_0::<>4__this
0xe5a2  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xe5a7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xe5ac  ldloc.0
0xe5ad  callvirt instance void Microsoft.Crm.Asynchronous.ReindexAllEventSource::ReindexAllTimeout(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo reindexInfo)
0xe5b2  ldarg.0
0xe5b3  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass2_0::asyncEvent
0xe5b8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xe5bd  ldc.i4.s 0x15
0xe5bf  ldstr    a0// "{0}"
0xe5c4  ldc.i4.1
0xe5c5  newarr   [mscorlib]System.Object
0xe5ca  dup
0xe5cb  ldc.i4.0
0xe5cc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe5d1  ldstr    aPReindexallCou// "p_ReindexAll could not rebuild all inde"...
0xe5d6  ldc.i4.1
0xe5d7  newarr   [mscorlib]System.Object
0xe5dc  dup
0xe5dd  ldc.i4.0
0xe5de  ldloc.0
0xe5df  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_Output()
0xe5e4  stelem.ref
0xe5e5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe5ea  stelem.ref
0xe5eb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xe5f0  ldloc.0
0xe5f1  callvirt instance int32 [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_ResultCode()
0xe5f6  ldc.i4.2
0xe5f7  bne.un.s loc_E652
0xe5f9  call     class Microsoft.Crm.Asynchronous.ReindexAllEventSource Microsoft.Crm.Asynchronous.ReindexAllEventSource::get_Instance()
0xe5fe  ldarg.0
0xe5ff  ldfld    class Microsoft.Crm.Asynchronous.ReindexAllOperation <>c__DisplayClass2_0::<>4__this
0xe604  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xe609  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xe60e  ldloc.0
0xe60f  callvirt instance void Microsoft.Crm.Asynchronous.ReindexAllEventSource::StatisticsUpdateTimeout(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo reindexInfo)
0xe614  ldarg.0
0xe615  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass2_0::asyncEvent
0xe61a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xe61f  ldc.i4.s 0x15
0xe621  ldstr    a0// "{0}"
0xe626  ldc.i4.1
0xe627  newarr   [mscorlib]System.Object
0xe62c  dup
0xe62d  ldc.i4.0
0xe62e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe633  ldstr    aPReindexallCou_0// "p_ReindexAll could not update all stati"...
0xe638  ldc.i4.1
0xe639  newarr   [mscorlib]System.Object
0xe63e  dup
0xe63f  ldc.i4.0
0xe640  ldloc.0
0xe641  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_Output()
0xe646  stelem.ref
0xe647  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe64c  stelem.ref
0xe64d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xe652  call     class Microsoft.Crm.Asynchronous.ReindexAllEventSource Microsoft.Crm.Asynchronous.ReindexAllEventSource::get_Instance()
0xe657  ldarg.0
0xe658  ldfld    class Microsoft.Crm.Asynchronous.ReindexAllOperation <>c__DisplayClass2_0::<>4__this
0xe65d  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xe662  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xe667  ldloc.0
0xe668  callvirt instance void Microsoft.Crm.Asynchronous.ReindexAllEventSource::ReindexAllFinish(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo reindexInfo)
0xe66d  ldarg.0
0xe66e  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass2_0::asyncEvent
0xe673  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RecurrenceStartTime()
0xe678  call     valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.MaintenanceWindowHelper::FitJobRecurrenceToMaintenanceWindow(valuetype [mscorlib]System.DateTime)
0xe67d  stloc.1
0xe67e  ldloca.s 1
0xe680  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0xe685  brfalse.s loc_E6AA
0xe687  ldarg.0
0xe688  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass2_0::asyncEvent
0xe68d  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RecurrencePattern()
0xe692  ldloca.s 1
0xe694  ldarg.0
0xe695  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass2_0::asyncEvent
0xe69a  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_RecurrenceStartTime()
0xe69f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::GetValueOrDefault(!!T0)
0xe6a4  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRescheduleEventResult::.ctor(string, valuetype [mscorlib]System.DateTime)
0xe6a9  ret
0xe6aa  ldloc.0
0xe6ab  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.ReindexInfo::get_Output()
0xe6b0  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor(string)
0xe6b5  ret
```
