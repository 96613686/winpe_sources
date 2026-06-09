# Microsoft.Crm.Admin.AdminService.CrmCertificateService::CreateInternal

- ea: `0x18de0`
- end: `0x18e79`
- name: `Microsoft.Crm.Admin.AdminService.CrmCertificateService::CreateInternal`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18860`
- `0x18af0`

## callees

- `0x18790`
- `0x18de0`
- `0x195a0`

## string_xrefs

- `0x18df7`: `CreateInternal`
- `0x18dfc`: `D:\a\1\s\src\CrmLive\Admin\Certificates\CrmCertificateService.cs`
- `0x18e4b`: `Created Certificate, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x18de0  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x18de5  stloc.0
0x18de6  ldloc.0
0x18de7  ldstr    aCertificates// "Certificates"
0x18dec  ldarg.0
0x18ded  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x18df2  ldc.i4   0x156
0x18df7  ldstr    aCreateinternal// "CreateInternal"
0x18dfc  ldstr    aDA1SSrcCrmlive_34// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Certi"...
0x18e01  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x18e06  unbox.any [mscorlib]System.Guid
0x18e0b  stloc.1
0x18e0c  ldarg.0
0x18e0d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CertificateData::get_Id()
0x18e12  ldloc.1
0x18e13  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x18e18  brfalse.s loc_18E25
0x18e1a  ldstr    aCertificateIds// "Certificate Ids must be equal"
0x18e1f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x18e24  throw
0x18e25  ldc.i4.s 0x38
0x18e27  ldarg.0
0x18e28  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CertificateData::get_Id()
0x18e2d  stloc.2
0x18e2e  ldloca.s 2
0x18e30  ldstr    aB// "B"
0x18e35  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18e3a  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x18e3f  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireNonOrganizationSpecificEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string)
0x18e44  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x18e49  ldc.i4.s 0x14
0x18e4b  ldstr    aCreatedCertifi// "Created Certificate, Id=({0})"
0x18e50  ldc.i4.1
0x18e51  newarr   [mscorlib]System.Object
0x18e56  dup
0x18e57  ldc.i4.0
0x18e58  ldarg.0
0x18e59  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CertificateData::get_Id()
0x18e5e  box      [mscorlib]System.Guid
0x18e63  stelem.ref
0x18e64  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18e69  ldarg.0
0x18e6a  stloc.3
0x18e6b  leave.s  loc_18E77
0x18e6d  ldloc.0
0x18e6e  brfalse.s loc_18E76
0x18e70  ldloc.0
0x18e71  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18e76  endfinally
0x18e77  ldloc.3
0x18e78  ret
```
