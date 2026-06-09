# Microsoft.Crm.CrmLive.Services.ServiceComponentSkuService::RetrieveByOrganization_0

- ea: `0x12310`
- end: `0x12417`
- name: `Microsoft.Crm.CrmLive.Services.ServiceComponentSkuService::RetrieveByOrganization_0`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x122f0`

## callees

- `0x120e0`
- `0x12310`

## string_xrefs

- `0x12379`: `ServiceComponentId`
- `0x1237f`: `ServiceComponentId`
- `0x12322`: `ServiceComponentSku`
- `0x1232f`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceComponentSkuService.cs`
- `0x123cf`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceComponentSkuService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x12310  ldarg.1
0x12311  ldstr    aOrganizationid// "organizationId"
0x12316  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1231b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x12320  stloc.0
0x12321  ldloc.0
0x12322  ldstr    aServicecompone_4// "ServiceComponentSku"
0x12327  ldnull
0x12328  ldc.i4.s 0x40
0x1232a  ldstr    aRetrievebyorga// "RetrieveByOrganization"
0x1232f  ldstr    aDA1SSrcCrmlive_24// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x12334  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], int32, string, string)
0x12339  stloc.1
0x1233a  ldloc.1
0x1233b  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x12340  brtrue   loc_12406
0x12345  ldloc.1
0x12346  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x1234b  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x12350  stloc.2
0x12351  br       loc_123EA
0x12356  ldloca.s 2
0x12358  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x1235d  stloc.3
0x1235e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x12363  stloc.s  4
0x12365  ldloc.s  4
0x12367  ldstr    aOrganizationid_0// "OrganizationId"
0x1236c  ldarg.1
0x1236d  box      [mscorlib]System.Guid
0x12372  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12377  ldloc.s  4
0x12379  ldstr    aServicecompone// "ServiceComponentId"
0x1237e  ldloc.3
0x1237f  ldstr    aServicecompone// "ServiceComponentId"
0x12384  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x12389  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1238e  ldarg.2
0x1238f  brfalse.s loc_123A9
0x12391  ldloc.s  4
0x12393  ldstr    aCount// "Count"
0x12398  ldc.i4.1
0x12399  ldc.i4.0
0x1239a  box      [mscorlib]System.Int32
0x1239f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x123a4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x123a9  ldloc.0
0x123aa  ldstr    aOrganizationre// "OrganizationResources"
0x123af  ldc.i4.1
0x123b0  newarr   [mscorlib]System.String
0x123b5  dup
0x123b6  ldc.i4.0
0x123b7  ldstr    aId// "Id"
0x123bc  stelem.ref
0x123bd  ldc.i4.1
0x123be  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x123c3  dup
0x123c4  ldc.i4.0
0x123c5  ldloc.s  4
0x123c7  stelem.ref
0x123c8  ldc.i4.s 0x4F
0x123ca  ldstr    aRetrievebyorga// "RetrieveByOrganization"
0x123cf  ldstr    aDA1SSrcCrmlive_24// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x123d4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x123d9  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x123de  brtrue.s loc_123EA
0x123e0  ldloc.3
0x123e1  call     class Microsoft.Crm.CrmLive.Services.ServiceComponentSku Microsoft.Crm.CrmLive.Services.ServiceComponentSku::FromPropertyBag(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag propBag)
0x123e6  stloc.s  5
0x123e8  leave.s  loc_12414
0x123ea  ldloca.s 2
0x123ec  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x123f1  brtrue   loc_12356
0x123f6  leave.s  loc_12412
0x123f8  ldloca.s 2
0x123fa  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x12400  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12405  endfinally
0x12406  leave.s  loc_12412
0x12408  ldloc.0
0x12409  brfalse.s loc_12411
0x1240b  ldloc.0
0x1240c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12411  endfinally
0x12412  ldnull
0x12413  ret
0x12414  ldloc.s  5
0x12416  ret
```
