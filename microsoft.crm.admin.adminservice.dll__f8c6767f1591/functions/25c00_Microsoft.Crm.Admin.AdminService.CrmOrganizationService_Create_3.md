# Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Create_3

- ea: `0x25c00`
- end: `0x25e44`
- name: `Microsoft.Crm.Admin.AdminService.CrmOrganizationService::Create_3`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x25af0`

## callees

- `0x18790`
- `0x25c00`
- `0x27f40`
- `0x27fa0`
- `0x27fc0`
- `0x27fe0`
- `0x285a0`
- `0x285e0`
- `0x28620`
- `0x286e0`
- `0x28950`
- `0x295b0`
- `0x29740`
- `0x2a210`
- `0x2a2e0`

## string_xrefs

- `0x25d6a`: `Create`
- `0x25d3d`: `PostProvisionComplete`
- `0x25d6f`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`
- `0x25dba`: `Created Organization, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x25c00  ldarg.1
0x25c01  ldstr    aOrganizationda_6// "organizationData"
0x25c06  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x25c0b  ldarg.1
0x25c0c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x25c11  stloc.0
0x25c12  ldloc.0
0x25c13  ldc.i4.s 0x14
0x25c15  ldstr    aCreatingOrgani// "Creating Organization, UniqueName=({0})"
0x25c1a  ldc.i4.1
0x25c1b  newarr   [mscorlib]System.Object
0x25c20  dup
0x25c21  ldc.i4.0
0x25c22  ldarg.1
0x25c23  callvirt instance string Microsoft.Crm.Admin.AdminService.OrganizationData::get_UniqueName()
0x25c28  stelem.ref
0x25c29  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25c2e  ldloc.0
0x25c2f  ldstr    aOrganizationId_1// "Organization identifier"
0x25c34  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x25c39  ldarg.0
0x25c3a  ldarg.1
0x25c3b  callvirt instance string Microsoft.Crm.Admin.AdminService.OrganizationData::get_UniqueName()
0x25c40  call     instance void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::ThrowIfNotValidUniqueName(string uniqueName)
0x25c45  ldarg.0
0x25c46  ldarg.1
0x25c47  callvirt instance string Microsoft.Crm.Admin.AdminService.OrganizationData::get_FriendlyName()
0x25c4c  call     instance void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::ThrowIfNotValidFriendlyName(string friendlyName)
0x25c51  ldarg.1
0x25c52  callvirt instance string Microsoft.Crm.Admin.AdminService.OrganizationData::get_SqlServerName()
0x25c57  ldstr    aSqlservername_0// "sqlServerName"
0x25c5c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x25c61  ldarg.1
0x25c62  callvirt instance string Microsoft.Crm.Admin.AdminService.OrganizationData::get_DatabaseName()
0x25c67  ldstr    aDatabasename_0// "databaseName"
0x25c6c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x25c71  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x25c76  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x25c7b  ldc.i4.1
0x25c7c  bne.un.s loc_25C96
0x25c7e  ldstr    aTraceenabled// "TraceEnabled"
0x25c83  ldc.i4.0
0x25c84  box      [mscorlib]System.Boolean
0x25c89  ldarg.1
0x25c8a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x25c8f  call     void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x25c94  br.s     loc_25CAC
0x25c96  ldstr    aTraceenabled// "TraceEnabled"
0x25c9b  ldc.i4.1
0x25c9c  box      [mscorlib]System.Boolean
0x25ca1  ldarg.1
0x25ca2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x25ca7  call     void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x25cac  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x25cb1  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x25cb6  ldc.i4.2
0x25cb7  beq.s    loc_25CD5
0x25cb9  ldstr    aS2srealm// "S2SRealm"
0x25cbe  ldloca.s 0
0x25cc0  ldstr    aD// "D"
0x25cc5  call     instance string [mscorlib]System.Guid::ToString(string)
0x25cca  ldarg.1
0x25ccb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x25cd0  call     void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x25cd5  ldstr    aTracecallstack// "TraceCallStack"
0x25cda  ldc.i4.1
0x25cdb  box      [mscorlib]System.Boolean
0x25ce0  ldarg.1
0x25ce1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x25ce6  call     void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x25ceb  ldstr    aTracecategorie// "TraceCategories"
0x25cf0  ldstr    aError// "*:Error"
0x25cf5  ldarg.1
0x25cf6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x25cfb  call     void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x25d00  ldstr    aMaxstoragesize// "MaxStorageSizeMb"
0x25d05  ldarg.1
0x25d06  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Admin.AdminService.OrganizationData::get_IsBackedByXdb()
0x25d0b  stloc.1
0x25d0c  ldloca.s 1
0x25d0e  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x25d13  brtrue.s loc_25D18
0x25d15  ldc.i4.0
0x25d16  br.s     loc_25D1F
0x25d18  ldloca.s 1
0x25d1a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x25d1f  brtrue.s loc_25D28
0x25d21  ldc.i4   0x400
0x25d26  br.s     loc_25D2D
0x25d28  ldc.i4   0x3E800
0x25d2d  box      [mscorlib]System.Int32
0x25d32  ldarg.1
0x25d33  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x25d38  call     void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x25d3d  ldstr    aPostprovisionc// "PostProvisionComplete"
0x25d42  ldc.i4.0
0x25d43  box      [mscorlib]System.Boolean
0x25d48  ldarg.1
0x25d49  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x25d4e  call     void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::AddPropertyIfMissing(string propertyName, object value, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x25d53  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x25d58  stloc.2
0x25d59  ldloc.2
0x25d5a  ldstr    aOrganization// "Organization"
0x25d5f  ldarg.1
0x25d60  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x25d65  ldc.i4   0xF6
0x25d6a  ldstr    aCreate// "Create"
0x25d6f  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x25d74  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x25d79  unbox.any [mscorlib]System.Guid
0x25d7e  stloc.3
0x25d7f  ldloc.0
0x25d80  ldloc.3
0x25d81  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x25d86  brfalse.s loc_25D93
0x25d88  ldstr    aOrganizationId_2// "Organization Ids must be equal"
0x25d8d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x25d92  throw
0x25d93  ldloc.0
0x25d94  ldloc.2
0x25d95  call     void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::CreateOrganizationFeatures(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService cfg)
0x25d9a  call     class Microsoft.Crm.Admin.AdminService.IOrganizationMaintenanceJobs Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::NewService()
0x25d9f  ldloc.0
0x25da0  ldarg.1
0x25da1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.OrganizationData::get_ScaleGroupId()
0x25da6  callvirt instance void Microsoft.Crm.Admin.AdminService.IOrganizationMaintenanceJobs::CreateJobs(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid scaleGroupId)
0x25dab  leave.s  loc_25DB7
0x25dad  ldloc.2
0x25dae  brfalse.s loc_25DB6
0x25db0  ldloc.2
0x25db1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25db6  endfinally
0x25db7  ldloc.0
0x25db8  ldc.i4.s 0x14
0x25dba  ldstr    aCreatedOrganiz// "Created Organization, Id=({0})"
0x25dbf  ldc.i4.1
0x25dc0  newarr   [mscorlib]System.Object
0x25dc5  dup
0x25dc6  ldc.i4.0
0x25dc7  ldloc.0
0x25dc8  box      [mscorlib]System.Guid
0x25dcd  stelem.ref
0x25dce  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25dd3  ldc.i4.s 0x1D
0x25dd5  ldloca.s 0
0x25dd7  ldstr    aB// "B"
0x25ddc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25de1  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x25de6  ldloc.0
0x25de7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x25dec  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x25df1  ldloc.0
0x25df2  ldc.i4.s 0x14
0x25df4  ldstr    aFiredNotificat// "Fired Notification: {0} For Organizatio"...
0x25df9  ldc.i4.2
0x25dfa  newarr   [mscorlib]System.Object
0x25dff  dup
0x25e00  ldc.i4.0
0x25e01  ldc.i4.s 0x1D
0x25e03  box      [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType
0x25e08  stelem.ref
0x25e09  dup
0x25e0a  ldc.i4.1
0x25e0b  ldloc.0
0x25e0c  box      [mscorlib]System.Guid
0x25e11  stelem.ref
0x25e12  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25e17  leave.s  loc_25E43
0x25e19  stloc.s  4
0x25e1b  ldloc.0
0x25e1c  ldc.i4.s 0x14
0x25e1e  ldstr    aExceptionCreat_7// "Exception creating Organization, Unique"...
0x25e23  ldc.i4.2
0x25e24  newarr   [mscorlib]System.Object
0x25e29  dup
0x25e2a  ldc.i4.0
0x25e2b  ldarg.1
0x25e2c  callvirt instance string Microsoft.Crm.Admin.AdminService.OrganizationData::get_UniqueName()
0x25e31  stelem.ref
0x25e32  dup
0x25e33  ldc.i4.1
0x25e34  ldloc.s  4
0x25e36  callvirt instance string [mscorlib]System.Exception::get_Message()
0x25e3b  stelem.ref
0x25e3c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25e41  rethrow
0x25e43  ret
```
