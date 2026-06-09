# Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.SubscribedPlanHelpers::ProvisionOrganizations

- ea: `0x2f550`
- end: `0x2f745`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.SubscribedPlanHelpers::ProvisionOrganizations`
- size: `501`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1d50`
- `0xc0e0`
- `0x2f440`
- `0x2f490`
- `0x2f550`

## string_xrefs

- `0x2f674`: `CrmScaleGroupProvisioningService`
- `0x2f6ae`: `SubscribedPlanHelpers.ProvisionOrganizations has fatally failed to create a provisioning queue item.`
- `0x2f6f1`: `Created organization {0}/{1} of type '{2}'`

## pseudocode

```c

```

## disassembly

```asm
0x2f550  ldarg.0
0x2f551  ldstr    aContextid_0// "contextId"
0x2f556  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2f55b  ldarg.1
0x2f55c  ldstr    aOrganizationpr_2// "organizationProvisioningFrom"
0x2f561  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2f566  ldarg.3
0x2f567  ldstr    aTotallicensedu// "totalLicensedUnits"
0x2f56c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNegative(int32, string)
0x2f571  ldarg.s  4
0x2f573  ldstr    aLogger// "logger"
0x2f578  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2f57d  ldarg.3
0x2f57e  brtrue.s loc_2F581
0x2f580  ret
0x2f581  ldarga.s 0
0x2f583  constrained. [mscorlib]System.Guid
0x2f589  callvirt instance string [mscorlib]System.Object::ToString()
0x2f58e  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IConfigDBLock [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigDBLock::NewLock(string)
0x2f593  stloc.0
0x2f594  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::.ctor()
0x2f599  stloc.1
0x2f59a  ldarg.1
0x2f59b  stloc.2
0x2f59c  ldloc.1
0x2f59d  ldarg.0
0x2f59e  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::GetPrimaryOrganizationByContextId(valuetype [mscorlib]System.Guid)
0x2f5a3  stloc.3
0x2f5a4  ldloca.s 3
0x2f5a6  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x2f5ab  brtrue.s loc_2F5B0
0x2f5ad  ldc.i4.0
0x2f5ae  br.s     loc_2F5BD
0x2f5b0  ldloc.2
0x2f5b1  ldloca.s 3
0x2f5b3  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x2f5b8  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2f5bd  brfalse  loc_2F738
0x2f5c2  ldarg.s  4
0x2f5c4  ldstr    aCheckingToAddA// "Checking to add additional instances of"...
0x2f5c9  ldarg.2
0x2f5ca  box      [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType
0x2f5cf  ldstr    aAsThisIsThePri// "' as this is the primary org"
0x2f5d4  call     string [mscorlib]System.String::Concat(object, object, object)
0x2f5d9  callvirt instance void Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.ISubscribedPlanLogger::WriteLine(string data)
0x2f5de  ldloc.1
0x2f5df  ldarg.0
0x2f5e0  ldarg.2
0x2f5e1  call     int32 Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.SubscribedPlanHelpers::RetrieveOrganizationCountByContextIdAndType(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService service, valuetype [mscorlib]System.Guid contextId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType type)
0x2f5e6  stloc.s  4
0x2f5e8  ldarg.s  4
0x2f5ea  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2f5ef  ldstr    aInstanceCountC// "Instance count: Current = [{0}], Desire"...
0x2f5f4  ldc.i4.2
0x2f5f5  newarr   [mscorlib]System.Object
0x2f5fa  dup
0x2f5fb  ldc.i4.0
0x2f5fc  ldloc.s  4
0x2f5fe  box      [mscorlib]System.Int32
0x2f603  stelem.ref
0x2f604  dup
0x2f605  ldc.i4.1
0x2f606  ldarg.3
0x2f607  box      [mscorlib]System.Int32
0x2f60c  stelem.ref
0x2f60d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2f612  callvirt instance void Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.ISubscribedPlanLogger::WriteLine(string data)
0x2f617  ldc.i4.0
0x2f618  stloc.s  5
0x2f61a  ldloc.s  4
0x2f61c  ldarg.3
0x2f61d  ble.s    loc_2F69E
0x2f61f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2f624  ldstr    aContexid0Has1A// "ContexId {0} has {1} additional instanc"...
0x2f629  ldc.i4.3
0x2f62a  newarr   [mscorlib]System.Object
0x2f62f  dup
0x2f630  ldc.i4.0
0x2f631  ldarg.0
0x2f632  box      [mscorlib]System.Guid
0x2f637  stelem.ref
0x2f638  dup
0x2f639  ldc.i4.1
0x2f63a  ldloc.s  4
0x2f63c  box      [mscorlib]System.Int32
0x2f641  stelem.ref
0x2f642  dup
0x2f643  ldc.i4.2
0x2f644  ldarg.3
0x2f645  box      [mscorlib]System.Int32
0x2f64a  stelem.ref
0x2f64b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2f650  stloc.s  8
0x2f652  ldnull
0x2f653  ldarg.1
0x2f654  ldc.i4.s 0xA
0x2f656  ldstr    a0// "{0}"
0x2f65b  ldc.i4.1
0x2f65c  newarr   [mscorlib]System.Object
0x2f661  dup
0x2f662  ldc.i4.0
0x2f663  ldloc.s  8
0x2f665  stelem.ref
0x2f666  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f66b  call     class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::NewEventLog()
0x2f670  stloc.s  9
0x2f672  ldloc.s  9
0x2f674  ldstr    aCrmscalegroupp// "CrmScaleGroupProvisioningService"
0x2f679  ldc.i4.1
0x2f67a  ldc.i4   0xC000460B
0x2f67f  conv.u8
0x2f680  ldc.i4.1
0x2f681  newarr   [mscorlib]System.Object
0x2f686  dup
0x2f687  ldc.i4.0
0x2f688  ldloc.s  8
0x2f68a  stelem.ref
0x2f68b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x2f690  leave.s  loc_2F69E
0x2f692  ldloc.s  9
0x2f694  brfalse.s loc_2F69D
0x2f696  ldloc.s  9
0x2f698  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f69d  endfinally
0x2f69e  ldc.i4.0
0x2f69f  stloc.s  6
0x2f6a1  ldnull
0x2f6a2  stloc.s  7
0x2f6a4  br       loc_2F72D
0x2f6a9  ldloc.s  6
0x2f6ab  ldc.i4.3
0x2f6ac  bne.un.s loc_2F6B9
0x2f6ae  ldstr    aSubscribedplan_2// "SubscribedPlanHelpers.ProvisionOrganiza"...
0x2f6b3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2f6b8  throw
0x2f6b9  ldloc.s  7
0x2f6bb  brtrue.s loc_2F6C6
0x2f6bd  ldarg.0
0x2f6be  ldarg.1
0x2f6bf  call     class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company Microsoft.Crm.CrmLive.Provisioning.SyncData.SubscribedPlanHandler.SubscribedPlanHelpers::GetCompanyObject(valuetype [mscorlib]System.Guid contextId, valuetype [mscorlib]System.Guid organizationId)
0x2f6c4  stloc.s  7
0x2f6c6  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x2f6cb  ldloc.s  7
0x2f6cd  ldarg.2
0x2f6ce  call     class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyHandler::CreateOrganization(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Company company, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType organizationType)
0x2f6d3  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Item1()
0x2f6d8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2f6dd  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2f6e2  brfalse.s loc_2F727
0x2f6e4  ldloc.s  5
0x2f6e6  ldc.i4.1
0x2f6e7  add
0x2f6e8  stloc.s  5
0x2f6ea  ldarg.s  4
0x2f6ec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2f6f1  ldstr    aCreatedOrganiz// "Created organization {0}/{1} of type '{"...
0x2f6f6  ldc.i4.3
0x2f6f7  newarr   [mscorlib]System.Object
0x2f6fc  dup
0x2f6fd  ldc.i4.0
0x2f6fe  ldloc.s  4
0x2f700  ldloc.s  5
0x2f702  add
0x2f703  box      [mscorlib]System.Int32
0x2f708  stelem.ref
0x2f709  dup
0x2f70a  ldc.i4.1
0x2f70b  ldarg.3
0x2f70c  box      [mscorlib]System.Int32
0x2f711  stelem.ref
0x2f712  dup
0x2f713  ldc.i4.2
0x2f714  ldarg.2
0x2f715  box      [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType
0x2f71a  stelem.ref
0x2f71b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2f720  callvirt instance void Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor.Action.SyncData.ISubscribedPlanLogger::WriteLine(string data)
0x2f725  br.s     loc_2F72D
0x2f727  ldloc.s  6
0x2f729  ldc.i4.1
0x2f72a  add
0x2f72b  stloc.s  6
0x2f72d  ldloc.s  4
0x2f72f  ldloc.s  5
0x2f731  add
0x2f732  ldarg.3
0x2f733  blt      loc_2F6A9
0x2f738  leave.s  loc_2F744
0x2f73a  ldloc.0
0x2f73b  brfalse.s loc_2F743
0x2f73d  ldloc.0
0x2f73e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f743  endfinally
0x2f744  ret
```
