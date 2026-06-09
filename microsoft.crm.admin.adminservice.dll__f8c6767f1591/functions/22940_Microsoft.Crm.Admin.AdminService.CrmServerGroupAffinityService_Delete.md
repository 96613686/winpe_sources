# Microsoft.Crm.Admin.AdminService.CrmServerGroupAffinityService::Delete

- ea: `0x22940`
- end: `0x22a27`
- name: `Microsoft.Crm.Admin.AdminService.CrmServerGroupAffinityService::Delete`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x17610`

## callees

- `0x1cb80`
- `0x1cc20`
- `0x22500`
- `0x22580`
- `0x227f0`
- `0x22940`

## string_xrefs

- `0x22983`: `Delete`
- `0x229f7`: `Delete`
- `0x22988`: `D:\a\1\s\src\CrmLive\Admin\ServerGroupAffinity\CrmServerGroupAffinityService.cs`
- `0x229fc`: `D:\a\1\s\src\CrmLive\Admin\ServerGroupAffinity\CrmServerGroupAffinityService.cs`
- `0x22952`: `Delete(affinityId={0})`

## pseudocode

```c

```

## disassembly

```asm
0x22940  ldarg.1
0x22941  ldstr    aAffinityid// "affinityId"
0x22946  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2294b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x22950  ldc.i4.s 0x14
0x22952  ldstr    aDeleteAffinity// "Delete(affinityId={0})"
0x22957  ldc.i4.1
0x22958  newarr   [mscorlib]System.Object
0x2295d  dup
0x2295e  ldc.i4.0
0x2295f  ldarg.1
0x22960  box      [mscorlib]System.Guid
0x22965  stelem.ref
0x22966  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2296b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x22970  stloc.0
0x22971  ldloc.0
0x22972  ldstr    aServergroupaff// "ServerGroupAffinity"
0x22977  ldarg.1
0x22978  box      [mscorlib]System.Guid
0x2297d  ldnull
0x2297e  ldc.i4   0xA2
0x22983  ldstr    aDelete// "Delete"
0x22988  ldstr    aDA1SSrcCrmlive_44// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Serve"...
0x2298d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x22992  brtrue.s loc_229B8
0x22994  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22999  ldstr    aNoServerGroupA_0// "No server group affinity with Guid {0}"
0x2299e  ldc.i4.1
0x2299f  newarr   [mscorlib]System.Object
0x229a4  dup
0x229a5  ldc.i4.0
0x229a6  ldarg.1
0x229a7  box      [mscorlib]System.Guid
0x229ac  stelem.ref
0x229ad  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x229b2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x229b7  throw
0x229b8  ldloc.0
0x229b9  ldc.i4.2
0x229ba  ldc.i4   0x1000
0x229bf  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmTransaction [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::BeginTransaction(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope, valuetype [System.Data]System.Data.IsolationLevel)
0x229c4  stloc.1
0x229c5  ldarg.0
0x229c6  ldarg.1
0x229c7  call     instance class Microsoft.Crm.Admin.AdminService.ServerGroupAffinityData Microsoft.Crm.Admin.AdminService.CrmServerGroupAffinityService::Retrieve(valuetype [mscorlib]System.Guid id)
0x229cc  stloc.2
0x229cd  ldloc.2
0x229ce  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerGroupAffinityType Microsoft.Crm.Admin.AdminService.ServerGroupAffinityData::get_AffinityType()
0x229d3  ldc.i4.1
0x229d4  bne.un.s loc_229E6
0x229d6  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmOrganizationGroupService::.ctor()
0x229db  ldloc.2
0x229dc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ServerGroupAffinityData::get_GroupId()
0x229e1  call     instance void Microsoft.Crm.Admin.AdminService.CrmOrganizationGroupService::Delete(valuetype [mscorlib]System.Guid groupId)
0x229e6  ldloc.0
0x229e7  ldstr    aServergroupaff// "ServerGroupAffinity"
0x229ec  ldarg.1
0x229ed  box      [mscorlib]System.Guid
0x229f2  ldc.i4   0xB8
0x229f7  ldstr    aDelete// "Delete"
0x229fc  ldstr    aDA1SSrcCrmlive_44// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Serve"...
0x22a01  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x22a06  leave.s  loc_22A26
0x22a08  pop
0x22a09  ldloc.1
0x22a0a  ldc.i4.0
0x22a0b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ICrmTransaction::RollbackTransaction(bool)
0x22a10  rethrow
0x22a12  ldloc.1
0x22a13  brfalse.s loc_22A1B
0x22a15  ldloc.1
0x22a16  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22a1b  endfinally
0x22a1c  ldloc.0
0x22a1d  brfalse.s loc_22A25
0x22a1f  ldloc.0
0x22a20  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22a25  endfinally
0x22a26  ret
```
