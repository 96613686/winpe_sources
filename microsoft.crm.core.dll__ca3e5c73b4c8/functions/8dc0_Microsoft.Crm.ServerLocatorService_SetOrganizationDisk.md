# Microsoft.Crm.ServerLocatorService::SetOrganizationDisk

- ea: `0x8dc0`
- end: `0x8ea9`
- name: `Microsoft.Crm.ServerLocatorService::SetOrganizationDisk`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x8370`
- `0x8dc0`
- `0xbfa0`
- `0x1be90`
- `0x44400`
- `0x44510`
- `0x4af90`
- `0x4d750`
- `0x4e650`
- `0x62500`

## string_xrefs

- `0x8e3c`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x8e4f`: `Update storage objects (object, value): ({0}, {1}) ({2}, {3}).`
- `0x8e8e`: `UpdateStorageObject`

## pseudocode

```c

```

## disassembly

```asm
0x8dc0  ldarg.1
0x8dc1  ldstr    aOrganizationid_0// "organizationId"
0x8dc6  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x8dcb  ldc.i4.2
0x8dcc  ldarg.0
0x8dcd  call     instance valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.ServerLocatorService::GetSku()
0x8dd2  beq.s    loc_8DD5
0x8dd4  ret
0x8dd5  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x8dda  stloc.0
0x8ddb  ldloc.0
0x8ddc  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0x8de1  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x8de6  stloc.1
0x8de7  ldloc.1
0x8de8  ldstr    aId// "Id"
0x8ded  ldarg.1
0x8dee  box      [mscorlib]System.Guid
0x8df3  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8df8  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x8dfd  stloc.2
0x8dfe  ldloc.2
0x8dff  ldstr    aLogsizemb// "LogSizeMB"
0x8e04  ldarg.3
0x8e05  box      [mscorlib]System.Int32
0x8e0a  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8e0f  ldloc.2
0x8e10  ldstr    aUnallocatedspa// "UnallocatedSpaceSizeMB"
0x8e15  ldarg.2
0x8e16  box      [mscorlib]System.Int32
0x8e1b  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8e20  ldloc.0
0x8e21  ldstr    aOrganization// "Organization"
0x8e26  ldloc.2
0x8e27  ldc.i4.1
0x8e28  newarr   Microsoft.Crm.Data.PropertyBag
0x8e2d  dup
0x8e2e  ldc.i4.0
0x8e2f  ldloc.1
0x8e30  stelem.ref
0x8e31  ldc.i4.0
0x8e32  ldc.i4   0x5D5
0x8e37  ldstr    aSetorganizatio_1// "SetOrganizationDisk"
0x8e3c  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x8e41  callvirt instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Update(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, class Microsoft.Crm.Data.PropertyBag[] conditions, bool fireNotification, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x8e46  ldc.i4.0
0x8e47  cgt
0x8e49  stloc.3
0x8e4a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e4f  ldstr    aUpdateStorageO// "Update storage objects (object, value):"...
0x8e54  ldc.i4.4
0x8e55  newarr   [mscorlib]System.Object
0x8e5a  dup
0x8e5b  ldc.i4.0
0x8e5c  ldstr    aLogsizemb// "LogSizeMB"
0x8e61  stelem.ref
0x8e62  dup
0x8e63  ldc.i4.1
0x8e64  ldarg.3
0x8e65  box      [mscorlib]System.Int32
0x8e6a  stelem.ref
0x8e6b  dup
0x8e6c  ldc.i4.2
0x8e6d  ldstr    aUnallocatedspa// "UnallocatedSpaceSizeMB"
0x8e72  stelem.ref
0x8e73  dup
0x8e74  ldc.i4.3
0x8e75  ldarg.2
0x8e76  box      [mscorlib]System.Int32
0x8e7b  stelem.ref
0x8e7c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8e81  stloc.s  4
0x8e83  call     class Microsoft.Crm.ConfigurationDatabase.IAuditHistory Microsoft.Crm.ConfigurationDatabase.AuditHistory::NewService()
0x8e88  ldarg.1
0x8e89  ldstr    aOrganizationId// "Organization.Id"
0x8e8e  ldstr    aUpdatestorageo// "UpdateStorageObject"
0x8e93  ldloc.s  4
0x8e95  ldloc.3
0x8e96  ldarg.1
0x8e97  callvirt instance void Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CreateCompletedEntry(valuetype [mscorlib]System.Guid objectId, string objectType, string operation, string details, bool succeeded, valuetype [mscorlib]System.Guid organizationId)
0x8e9c  leave.s  loc_8EA8
0x8e9e  ldloc.0
0x8e9f  brfalse.s loc_8EA7
0x8ea1  ldloc.0
0x8ea2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ea7  endfinally
0x8ea8  ret
```
