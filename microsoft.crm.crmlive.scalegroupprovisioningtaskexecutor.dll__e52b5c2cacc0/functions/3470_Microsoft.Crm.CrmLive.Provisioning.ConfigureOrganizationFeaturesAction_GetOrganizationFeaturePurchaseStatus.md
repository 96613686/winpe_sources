# Microsoft.Crm.CrmLive.Provisioning.ConfigureOrganizationFeaturesAction::GetOrganizationFeaturePurchaseStatus

- ea: `0x3470`
- end: `0x360f`
- name: `Microsoft.Crm.CrmLive.Provisioning.ConfigureOrganizationFeaturesAction::GetOrganizationFeaturePurchaseStatus`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x33b0`

## callees

- `0x3470`

## string_xrefs

- `0x348d`: `ServiceComponentSku`
- `0x34a2`: `ServiceComponentId`
- `0x34eb`: `ServiceComponentId`
- `0x34f2`: `ServiceComponentId`
- `0x3521`: `ServiceComponentId`
- `0x358b`: `ServiceComponentId`
- `0x3591`: `ServiceComponentId`
- `0x34af`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\ConfigureOrganizationFeaturesAction.cs`
- `0x3539`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\ConfigureOrganizationFeaturesAction.cs`
- `0x35e7`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\ConfigureOrganizationFeaturesAction.cs`
- `0x3514`: `ServiceInstance`
- `0x35c3`: `ServiceComponentFeatureMap`

## pseudocode

```c

```

## disassembly

```asm
0x3470  ldarg.0
0x3471  ldstr    aOrgid// "orgId"
0x3476  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x347b  ldarg.1
0x347c  ldstr    aFeatureid// "featureId"
0x3481  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x3486  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x348b  stloc.0
0x348c  ldloc.0
0x348d  ldstr    aServicecompone// "ServiceComponentSku"
0x3492  ldc.i4.2
0x3493  newarr   [mscorlib]System.String
0x3498  dup
0x3499  ldc.i4.0
0x349a  ldstr    aName// "Name"
0x349f  stelem.ref
0x34a0  dup
0x34a1  ldc.i4.1
0x34a2  ldstr    aServicecompone_0// "ServiceComponentId"
0x34a7  stelem.ref
0x34a8  ldc.i4.s 0x55
0x34aa  ldstr    aGetorganizatio// "GetOrganizationFeaturePurchaseStatus"
0x34af  ldstr    aDDbsShDccm2110_2// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x34b4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], int32, string, string)
0x34b9  stloc.1
0x34ba  ldnull
0x34bb  stloc.2
0x34bc  ldloc.1
0x34bd  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x34c2  brtrue   loc_3579
0x34c7  ldloc.1
0x34c8  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x34cd  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x34d2  stloc.s  4
0x34d4  br       loc_355D
0x34d9  ldloca.s 4
0x34db  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x34e0  stloc.s  5
0x34e2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x34e7  stloc.s  6
0x34e9  ldloc.s  6
0x34eb  ldstr    aServicecompone_0// "ServiceComponentId"
0x34f0  ldloc.s  5
0x34f2  ldstr    aServicecompone_0// "ServiceComponentId"
0x34f7  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x34fc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3501  ldloc.s  6
0x3503  ldstr    aOrganizationid_0// "OrganizationId"
0x3508  ldarg.0
0x3509  box      [mscorlib]System.Guid
0x350e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x3513  ldloc.0
0x3514  ldstr    aServiceinstanc// "ServiceInstance"
0x3519  ldc.i4.1
0x351a  newarr   [mscorlib]System.String
0x351f  dup
0x3520  ldc.i4.0
0x3521  ldstr    aServicecompone_0// "ServiceComponentId"
0x3526  stelem.ref
0x3527  ldc.i4.1
0x3528  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x352d  dup
0x352e  ldc.i4.0
0x352f  ldloc.s  6
0x3531  stelem.ref
0x3532  ldc.i4.s 0x61
0x3534  ldstr    aGetorganizatio// "GetOrganizationFeaturePurchaseStatus"
0x3539  ldstr    aDDbsShDccm2110_2// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x353e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x3543  stloc.s  7
0x3545  ldloc.s  7
0x3547  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x354c  brtrue.s loc_355D
0x354e  ldloc.s  7
0x3550  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x3555  call     T0x2B000017
0x355a  stloc.2
0x355b  leave.s  loc_3579
0x355d  ldloca.s 4
0x355f  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x3564  brtrue   loc_34D9
0x3569  leave.s  loc_3579
0x356b  ldloca.s 4
0x356d  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x3573  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3578  endfinally
0x3579  ldloc.2
0x357a  brtrue.s loc_3584
0x357c  ldc.i4.1
0x357d  stloc.s  8
0x357f  leave    loc_360C
0x3584  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3589  stloc.3
0x358a  ldloc.3
0x358b  ldstr    aServicecompone_0// "ServiceComponentId"
0x3590  ldloc.2
0x3591  ldstr    aServicecompone_0// "ServiceComponentId"
0x3596  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x359b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x35a0  ldloc.3
0x35a1  ldstr    aFeatureid_0// "FeatureId"
0x35a6  ldarg.1
0x35a7  box      [mscorlib]System.Guid
0x35ac  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x35b1  ldloc.3
0x35b2  ldstr    aEnabled// "Enabled"
0x35b7  ldc.i4.0
0x35b8  box      [mscorlib]System.Boolean
0x35bd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x35c2  ldloc.0
0x35c3  ldstr    aServicecompone_1// "ServiceComponentFeatureMap"
0x35c8  ldc.i4.1
0x35c9  newarr   [mscorlib]System.String
0x35ce  dup
0x35cf  ldc.i4.0
0x35d0  ldstr    aEnabled// "Enabled"
0x35d5  stelem.ref
0x35d6  ldc.i4.1
0x35d7  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x35dc  dup
0x35dd  ldc.i4.0
0x35de  ldloc.3
0x35df  stelem.ref
0x35e0  ldc.i4.s 0x79
0x35e2  ldstr    aGetorganizatio// "GetOrganizationFeaturePurchaseStatus"
0x35e7  ldstr    aDDbsShDccm2110_2// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x35ec  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x35f1  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x35f6  brfalse.s loc_35FD
0x35f8  ldc.i4.1
0x35f9  stloc.s  8
0x35fb  leave.s  loc_360C
0x35fd  ldc.i4.0
0x35fe  stloc.s  8
0x3600  leave.s  loc_360C
0x3602  ldloc.0
0x3603  brfalse.s loc_360B
0x3605  ldloc.0
0x3606  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x360b  endfinally
0x360c  ldloc.s  8
0x360e  ret
```
