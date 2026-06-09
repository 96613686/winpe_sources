# Microsoft.Crm.Admin.AdminService.CrmOrganizationService::DeleteOrganizationRelatedRecords

- ea: `0x25fb0`
- end: `0x26072`
- name: `Microsoft.Crm.Admin.AdminService.CrmOrganizationService::DeleteOrganizationRelatedRecords`
- size: `194`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x25fb0`

## string_xrefs

- `0x26027`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`
- `0x25fd4`: `Hard deleting records from table {0} for organization {1} in config db.`
- `0x26022`: `DeleteOrganizationRelatedRecords`
- `0x26038`: `Error while deleting records from table {0} for organization {1} in config db : {2}`

## pseudocode

```c

```

## disassembly

```asm
0x25fb0  ldarg.1
0x25fb1  ldstr    aTablename// "tableName"
0x25fb6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x25fbb  ldarg.2
0x25fbc  ldstr    aOrganizationco// "organizationColumnName"
0x25fc1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x25fc6  ldarg.3
0x25fc7  ldstr    aOrganizationid// "organizationId"
0x25fcc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x25fd1  ldarg.3
0x25fd2  ldc.i4.s 0xA
0x25fd4  ldstr    aHardDeletingRe// "Hard deleting records from table {0} fo"...
0x25fd9  ldc.i4.2
0x25fda  newarr   [mscorlib]System.Object
0x25fdf  dup
0x25fe0  ldc.i4.0
0x25fe1  ldarg.1
0x25fe2  stelem.ref
0x25fe3  dup
0x25fe4  ldc.i4.1
0x25fe5  ldarga.s 3
0x25fe7  constrained. [mscorlib]System.Guid
0x25fed  callvirt instance string [mscorlib]System.Object::ToString()
0x25ff2  stelem.ref
0x25ff3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25ff8  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x25ffd  stloc.0
0x25ffe  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x26003  stloc.1
0x26004  ldloc.1
0x26005  ldarg.2
0x26006  ldarg.3
0x26007  box      [mscorlib]System.Guid
0x2600c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x26011  ldloc.0
0x26012  ldarg.1
0x26013  ldc.i4.1
0x26014  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x26019  dup
0x2601a  ldc.i4.0
0x2601b  ldloc.1
0x2601c  stelem.ref
0x2601d  ldc.i4   0x15A
0x26022  ldstr    aDeleteorganiza// "DeleteOrganizationRelatedRecords"
0x26027  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2602c  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x26031  pop
0x26032  leave.s  loc_26071
0x26034  stloc.2
0x26035  ldarg.3
0x26036  ldc.i4.s 0xA
0x26038  ldstr    aErrorWhileDele// "Error while deleting records from table"...
0x2603d  ldc.i4.3
0x2603e  newarr   [mscorlib]System.Object
0x26043  dup
0x26044  ldc.i4.0
0x26045  ldarg.1
0x26046  stelem.ref
0x26047  dup
0x26048  ldc.i4.1
0x26049  ldarga.s 3
0x2604b  constrained. [mscorlib]System.Guid
0x26051  callvirt instance string [mscorlib]System.Object::ToString()
0x26056  stelem.ref
0x26057  dup
0x26058  ldc.i4.2
0x26059  ldloc.2
0x2605a  callvirt instance string [mscorlib]System.Object::ToString()
0x2605f  stelem.ref
0x26060  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x26065  leave.s  loc_26071
0x26067  ldloc.0
0x26068  brfalse.s loc_26070
0x2606a  ldloc.0
0x2606b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26070  endfinally
0x26071  ret
```
