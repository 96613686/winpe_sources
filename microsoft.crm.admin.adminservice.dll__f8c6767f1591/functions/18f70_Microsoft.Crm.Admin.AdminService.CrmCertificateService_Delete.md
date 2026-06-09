# Microsoft.Crm.Admin.AdminService.CrmCertificateService::Delete

- ea: `0x18f70`
- end: `0x19034`
- name: `Microsoft.Crm.Admin.AdminService.CrmCertificateService::Delete`
- size: `196`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18e80`
- `0x18f30`

## callees

- `0x18f70`

## string_xrefs

- `0x18fb2`: `Delete`
- `0x18fb7`: `D:\a\1\s\src\CrmLive\Admin\Certificates\CrmCertificateService.cs`
- `0x18fe0`: `Deleted Certificate, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x18f70  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x18f75  ldc.i4.s 0x14
0x18f77  ldstr    aDeletingCertif_0// "Deleting Certificate, Id=({0})"
0x18f7c  ldc.i4.1
0x18f7d  newarr   [mscorlib]System.Object
0x18f82  dup
0x18f83  ldc.i4.0
0x18f84  ldarg.1
0x18f85  box      [mscorlib]System.Guid
0x18f8a  stelem.ref
0x18f8b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18f90  ldarg.1
0x18f91  ldstr    aCertificateIde// "Certificate identifier"
0x18f96  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x18f9b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x18fa0  stloc.0
0x18fa1  ldloc.0
0x18fa2  ldstr    aCertificates// "Certificates"
0x18fa7  ldarg.1
0x18fa8  box      [mscorlib]System.Guid
0x18fad  ldc.i4   0x1AF
0x18fb2  ldstr    aDelete// "Delete"
0x18fb7  ldstr    aDA1SSrcCrmlive_34// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Certi"...
0x18fbc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x18fc1  ldc.i4.s 0x3A
0x18fc3  ldarga.s 1
0x18fc5  ldstr    aB// "B"
0x18fca  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18fcf  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x18fd4  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireNonOrganizationSpecificEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string)
0x18fd9  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x18fde  ldc.i4.s 0x14
0x18fe0  ldstr    aDeletedCertifi// "Deleted Certificate, Id=({0})"
0x18fe5  ldc.i4.1
0x18fe6  newarr   [mscorlib]System.Object
0x18feb  dup
0x18fec  ldc.i4.0
0x18fed  ldarg.1
0x18fee  box      [mscorlib]System.Guid
0x18ff3  stelem.ref
0x18ff4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18ff9  leave.s  loc_19005
0x18ffb  ldloc.0
0x18ffc  brfalse.s loc_19004
0x18ffe  ldloc.0
0x18fff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19004  endfinally
0x19005  leave.s  loc_19033
0x19007  stloc.1
0x19008  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1900d  ldc.i4.s 0x14
0x1900f  ldstr    aExceptionDelet// "Exception deleting Certificate, Id=({0}"...
0x19014  ldc.i4.2
0x19015  newarr   [mscorlib]System.Object
0x1901a  dup
0x1901b  ldc.i4.0
0x1901c  ldarg.1
0x1901d  box      [mscorlib]System.Guid
0x19022  stelem.ref
0x19023  dup
0x19024  ldc.i4.1
0x19025  ldloc.1
0x19026  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1902b  stelem.ref
0x1902c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19031  rethrow
0x19033  ret
```
