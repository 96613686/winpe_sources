# Microsoft.Crm.CrmLive.Services.ServiceInstanceService::TryGetServiceInstanceMatchesSku

- ea: `0x13060`
- end: `0x13181`
- name: `Microsoft.Crm.CrmLive.Services.ServiceInstanceService::TryGetServiceInstanceMatchesSku`
- size: `289`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x129a0`
- `0x12df0`

## callees

- `0x13060`

## string_xrefs

- `0x13074`: `ServiceComponentId`
- `0x130c9`: `ServiceComponentId`
- `0x130cf`: `ServiceComponentId`
- `0x13104`: `ServiceComponentId`
- `0x13067`: `ServiceComponentSku`
- `0x130df`: `ServiceInstance`
- `0x13084`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceInstanceService.cs`
- `0x1312f`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceInstanceService.cs`
- `0x130bc`: `ServiceInstanceId`
- `0x13114`: `ServiceInstanceId`
- `0x1307f`: `TryGetServiceInstanceMatchesSku`
- `0x1312a`: `TryGetServiceInstanceMatchesSku`

## pseudocode

```c

```

## disassembly

```asm
0x13060  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x13065  stloc.0
0x13066  ldloc.0
0x13067  ldstr    aServicecompone_4// "ServiceComponentSku"
0x1306c  ldc.i4.1
0x1306d  newarr   [mscorlib]System.String
0x13072  dup
0x13073  ldc.i4.0
0x13074  ldstr    aServicecompone// "ServiceComponentId"
0x13079  stelem.ref
0x1307a  ldc.i4   0x15E
0x1307f  ldstr    aTrygetservicei_0// "TryGetServiceInstanceMatchesSku"
0x13084  ldstr    aDA1SSrcCrmlive_25// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x13089  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], int32, string, string)
0x1308e  stloc.1
0x1308f  ldloc.1
0x13090  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x13095  brtrue   loc_13170
0x1309a  ldloc.1
0x1309b  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x130a0  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x130a5  stloc.2
0x130a6  br       loc_13154
0x130ab  ldloca.s 2
0x130ad  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x130b2  stloc.3
0x130b3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x130b8  stloc.s  4
0x130ba  ldloc.s  4
0x130bc  ldstr    aServiceinstanc_0// "ServiceInstanceId"
0x130c1  ldarg.0
0x130c2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x130c7  ldloc.s  4
0x130c9  ldstr    aServicecompone// "ServiceComponentId"
0x130ce  ldloc.3
0x130cf  ldstr    aServicecompone// "ServiceComponentId"
0x130d4  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x130d9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x130de  ldloc.0
0x130df  ldstr    aServiceinstanc// "ServiceInstance"
0x130e4  ldc.i4.6
0x130e5  newarr   [mscorlib]System.String
0x130ea  dup
0x130eb  ldc.i4.0
0x130ec  ldstr    aFriendlyname// "FriendlyName"
0x130f1  stelem.ref
0x130f2  dup
0x130f3  ldc.i4.1
0x130f4  ldstr    aId// "Id"
0x130f9  stelem.ref
0x130fa  dup
0x130fb  ldc.i4.2
0x130fc  ldstr    aOrganizationid_0// "OrganizationId"
0x13101  stelem.ref
0x13102  dup
0x13103  ldc.i4.3
0x13104  ldstr    aServicecompone// "ServiceComponentId"
0x13109  stelem.ref
0x1310a  dup
0x1310b  ldc.i4.4
0x1310c  ldstr    aStatuscode// "StatusCode"
0x13111  stelem.ref
0x13112  dup
0x13113  ldc.i4.5
0x13114  ldstr    aServiceinstanc_0// "ServiceInstanceId"
0x13119  stelem.ref
0x1311a  ldc.i4.1
0x1311b  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x13120  dup
0x13121  ldc.i4.0
0x13122  ldloc.s  4
0x13124  stelem.ref
0x13125  ldc.i4   0x169
0x1312a  ldstr    aTrygetservicei_0// "TryGetServiceInstanceMatchesSku"
0x1312f  ldstr    aDA1SSrcCrmlive_25// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x13134  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x13139  stloc.s  5
0x1313b  ldloc.s  5
0x1313d  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x13142  brtrue.s loc_13154
0x13144  ldloc.s  5
0x13146  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x1314b  call     T0x2B00005D
0x13150  stloc.s  6
0x13152  leave.s  loc_1317E
0x13154  ldloca.s 2
0x13156  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x1315b  brtrue   loc_130AB
0x13160  leave.s  loc_1317C
0x13162  ldloca.s 2
0x13164  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x1316a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1316f  endfinally
0x13170  leave.s  loc_1317C
0x13172  ldloc.0
0x13173  brfalse.s loc_1317B
0x13175  ldloc.0
0x13176  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1317b  endfinally
0x1317c  ldnull
0x1317d  ret
0x1317e  ldloc.s  6
0x13180  ret
```
