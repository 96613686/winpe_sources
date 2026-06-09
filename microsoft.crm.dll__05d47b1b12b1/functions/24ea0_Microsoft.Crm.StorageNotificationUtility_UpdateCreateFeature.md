# Microsoft.Crm.StorageNotificationUtility::UpdateCreateFeature

- ea: `0x24ea0`
- end: `0x24fad`
- name: `Microsoft.Crm.StorageNotificationUtility::UpdateCreateFeature`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x24fb0`

## callees

- `0x24ea0`
- `0x25610`

## string_xrefs

- `0x24f05`: `UpdateCreateFeature`
- `0x24f85`: `UpdateCreateFeature`

## pseudocode

```c

```

## disassembly

```asm
0x24ea0  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationFeature::CreateEntity
0x24ea5  stloc.0
0x24ea6  ldc.i4.0
0x24ea7  stloc.1
0x24ea8  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x24ead  stloc.2
0x24eae  ldloca.s 3
0x24eb0  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x24eb6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x24ebb  stloc.s  4
0x24ebd  ldloc.s  4
0x24ebf  ldstr    aOrganizationid// "OrganizationId"
0x24ec4  ldarg.0
0x24ec5  box      [mscorlib]System.Guid
0x24eca  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x24ecf  ldloc.s  4
0x24ed1  ldstr    aFeatureid// "FeatureId"
0x24ed6  ldloc.0
0x24ed7  box      [mscorlib]System.Guid
0x24edc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x24ee1  ldloc.2
0x24ee2  ldstr    aOrganizationfe// "OrganizationFeatureMap"
0x24ee7  ldc.i4.1
0x24ee8  newarr   [mscorlib]System.String
0x24eed  dup
0x24eee  ldc.i4.0
0x24eef  ldstr    aEnabled// "Enabled"
0x24ef4  stelem.ref
0x24ef5  ldc.i4.1
0x24ef6  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x24efb  dup
0x24efc  ldc.i4.0
0x24efd  ldloc.s  4
0x24eff  stelem.ref
0x24f00  ldc.i4   0x235
0x24f05  ldstr    aUpdatecreatefe// "UpdateCreateFeature"
0x24f0a  ldstr    aDA1SSrcSharedS_4// "D:\\a\\1\\s\\src\\Shared\\Server\\Utils"...
0x24f0f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x24f14  stloc.s  5
0x24f16  ldloc.s  5
0x24f18  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x24f1d  brtrue.s loc_24F41
0x24f1f  ldloca.s 3
0x24f21  ldloc.s  5
0x24f23  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x24f28  call     T0x2B000021
0x24f2d  ldstr    aEnabled// "Enabled"
0x24f32  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x24f37  unbox.any [mscorlib]System.Boolean
0x24f3c  call     instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x24f41  ldloca.s 3
0x24f43  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x24f48  brfalse.s loc_24F97
0x24f4a  ldloca.s 3
0x24f4c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x24f51  ldarg.1
0x24f52  beq.s    loc_24F97
0x24f54  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x24f59  stloc.s  6
0x24f5b  ldloc.s  6
0x24f5d  ldstr    aEnabled// "Enabled"
0x24f62  ldarg.1
0x24f63  box      [mscorlib]System.Boolean
0x24f68  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x24f6d  ldloc.2
0x24f6e  ldstr    aOrganizationfe// "OrganizationFeatureMap"
0x24f73  ldloc.s  6
0x24f75  ldc.i4.1
0x24f76  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x24f7b  dup
0x24f7c  ldc.i4.0
0x24f7d  ldloc.s  4
0x24f7f  stelem.ref
0x24f80  ldc.i4   0x240
0x24f85  ldstr    aUpdatecreatefe// "UpdateCreateFeature"
0x24f8a  ldstr    aDA1SSrcSharedS_4// "D:\\a\\1\\s\\src\\Shared\\Server\\Utils"...
0x24f8f  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x24f94  pop
0x24f95  ldc.i4.1
0x24f96  stloc.1
0x24f97  ldloc.1
0x24f98  brfalse.s loc_24FA0
0x24f9a  ldarg.0
0x24f9b  call     void Microsoft.Crm.StorageNotificationUtility::FireNotification(valuetype [mscorlib]System.Guid orgId)
0x24fa0  leave.s  loc_24FAC
0x24fa2  ldloc.2
0x24fa3  brfalse.s loc_24FAB
0x24fa5  ldloc.2
0x24fa6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24fab  endfinally
0x24fac  ret
```
