# Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::UpdateContextId

- ea: `0x10df0`
- end: `0x10eea`
- name: `Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::UpdateContextId`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x10ef0`

## callees

- `0x10df0`

## string_xrefs

- `0x10e64`: `D:\a\1\s\src\CrmLive\Admin\OrganizationLifecycle\OrganizationLifecycleService.cs`
- `0x10e92`: `D:\a\1\s\src\CrmLive\Admin\OrganizationLifecycle\OrganizationLifecycleService.cs`
- `0x10e5f`: `UpdateContextId`
- `0x10e8d`: `UpdateContextId`

## pseudocode

```c

```

## disassembly

```asm
0x10df0  ldarg.1
0x10df1  ldstr    aOrgid// "orgId"
0x10df6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x10dfb  ldarga.s 2
0x10dfd  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x10e02  brfalse.s loc_10E15
0x10e04  ldarga.s 2
0x10e06  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x10e0b  ldstr    aContextid_0// "contextId"
0x10e10  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x10e15  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x10e1a  stloc.0
0x10e1b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x10e20  stloc.1
0x10e21  ldloc.1
0x10e22  ldstr    aContextid// "ContextId"
0x10e27  ldarg.2
0x10e28  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x10e2d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x10e32  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x10e37  stloc.2
0x10e38  ldloc.2
0x10e39  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x10e3e  ldarg.1
0x10e3f  box      [mscorlib]System.Guid
0x10e44  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x10e49  ldloc.0
0x10e4a  ldstr    aOrganizationli// "OrganizationLifecycle"
0x10e4f  ldloc.1
0x10e50  ldc.i4.1
0x10e51  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x10e56  dup
0x10e57  ldc.i4.0
0x10e58  ldloc.2
0x10e59  stelem.ref
0x10e5a  ldc.i4   0x253
0x10e5f  ldstr    aUpdatecontexti// "UpdateContextId"
0x10e64  ldstr    aDA1SSrcCrmlive_21// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x10e69  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x10e6e  pop
0x10e6f  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x10e74  ldstr    aOrganizationli// "OrganizationLifecycle"
0x10e79  ldc.i4.1
0x10e7a  newarr   [mscorlib]System.String
0x10e7f  dup
0x10e80  ldc.i4.0
0x10e81  ldstr    aId// "Id"
0x10e86  stelem.ref
0x10e87  ldloc.2
0x10e88  ldc.i4   0x25A
0x10e8d  ldstr    aUpdatecontexti// "UpdateContextId"
0x10e92  ldstr    aDA1SSrcCrmlive_21// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x10e97  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x10e9c  stloc.3
0x10e9d  ldarg.3
0x10e9e  brfalse.s loc_10EDD
0x10ea0  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x10ea5  ldstr    aOrganizationli// "OrganizationLifecycle"
0x10eaa  ldloc.3
0x10eab  ldstr    aId// "Id"
0x10eb0  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x10eb5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Flush(string, object)
0x10eba  ldc.i4.s 0x1F
0x10ebc  ldarga.s 1
0x10ebe  ldstr    aB// "B"
0x10ec3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10ec8  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x10ecd  ldarg.1
0x10ece  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x10ed3  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10ed8  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::Kick()
0x10edd  leave.s  loc_10EE9
0x10edf  ldloc.0
0x10ee0  brfalse.s loc_10EE8
0x10ee2  ldloc.0
0x10ee3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10ee8  endfinally
0x10ee9  ret
```
