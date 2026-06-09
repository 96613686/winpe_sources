# Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::SetLastUserLicenseStorageChangeTime

- ea: `0xfa50`
- end: `0xfb15`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::SetLastUserLicenseStorageChangeTime`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xf840`

## callees

- `0xfa50`

## string_xrefs

- `0xfa8d`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SyncData\SyncSubscribedPlanAction.cs`
- `0xfab4`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SyncData\SyncSubscribedPlanAction.cs`
- `0xfac7`: `Update LastUserLicenseStorageChange to {0}.`
- `0xfaf6`: `UpdateStorageObject`

## pseudocode

```c

```

## disassembly

```asm
0xfa50  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xfa55  stloc.0
0xfa56  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xfa5b  stloc.1
0xfa5c  ldloc.1
0xfa5d  ldstr    aLastuserlicens// "LastUserLicenseStorageChange"
0xfa62  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xfa67  box      [mscorlib]System.DateTime
0xfa6c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xfa71  ldloc.0
0xfa72  ldstr    aOrganization// "Organization"
0xfa77  ldarg.0
0xfa78  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::_orgId
0xfa7d  box      [mscorlib]System.Guid
0xfa82  ldloc.1
0xfa83  ldc.i4   0x104
0xfa88  ldstr    aSetlastuserlic// "SetLastUserLicenseStorageChangeTime"
0xfa8d  ldstr    aDDbsShDccm2110_20// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xfa92  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xfa97  pop
0xfa98  ldloc.0
0xfa99  ldstr    aOrganization// "Organization"
0xfa9e  ldarg.0
0xfa9f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::_orgId
0xfaa4  box      [mscorlib]System.Guid
0xfaa9  ldloc.1
0xfaaa  ldc.i4   0x105
0xfaaf  ldstr    aSetlastuserlic// "SetLastUserLicenseStorageChangeTime"
0xfab4  ldstr    aDDbsShDccm2110_20// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xfab9  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xfabe  ldc.i4.0
0xfabf  cgt
0xfac1  stloc.2
0xfac2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfac7  ldstr    aUpdateLastuser// "Update LastUserLicenseStorageChange to "...
0xfacc  ldc.i4.1
0xfacd  newarr   [mscorlib]System.Object
0xfad2  dup
0xfad3  ldc.i4.0
0xfad4  ldloc.1
0xfad5  ldstr    aLastuserlicens// "LastUserLicenseStorageChange"
0xfada  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xfadf  stelem.ref
0xfae0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xfae5  stloc.3
0xfae6  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.AuditHistory::NewService()
0xfaeb  ldarg.0
0xfaec  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::_orgId
0xfaf1  ldstr    aOrganizationId// "Organization.Id"
0xfaf6  ldstr    aUpdatestorageo// "UpdateStorageObject"
0xfafb  ldloc.3
0xfafc  ldloc.2
0xfafd  ldarg.0
0xfafe  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncSubscribedPlanAction::_orgId
0xfb03  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CreateCompletedEntry(valuetype [mscorlib]System.Guid, string, string, string, bool, valuetype [mscorlib]System.Guid)
0xfb08  leave.s  loc_FB14
0xfb0a  ldloc.0
0xfb0b  brfalse.s loc_FB13
0xfb0d  ldloc.0
0xfb0e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfb13  endfinally
0xfb14  ret
```
