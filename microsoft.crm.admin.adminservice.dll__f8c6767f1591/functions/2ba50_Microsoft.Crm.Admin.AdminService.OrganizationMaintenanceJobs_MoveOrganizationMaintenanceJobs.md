# Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::MoveOrganizationMaintenanceJobs

- ea: `0x2ba50`
- end: `0x2bbb9`
- name: `Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::MoveOrganizationMaintenanceJobs`
- size: `361`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x2b9e0`
- `0x2ba50`

## string_xrefs

- `0x2ba82`: `Move organization maintenance jobs`
- `0x2bada`: `MoveOrganizationMaintenanceJobs`
- `0x2bb6e`: `MoveOrganizationMaintenanceJobs`
- `0x2bb8a`: `Move maintenance jobs not allowed in non-live environment.`
- `0x2bb9c`: `Exception in move maintenance jobs {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2ba50  ldarg.0
0x2ba51  ldstr    aFromscalegroup// "fromScaleGroup"
0x2ba56  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2ba5b  ldarg.1
0x2ba5c  ldstr    aToscalegroup// "toScaleGroup"
0x2ba61  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2ba66  ldarg.2
0x2ba67  ldstr    aOrganizationid// "organizationId"
0x2ba6c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2ba71  ldarg.0
0x2ba72  ldarg.1
0x2ba73  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2ba78  brfalse.s loc_2BA7F
0x2ba7a  leave    loc_2BBB8
0x2ba7f  ldarg.2
0x2ba80  ldc.i4.s 0x14
0x2ba82  ldstr    aMoveOrganizati// "Move organization maintenance jobs"
0x2ba87  ldc.i4.0
0x2ba88  newarr   [mscorlib]System.Object
0x2ba8d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2ba92  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x2ba97  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x2ba9c  ldc.i4.2
0x2ba9d  bne.un   loc_2BB8A
0x2baa2  ldarg.0
0x2baa3  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService(valuetype [mscorlib]System.Guid)
0x2baa8  stloc.0
0x2baa9  ldnull
0x2baaa  stloc.1
0x2baab  ldnull
0x2baac  stloc.2
0x2baad  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2bab2  stloc.1
0x2bab3  ldloc.1
0x2bab4  ldstr    aOrganizationid_0// "OrganizationId"
0x2bab9  ldarg.2
0x2baba  box      [mscorlib]System.Guid
0x2babf  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2bac4  ldloc.0
0x2bac5  ldstr    aScalegrouporga// "ScaleGroupOrganizationMaintenanceJobs"
0x2baca  ldnull
0x2bacb  ldc.i4.1
0x2bacc  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x2bad1  dup
0x2bad2  ldc.i4.0
0x2bad3  ldloc.1
0x2bad4  stelem.ref
0x2bad5  ldc.i4   0x41D
0x2bada  ldstr    aMoveorganizati// "MoveOrganizationMaintenanceJobs"
0x2badf  ldstr    aDA1SSrcCrmlive_52// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2bae4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x2bae9  stloc.2
0x2baea  leave.s  loc_2BB04
0x2baec  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2baf1  ldstr    aInvalidObjectN// "Invalid object name"
0x2baf6  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2bafb  brfalse.s loc_2BB02
0x2bafd  leave    loc_2BBB8
0x2bb02  rethrow
0x2bb04  ldloc.2
0x2bb05  brfalse.s loc_2BB7E
0x2bb07  ldloc.2
0x2bb08  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x2bb0d  stloc.3
0x2bb0e  br.s     loc_2BB40
0x2bb10  ldloca.s 3
0x2bb12  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x2bb17  stloc.s  5
0x2bb19  ldloca.s 5
0x2bb1b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x2bb20  stloc.s  4
0x2bb22  ldloc.s  4
0x2bb24  ldstr    aId// "Id"
0x2bb29  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x2bb2e  box      [mscorlib]System.Guid
0x2bb33  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2bb38  ldarg.1
0x2bb39  ldloc.s  4
0x2bb3b  call     void Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::Create(valuetype [mscorlib]System.Guid scaleGroup, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2bb40  ldloca.s 3
0x2bb42  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x2bb47  brtrue.s loc_2BB10
0x2bb49  leave.s  loc_2BB59
0x2bb4b  ldloca.s 3
0x2bb4d  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x2bb53  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2bb58  endfinally
0x2bb59  ldloc.0
0x2bb5a  ldstr    aScalegrouporga// "ScaleGroupOrganizationMaintenanceJobs"
0x2bb5f  ldc.i4.1
0x2bb60  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x2bb65  dup
0x2bb66  ldc.i4.0
0x2bb67  ldloc.1
0x2bb68  stelem.ref
0x2bb69  ldc.i4   0x438
0x2bb6e  ldstr    aMoveorganizati// "MoveOrganizationMaintenanceJobs"
0x2bb73  ldstr    aDA1SSrcCrmlive_52// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2bb78  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x2bb7d  pop
0x2bb7e  leave.s  loc_2BB95
0x2bb80  ldloc.0
0x2bb81  brfalse.s loc_2BB89
0x2bb83  ldloc.0
0x2bb84  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2bb89  endfinally
0x2bb8a  ldstr    aMoveMaintenanc// "Move maintenance jobs not allowed in no"...
0x2bb8f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2bb94  throw
0x2bb95  leave.s  loc_2BBB8
0x2bb97  stloc.s  6
0x2bb99  ldarg.2
0x2bb9a  ldc.i4.s 0x14
0x2bb9c  ldstr    aExceptionInMov_3// "Exception in move maintenance jobs {0}"
0x2bba1  ldc.i4.1
0x2bba2  newarr   [mscorlib]System.Object
0x2bba7  dup
0x2bba8  ldc.i4.0
0x2bba9  ldloc.s  6
0x2bbab  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2bbb0  stelem.ref
0x2bbb1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2bbb6  rethrow
0x2bbb8  ret
```
