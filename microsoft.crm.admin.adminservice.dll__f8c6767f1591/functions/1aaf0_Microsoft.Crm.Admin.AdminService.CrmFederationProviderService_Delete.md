# Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::Delete

- ea: `0x1aaf0`
- end: `0x1abb4`
- name: `Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::Delete`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1aaf0`

## string_xrefs

- `0x1ab32`: `Delete`
- `0x1ab37`: `D:\a\1\s\src\CrmLive\Admin\FederationProvider\CrmFederationProviderService.cs`
- `0x1ab60`: `Deleted FederationProvider, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x1aaf0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1aaf5  ldc.i4.s 0x14
0x1aaf7  ldstr    aDeletingFedera// "Deleting FederationProvider, Id=({0})"
0x1aafc  ldc.i4.1
0x1aafd  newarr   [mscorlib]System.Object
0x1ab02  dup
0x1ab03  ldc.i4.0
0x1ab04  ldarg.1
0x1ab05  box      [mscorlib]System.Guid
0x1ab0a  stelem.ref
0x1ab0b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ab10  ldarg.1
0x1ab11  ldstr    aFederationprov_0// "FederationProvider identifier"
0x1ab16  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1ab1b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1ab20  stloc.0
0x1ab21  ldloc.0
0x1ab22  ldstr    aFederationprov_1// "FederationProvider"
0x1ab27  ldarg.1
0x1ab28  box      [mscorlib]System.Guid
0x1ab2d  ldc.i4   0xA9
0x1ab32  ldstr    aDelete// "Delete"
0x1ab37  ldstr    aDA1SSrcCrmlive_36// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Feder"...
0x1ab3c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x1ab41  ldc.i4.s 0x37
0x1ab43  ldarga.s 1
0x1ab45  ldstr    aB// "B"
0x1ab4a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ab4f  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x1ab54  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireNonOrganizationSpecificEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string)
0x1ab59  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1ab5e  ldc.i4.s 0x14
0x1ab60  ldstr    aDeletedFederat// "Deleted FederationProvider, Id=({0})"
0x1ab65  ldc.i4.1
0x1ab66  newarr   [mscorlib]System.Object
0x1ab6b  dup
0x1ab6c  ldc.i4.0
0x1ab6d  ldarg.1
0x1ab6e  box      [mscorlib]System.Guid
0x1ab73  stelem.ref
0x1ab74  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ab79  leave.s  loc_1AB85
0x1ab7b  ldloc.0
0x1ab7c  brfalse.s loc_1AB84
0x1ab7e  ldloc.0
0x1ab7f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ab84  endfinally
0x1ab85  leave.s  loc_1ABB3
0x1ab87  stloc.1
0x1ab88  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1ab8d  ldc.i4.s 0x14
0x1ab8f  ldstr    aExceptionDelet_0// "Exception deleting FederationProvider, "...
0x1ab94  ldc.i4.2
0x1ab95  newarr   [mscorlib]System.Object
0x1ab9a  dup
0x1ab9b  ldc.i4.0
0x1ab9c  ldarg.1
0x1ab9d  box      [mscorlib]System.Guid
0x1aba2  stelem.ref
0x1aba3  dup
0x1aba4  ldc.i4.1
0x1aba5  ldloc.1
0x1aba6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1abab  stelem.ref
0x1abac  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1abb1  rethrow
0x1abb3  ret
```
