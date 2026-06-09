# Microsoft.Crm.Admin.AdminService.CrmAsyncGroupService::Delete

- ea: `0x17610`
- end: `0x176f3`
- name: `Microsoft.Crm.Admin.AdminService.CrmAsyncGroupService::Delete`
- size: `227`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x17610`
- `0x22400`
- `0x225e0`
- `0x225f0`
- `0x22860`
- `0x22940`
- `0x22a30`

## string_xrefs

- `0x17630`: `Delete`
- `0x176c3`: `Delete`
- `0x17635`: `D:\a\1\s\src\CrmLive\Admin\AsyncGroup\CrmAsyncGroupService.cs`
- `0x176c8`: `D:\a\1\s\src\CrmLive\Admin\AsyncGroup\CrmAsyncGroupService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x17610  ldarg.1
0x17611  ldstr    aGroupid_0// "groupId"
0x17616  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1761b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x17620  stloc.0
0x17621  ldloc.0
0x17622  ldstr    aAsyncgroup// "AsyncGroup"
0x17627  ldarg.1
0x17628  box      [mscorlib]System.Guid
0x1762d  ldnull
0x1762e  ldc.i4.s 0x56
0x17630  ldstr    aDelete// "Delete"
0x17635  ldstr    aDA1SSrcCrmlive_32// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Async"...
0x1763a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x1763f  brtrue.s loc_17665
0x17641  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17646  ldstr    aNoAsyncGroupWi// "no async group with Guid {0}"
0x1764b  ldc.i4.1
0x1764c  newarr   [mscorlib]System.Object
0x17651  dup
0x17652  ldc.i4.0
0x17653  ldarg.1
0x17654  box      [mscorlib]System.Guid
0x17659  stelem.ref
0x1765a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1765f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x17664  throw
0x17665  ldloc.0
0x17666  ldc.i4.2
0x17667  ldc.i4   0x1000
0x1766c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmTransaction [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::BeginTransaction(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope, valuetype [System.Data]System.Data.IsolationLevel)
0x17671  stloc.1
0x17672  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmServerGroupAffinityService::.ctor()
0x17677  stloc.2
0x17678  newobj   instance void Microsoft.Crm.Admin.AdminService.ServerGroupAffinityFilter::.ctor()
0x1767d  stloc.3
0x1767e  ldloc.3
0x1767f  ldarg.1
0x17680  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerGroupAffinityFilter::set_OwningGroupId(valuetype [mscorlib]System.Guid value)
0x17685  ldloc.2
0x17686  ldloc.3
0x17687  callvirt instance class Microsoft.Crm.Admin.AdminService.ServerGroupAffinityData[] Microsoft.Crm.Admin.AdminService.CrmServerGroupAffinityService::RetrieveMultiple(class Microsoft.Crm.Admin.AdminService.ServerGroupAffinityFilter filter)
0x1768c  stloc.s  4
0x1768e  ldc.i4.0
0x1768f  stloc.s  5
0x17691  br.s     loc_176AD
0x17693  ldloc.s  4
0x17695  ldloc.s  5
0x17697  ldelem.ref
0x17698  stloc.s  6
0x1769a  ldloc.2
0x1769b  ldloc.s  6
0x1769d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ServerGroupAffinityData::get_Id()
0x176a2  callvirt instance void Microsoft.Crm.Admin.AdminService.CrmServerGroupAffinityService::Delete(valuetype [mscorlib]System.Guid affinityId)
0x176a7  ldloc.s  5
0x176a9  ldc.i4.1
0x176aa  add
0x176ab  stloc.s  5
0x176ad  ldloc.s  5
0x176af  ldloc.s  4
0x176b1  ldlen
0x176b2  conv.i4
0x176b3  blt.s    loc_17693
0x176b5  ldloc.0
0x176b6  ldstr    aAsyncgroup// "AsyncGroup"
0x176bb  ldarg.1
0x176bc  box      [mscorlib]System.Guid
0x176c1  ldc.i4.s 0x6B
0x176c3  ldstr    aDelete// "Delete"
0x176c8  ldstr    aDA1SSrcCrmlive_32// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Async"...
0x176cd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x176d2  leave.s  loc_176F2
0x176d4  pop
0x176d5  ldloc.1
0x176d6  ldc.i4.0
0x176d7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ICrmTransaction::RollbackTransaction(bool)
0x176dc  rethrow
0x176de  ldloc.1
0x176df  brfalse.s loc_176E7
0x176e1  ldloc.1
0x176e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x176e7  endfinally
0x176e8  ldloc.0
0x176e9  brfalse.s loc_176F1
0x176eb  ldloc.0
0x176ec  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x176f1  endfinally
0x176f2  ret
```
