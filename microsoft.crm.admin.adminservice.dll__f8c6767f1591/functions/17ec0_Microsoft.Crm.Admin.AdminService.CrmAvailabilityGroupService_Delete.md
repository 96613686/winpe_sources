# Microsoft.Crm.Admin.AdminService.CrmAvailabilityGroupService::Delete

- ea: `0x17ec0`
- end: `0x17f3e`
- name: `Microsoft.Crm.Admin.AdminService.CrmAvailabilityGroupService::Delete`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x17ec0`

## string_xrefs

- `0x17f02`: `Delete`
- `0x17f07`: `D:\a\1\s\src\CrmLive\Admin\AvailabilityGroup\CrmAvailabilityGroupService.cs`
- `0x17f18`: `Deleted AvailabilityGroup, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x17ec0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x17ec5  ldc.i4.s 9
0x17ec7  ldstr    aDeletingAvaila// "Deleting AvailabilityGroup, Id=({0})"
0x17ecc  ldc.i4.1
0x17ecd  newarr   [mscorlib]System.Object
0x17ed2  dup
0x17ed3  ldc.i4.0
0x17ed4  ldarg.1
0x17ed5  box      [mscorlib]System.Guid
0x17eda  stelem.ref
0x17edb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x17ee0  ldarg.1
0x17ee1  ldstr    aAvailabilitygr_5// "AvailabilityGroup identifier"
0x17ee6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x17eeb  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x17ef0  stloc.0
0x17ef1  ldloc.0
0x17ef2  ldstr    aAvailabilitygr_4// "AvailabilityGroups"
0x17ef7  ldarg.1
0x17ef8  box      [mscorlib]System.Guid
0x17efd  ldc.i4   0x8F
0x17f02  ldstr    aDelete// "Delete"
0x17f07  ldstr    aDA1SSrcCrmlive_33// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Avail"...
0x17f0c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x17f11  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x17f16  ldc.i4.s 9
0x17f18  ldstr    aDeletedAvailab// "Deleted AvailabilityGroup, Id=({0})"
0x17f1d  ldc.i4.1
0x17f1e  newarr   [mscorlib]System.Object
0x17f23  dup
0x17f24  ldc.i4.0
0x17f25  ldarg.1
0x17f26  box      [mscorlib]System.Guid
0x17f2b  stelem.ref
0x17f2c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x17f31  leave.s  loc_17F3D
0x17f33  ldloc.0
0x17f34  brfalse.s loc_17F3C
0x17f36  ldloc.0
0x17f37  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17f3c  endfinally
0x17f3d  ret
```
