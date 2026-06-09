# Microsoft.Crm.Admin.AdminService.CrmCertificateService::Update

- ea: `0x19470`
- end: `0x19546`
- name: `Microsoft.Crm.Admin.AdminService.CrmCertificateService::Update`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18860`

## callees

- `0x18790`
- `0x19470`

## string_xrefs

- `0x194c3`: `Update`
- `0x194c8`: `D:\a\1\s\src\CrmLive\Admin\Certificates\CrmCertificateService.cs`
- `0x194f2`: `Updated Certificate, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x19470  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x19475  ldc.i4.s 0x14
0x19477  ldstr    aUpdatingCertif_0// "Updating Certificate property, Id=({0})"...
0x1947c  ldc.i4.1
0x1947d  newarr   [mscorlib]System.Object
0x19482  dup
0x19483  ldc.i4.0
0x19484  ldarg.1
0x19485  box      [mscorlib]System.Guid
0x1948a  stelem.ref
0x1948b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19490  ldarg.1
0x19491  ldstr    aCertificateIde// "Certificate identifier"
0x19496  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1949b  ldarg.2
0x1949c  ldstr    aCertificatedat// "CertificateData"
0x194a1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x194a6  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x194ab  stloc.0
0x194ac  ldloc.0
0x194ad  ldstr    aCertificates// "Certificates"
0x194b2  ldarg.1
0x194b3  box      [mscorlib]System.Guid
0x194b8  ldarg.2
0x194b9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x194be  ldc.i4   0x29A
0x194c3  ldstr    aUpdate// "Update"
0x194c8  ldstr    aDA1SSrcCrmlive_34// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Certi"...
0x194cd  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x194d2  pop
0x194d3  ldc.i4.s 0x39
0x194d5  ldarga.s 1
0x194d7  ldstr    aB// "B"
0x194dc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x194e1  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x194e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireNonOrganizationSpecificEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string)
0x194eb  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x194f0  ldc.i4.s 0x14
0x194f2  ldstr    aUpdatedCertifi// "Updated Certificate, Id=({0})"
0x194f7  ldc.i4.1
0x194f8  newarr   [mscorlib]System.Object
0x194fd  dup
0x194fe  ldc.i4.0
0x194ff  ldarg.1
0x19500  box      [mscorlib]System.Guid
0x19505  stelem.ref
0x19506  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1950b  leave.s  loc_19517
0x1950d  ldloc.0
0x1950e  brfalse.s loc_19516
0x19510  ldloc.0
0x19511  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19516  endfinally
0x19517  leave.s  loc_19545
0x19519  stloc.1
0x1951a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1951f  ldc.i4.s 0x14
0x19521  ldstr    aExceptionInUpd// "Exception in updating Certificate Id=({"...
0x19526  ldc.i4.2
0x19527  newarr   [mscorlib]System.Object
0x1952c  dup
0x1952d  ldc.i4.0
0x1952e  ldarg.1
0x1952f  box      [mscorlib]System.Guid
0x19534  stelem.ref
0x19535  dup
0x19536  ldc.i4.1
0x19537  ldloc.1
0x19538  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1953d  stelem.ref
0x1953e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19543  rethrow
0x19545  ret
```
