# Microsoft.Crm.Admin.AdminService.CrmServerService::Delete

- ea: `0x20b10`
- end: `0x20c04`
- name: `Microsoft.Crm.Admin.AdminService.CrmServerService::Delete`
- size: `244`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x17850`
- `0x20b10`
- `0x21180`

## string_xrefs

- `0x20b82`: `Delete`
- `0x20b87`: `D:\a\1\s\src\CrmLive\Admin\Server\CrmServerService.cs`
- `0x20bb0`: `Deleted Server, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x20b10  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x20b15  ldc.i4.s 0x14
0x20b17  ldstr    aDeletingServer// "Deleting Server, Id=({0})"
0x20b1c  ldc.i4.1
0x20b1d  newarr   [mscorlib]System.Object
0x20b22  dup
0x20b23  ldc.i4.0
0x20b24  ldarg.1
0x20b25  box      [mscorlib]System.Guid
0x20b2a  stelem.ref
0x20b2b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20b30  ldarg.1
0x20b31  ldstr    aServerIdentifi// "Server identifier"
0x20b36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x20b3b  ldc.i4.2
0x20b3c  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x20b41  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x20b46  bne.un.s loc_20B6B
0x20b48  ldarg.0
0x20b49  ldarg.1
0x20b4a  call     instance valuetype Microsoft.Crm.Admin.AdminService.ServerState Microsoft.Crm.Admin.AdminService.CrmServerService::GetState(valuetype [mscorlib]System.Guid serverId)
0x20b4f  stloc.0
0x20b50  ldc.i4.1
0x20b51  ldloc.0
0x20b52  bne.un.s loc_20B6B
0x20b54  ldstr    aServer_1// "Server"
0x20b59  ldarg.1
0x20b5a  box      [mscorlib]System.Guid
0x20b5f  ldloc.0
0x20b60  box      Microsoft.Crm.Admin.AdminService.ServerState
0x20b65  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBCannotDeleteObjectDueState(string objectType, object value, class [mscorlib]System.Enum state)
0x20b6a  throw
0x20b6b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x20b70  stloc.1
0x20b71  ldloc.1
0x20b72  ldstr    aServer_1// "Server"
0x20b77  ldarg.1
0x20b78  box      [mscorlib]System.Guid
0x20b7d  ldc.i4   0x16A
0x20b82  ldstr    aDelete// "Delete"
0x20b87  ldstr    aDA1SSrcCrmlive_43// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Serve"...
0x20b8c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x20b91  ldc.i4.s 0x2D
0x20b93  ldarga.s 1
0x20b95  ldstr    aB// "B"
0x20b9a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20b9f  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x20ba4  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireNonOrganizationSpecificEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string)
0x20ba9  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x20bae  ldc.i4.s 0x14
0x20bb0  ldstr    aDeletedServerI// "Deleted Server, Id=({0})"
0x20bb5  ldc.i4.1
0x20bb6  newarr   [mscorlib]System.Object
0x20bbb  dup
0x20bbc  ldc.i4.0
0x20bbd  ldarg.1
0x20bbe  box      [mscorlib]System.Guid
0x20bc3  stelem.ref
0x20bc4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20bc9  leave.s  loc_20BD5
0x20bcb  ldloc.1
0x20bcc  brfalse.s loc_20BD4
0x20bce  ldloc.1
0x20bcf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20bd4  endfinally
0x20bd5  leave.s  loc_20C03
0x20bd7  stloc.2
0x20bd8  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x20bdd  ldc.i4.s 0x14
0x20bdf  ldstr    aExceptionDelet_4// "Exception deleting Server, Id=({0} : {1"...
0x20be4  ldc.i4.2
0x20be5  newarr   [mscorlib]System.Object
0x20bea  dup
0x20beb  ldc.i4.0
0x20bec  ldarg.1
0x20bed  box      [mscorlib]System.Guid
0x20bf2  stelem.ref
0x20bf3  dup
0x20bf4  ldc.i4.1
0x20bf5  ldloc.2
0x20bf6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x20bfb  stelem.ref
0x20bfc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20c01  rethrow
0x20c03  ret
```
