# Microsoft.Crm.CrmLive.Services.ServiceComponentSkuService::RetrieveOrganizationsBySku

- ea: `0x125b0`
- end: `0x1268f`
- name: `Microsoft.Crm.CrmLive.Services.ServiceComponentSkuService::RetrieveOrganizationsBySku`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x12040`
- `0x12460`
- `0x124f0`
- `0x125b0`

## string_xrefs

- `0x125ca`: `ServiceComponentId`
- `0x1261b`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceComponentSkuService.cs`
- `0x125f4`: `ServiceInstance`

## pseudocode

```c

```

## disassembly

```asm
0x125b0  ldarg.0
0x125b1  ldarg.1
0x125b2  call     instance bool Microsoft.Crm.CrmLive.Services.ServiceComponentSkuService::IsValidSku(string skuName)
0x125b7  brtrue.s loc_125BB
0x125b9  ldnull
0x125ba  ret
0x125bb  ldarg.0
0x125bc  ldarg.1
0x125bd  call     instance class Microsoft.Crm.CrmLive.Services.ServiceComponentSku Microsoft.Crm.CrmLive.Services.ServiceComponentSkuService::RetrieveServiceComponentSkuByDescription(string description)
0x125c2  stloc.0
0x125c3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x125c8  stloc.1
0x125c9  ldloc.1
0x125ca  ldstr    aServicecompone// "ServiceComponentId"
0x125cf  ldloc.0
0x125d0  callvirt instance string Microsoft.Crm.CrmLive.Services.ServiceComponentSku::get_ServiceComponentId()
0x125d5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x125da  ldloc.1
0x125db  ldstr    aStatuscode// "StatusCode"
0x125e0  ldc.i4.1
0x125e1  box      [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.ServiceInstanceStatus
0x125e6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x125eb  ldnull
0x125ec  stloc.2
0x125ed  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x125f2  stloc.3
0x125f3  ldloc.3
0x125f4  ldstr    aServiceinstanc// "ServiceInstance"
0x125f9  ldc.i4.1
0x125fa  newarr   [mscorlib]System.String
0x125ff  dup
0x12600  ldc.i4.0
0x12601  ldstr    aOrganizationid_0// "OrganizationId"
0x12606  stelem.ref
0x12607  ldc.i4.1
0x12608  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x1260d  dup
0x1260e  ldc.i4.0
0x1260f  ldloc.1
0x12610  stelem.ref
0x12611  ldc.i4   0xF8
0x12616  ldstr    aRetrieveorgani_0// "RetrieveOrganizationsBySku"
0x1261b  ldstr    aDA1SSrcCrmlive_24// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x12620  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x12625  stloc.2
0x12626  leave.s  loc_12632
0x12628  ldloc.3
0x12629  brfalse.s loc_12631
0x1262b  ldloc.3
0x1262c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12631  endfinally
0x12632  ldloc.2
0x12633  brfalse.s loc_1268D
0x12635  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x1263a  stloc.s  4
0x1263c  ldloc.2
0x1263d  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x12642  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x12647  stloc.s  5
0x12649  br.s     loc_1266C
0x1264b  ldloca.s 5
0x1264d  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x12652  stloc.s  6
0x12654  ldloc.s  4
0x12656  ldloc.s  6
0x12658  ldstr    aOrganizationid_0// "OrganizationId"
0x1265d  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x12662  unbox.any [mscorlib]System.Guid
0x12667  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x1266c  ldloca.s 5
0x1266e  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x12673  brtrue.s loc_1264B
0x12675  leave.s  loc_12685
0x12677  ldloca.s 5
0x12679  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x1267f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12684  endfinally
0x12685  ldloc.s  4
0x12687  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x1268c  ret
0x1268d  ldnull
0x1268e  ret
```
