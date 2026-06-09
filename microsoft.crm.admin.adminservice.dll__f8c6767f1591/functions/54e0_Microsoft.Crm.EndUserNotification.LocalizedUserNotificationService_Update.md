# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::Update

- ea: `0x54e0`
- end: `0x5814`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::Update`
- size: `820`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x5370`
- `0x54e0`
- `0x7020`
- `0x7b70`
- `0x7fb0`

## string_xrefs

- `0x55e4`: `Update`
- `0x57cc`: `Update`
- `0x55c7`: `TemplateName`
- `0x5649`: `TemplateName`
- `0x55e9`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationService.cs`
- `0x57d1`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationService.cs`
- `0x552c`: `Cannot submit both notification id and description as update for end user notification`

## pseudocode

```c

```

## disassembly

```asm
0x54e0  ldarga.s 1
0x54e2  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x54e7  brfalse.s loc_5537
0x54e9  ldarga.s 1
0x54eb  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x54f0  brfalse.s loc_5537
0x54f2  ldarg.1
0x54f3  stloc.s  5
0x54f5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x54fa  stloc.s  6
0x54fc  ldloca.s 5
0x54fe  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x5503  brtrue.s loc_5508
0x5505  ldc.i4.1
0x5506  br.s     loc_5522
0x5508  ldloca.s 5
0x550a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x550f  brtrue.s loc_5514
0x5511  ldc.i4.0
0x5512  br.s     loc_5522
0x5514  ldloca.s 5
0x5516  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x551b  ldloc.s  6
0x551d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5522  brfalse.s loc_5537
0x5524  ldarg.2
0x5525  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x552a  brtrue.s loc_5537
0x552c  ldstr    aCannotSubmitBo// "Cannot submit both notification id and "...
0x5531  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5536  throw
0x5537  ldarga.s 1
0x5539  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x553e  brtrue.s loc_5553
0x5540  ldarg.2
0x5541  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5546  brfalse.s loc_5553
0x5548  ldstr    aMustProvideEit// "Must provide either notificationId or d"...
0x554d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5552  throw
0x5553  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x5558  stloc.0
0x5559  ldarga.s 1
0x555b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x5560  brfalse.s loc_5594
0x5562  ldarga.s 1
0x5564  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5569  box      [mscorlib]System.Guid
0x556e  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x5574  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x5579  brtrue.s loc_5594
0x557b  ldloc.0
0x557c  ldstr    aId// "Id"
0x5581  ldarga.s 1
0x5583  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x5588  box      [mscorlib]System.Guid
0x558d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x5592  br.s     loc_55A8
0x5594  ldarg.2
0x5595  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x559a  brtrue.s loc_55A8
0x559c  ldloc.0
0x559d  ldstr    aDescription// "Description"
0x55a2  ldarg.2
0x55a3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x55a8  ldarg.0
0x55a9  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::GetDatabaseService()
0x55ae  stloc.s  7
0x55b0  ldloc.s  7
0x55b2  ldstr    aLocalizedusern// "LocalizedUserNotification"
0x55b7  ldc.i4.3
0x55b8  newarr   [mscorlib]System.String
0x55bd  dup
0x55be  ldc.i4.0
0x55bf  ldstr    aId// "Id"
0x55c4  stelem.ref
0x55c5  dup
0x55c6  ldc.i4.1
0x55c7  ldstr    aTemplatename// "TemplateName"
0x55cc  stelem.ref
0x55cd  dup
0x55ce  ldc.i4.2
0x55cf  ldstr    aVersion// "Version"
0x55d4  stelem.ref
0x55d5  ldc.i4.1
0x55d6  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x55db  dup
0x55dc  ldc.i4.0
0x55dd  ldloc.0
0x55de  stelem.ref
0x55df  ldc.i4   0xB2
0x55e4  ldstr    aUpdate// "Update"
0x55e9  ldstr    aDA1SSrcCrmlive_9// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x55ee  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x55f3  stloc.1
0x55f4  leave.s  loc_5602
0x55f6  ldloc.s  7
0x55f8  brfalse.s loc_5601
0x55fa  ldloc.s  7
0x55fc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5601  endfinally
0x5602  ldloc.1
0x5603  brtrue.s loc_5607
0x5605  ldnull
0x5606  ret
0x5607  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x560c  stloc.2
0x560d  newobj   instance void Microsoft.Crm.EndUserNotification.SlugService::.ctor()
0x5612  stloc.3
0x5613  ldloc.1
0x5614  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x5619  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x561e  stloc.s  8
0x5620  br.s     loc_5672
0x5622  ldloca.s 8
0x5624  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x5629  stloc.s  9
0x562b  ldloc.s  9
0x562d  ldstr    aId// "Id"
0x5632  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5637  unbox.any [mscorlib]System.Guid
0x563c  stloc.s  0xA
0x563e  ldloc.2
0x563f  ldloc.s  0xA
0x5641  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x5646  ldloc.3
0x5647  ldloc.s  9
0x5649  ldstr    aTemplatename// "TemplateName"
0x564e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5653  castclass [mscorlib]System.String
0x5658  ldloc.s  9
0x565a  ldstr    aVersion// "Version"
0x565f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5664  unbox.any [mscorlib]System.Int32
0x5669  ldarg.s  6
0x566b  ldarg.s  7
0x566d  callvirt instance void Microsoft.Crm.EndUserNotification.SlugService::ValidateForUpdate(string templateName, int32 version, string[] parameterNames, string[] parameterValues)
0x5672  ldloca.s 8
0x5674  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x5679  brtrue.s loc_5622
0x567b  leave.s  loc_568B
0x567d  ldloca.s 8
0x567f  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x5685  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x568a  endfinally
0x568b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x5690  stloc.s  4
0x5692  ldloc.s  4
0x5694  ldstr    aModifiedon// "ModifiedOn"
0x5699  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x569e  box      [mscorlib]System.DateTime
0x56a3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x56a8  ldarg.3
0x56a9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x56ae  brtrue.s loc_56BD
0x56b0  ldloc.s  4
0x56b2  ldstr    aDescription// "Description"
0x56b7  ldarg.3
0x56b8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x56bd  ldarga.s 8
0x56bf  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationStatusCode>::get_HasValue()
0x56c4  brfalse.s loc_56E2
0x56c6  ldarga.s 8
0x56c8  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationStatusCode>::get_HasValue()
0x56cd  brfalse.s loc_56E2
0x56cf  ldloc.s  4
0x56d1  ldstr    aStatuscode// "StatusCode"
0x56d6  ldarg.s  8
0x56d8  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationStatusCode>
0x56dd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x56e2  ldarga.s 4
0x56e4  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationTargetType>::get_HasValue()
0x56e9  brfalse  loc_579C
0x56ee  ldarga.s 4
0x56f0  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationTargetType>::get_HasValue()
0x56f5  brfalse  loc_579C
0x56fa  ldarg.s  5
0x56fc  ldstr    aTargetid// "targetId"
0x5701  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x5706  ldarg.s  4
0x5708  stloc.s  0xB
0x570a  ldc.i4.1
0x570b  stloc.s  0xC
0x570d  ldloca.s 0xB
0x570f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationTargetType>::GetValueOrDefault()
0x5714  ldloc.s  0xC
0x5716  ceq
0x5718  ldloca.s 0xB
0x571a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationTargetType>::get_HasValue()
0x571f  and
0x5720  brfalse.s loc_5744
0x5722  ldloc.s  4
0x5724  ldstr    aOrganizationid_0// "OrganizationId"
0x5729  ldarg.s  5
0x572b  box      [mscorlib]System.Guid
0x5730  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x5735  ldloc.s  4
0x5737  ldstr    aScalegroupid_0// "ScaleGroupId"
0x573c  ldnull
0x573d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x5742  br.s     loc_579C
0x5744  ldarg.s  4
0x5746  stloc.s  0xB
0x5748  ldc.i4.2
0x5749  stloc.s  0xC
0x574b  ldloca.s 0xB
0x574d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationTargetType>::GetValueOrDefault()
0x5752  ldloc.s  0xC
0x5754  ceq
0x5756  ldloca.s 0xB
0x5758  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationTargetType>::get_HasValue()
0x575d  and
0x575e  brfalse.s loc_5782
0x5760  ldloc.s  4
0x5762  ldstr    aOrganizationid_0// "OrganizationId"
0x5767  ldnull
0x5768  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x576d  ldloc.s  4
0x576f  ldstr    aScalegroupid_0// "ScaleGroupId"
0x5774  ldarg.s  5
0x5776  box      [mscorlib]System.Guid
0x577b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x5780  br.s     loc_579C
0x5782  ldloc.s  4
0x5784  ldstr    aOrganizationid_0// "OrganizationId"
0x5789  ldnull
0x578a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x578f  ldloc.s  4
0x5791  ldstr    aScalegroupid_0// "ScaleGroupId"
0x5796  ldnull
0x5797  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x579c  ldarg.0
0x579d  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::GetDatabaseService()
0x57a2  stloc.s  0xD
0x57a4  ldloc.2
0x57a5  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x57aa  stloc.s  0xE
0x57ac  br.s     loc_57E8
0x57ae  ldloca.s 0xE
0x57b0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x57b5  stloc.s  0xF
0x57b7  ldloc.s  0xD
0x57b9  ldstr    aLocalizedusern// "LocalizedUserNotification"
0x57be  ldloc.s  0xF
0x57c0  box      [mscorlib]System.Guid
0x57c5  ldloc.s  4
0x57c7  ldc.i4   0xF0
0x57cc  ldstr    aUpdate// "Update"
0x57d1  ldstr    aDA1SSrcCrmlive_9// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x57d6  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x57db  pop
0x57dc  ldarg.0
0x57dd  ldloc.s  0xF
0x57df  ldarg.s  6
0x57e1  ldarg.s  7
0x57e3  call     instance void Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::UpdateParameters(valuetype [mscorlib]System.Guid notificationId, string[] slugNames, string[] slugValues)
0x57e8  ldloca.s 0xE
0x57ea  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x57ef  brtrue.s loc_57AE
0x57f1  leave.s  loc_580D
0x57f3  ldloca.s 0xE
0x57f5  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x57fb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5800  endfinally
0x5801  ldloc.s  0xD
0x5803  brfalse.s loc_580C
0x5805  ldloc.s  0xD
0x5807  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x580c  endfinally
0x580d  ldloc.2
0x580e  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x5813  ret
```
