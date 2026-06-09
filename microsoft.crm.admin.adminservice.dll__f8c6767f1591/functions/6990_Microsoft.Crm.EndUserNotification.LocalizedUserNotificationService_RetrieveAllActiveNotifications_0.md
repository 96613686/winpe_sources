# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::RetrieveAllActiveNotifications_0

- ea: `0x6990`
- end: `0x6be8`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::RetrieveAllActiveNotifications_0`
- size: `600`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x6290`
- `0x6980`

## callees

- `0x6990`
- `0x6bf0`
- `0x6c30`
- `0x6c60`
- `0x3d0e0`

## string_xrefs

- `0x6a1b`: `TemplateName`
- `0x6a34`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationService.cs`
- `0x6a9b`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationService.cs`
- `0x6ad8`: `D:\a\1\s\src\CrmLive\Admin\EndUserNotification\LocalizedUserNotificationService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x6990  ldnull
0x6991  stloc.0
0x6992  ldarg.3
0x6993  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x6998  stloc.1
0x6999  ldarga.s 1
0x699b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationTargetType>::get_HasValue()
0x69a0  brfalse.s loc_69AE
0x69a2  ldarga.s 1
0x69a4  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationTargetType>::get_HasValue()
0x69a9  brtrue   loc_6A44
0x69ae  ldnull
0x69af  stloc.2
0x69b0  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildSiteWideConidtion()
0x69b5  stloc.3
0x69b6  ldarg.2
0x69b7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x69bc  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x69c1  brfalse.s loc_69FA
0x69c3  ldarg.2
0x69c4  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildOrganizationCondition(valuetype [mscorlib]System.Guid organizationId)
0x69c9  stloc.s  4
0x69cb  ldarg.0
0x69cc  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::_context
0x69d1  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x69d6  ldarg.2
0x69d7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetOrganizationScaleGroupId(valuetype [mscorlib]System.Guid)
0x69dc  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildScaleGroupCondition(valuetype [mscorlib]System.Guid scaleGroupId)
0x69e1  stloc.s  5
0x69e3  ldc.i4.3
0x69e4  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x69e9  dup
0x69ea  ldc.i4.0
0x69eb  ldloc.s  4
0x69ed  stelem.ref
0x69ee  dup
0x69ef  ldc.i4.1
0x69f0  ldloc.s  5
0x69f2  stelem.ref
0x69f3  dup
0x69f4  ldc.i4.2
0x69f5  ldloc.3
0x69f6  stelem.ref
0x69f7  stloc.2
0x69f8  br.s     loc_6A05
0x69fa  ldc.i4.1
0x69fb  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x6a00  dup
0x6a01  ldc.i4.0
0x6a02  ldloc.3
0x6a03  stelem.ref
0x6a04  stloc.2
0x6a05  ldloc.1
0x6a06  ldstr    aLocalizedusern// "LocalizedUserNotification"
0x6a0b  ldc.i4.3
0x6a0c  newarr   [mscorlib]System.String
0x6a11  dup
0x6a12  ldc.i4.0
0x6a13  ldstr    aId// "Id"
0x6a18  stelem.ref
0x6a19  dup
0x6a1a  ldc.i4.1
0x6a1b  ldstr    aTemplatename// "TemplateName"
0x6a20  stelem.ref
0x6a21  dup
0x6a22  ldc.i4.2
0x6a23  ldstr    aVersion// "Version"
0x6a28  stelem.ref
0x6a29  ldloc.2
0x6a2a  ldc.i4   0x441
0x6a2f  ldstr    aRetrieveallact// "RetrieveAllActiveNotifications"
0x6a34  ldstr    aDA1SSrcCrmlive_9// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x6a39  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x6a3e  stloc.0
0x6a3f  leave    loc_6AEF
0x6a44  ldarga.s 1
0x6a46  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationTargetType>::get_Value()
0x6a4b  stloc.s  6
0x6a4d  ldloc.s  6
0x6a4f  ldc.i4.1
0x6a50  bne.un.s loc_6AA8
0x6a52  ldarg.2
0x6a53  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildOrganizationCondition(valuetype [mscorlib]System.Guid organizationId)
0x6a58  stloc.s  7
0x6a5a  ldarg.3
0x6a5b  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x6a60  ldarg.2
0x6a61  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetOrganizationScaleGroupId(valuetype [mscorlib]System.Guid)
0x6a66  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildScaleGroupCondition(valuetype [mscorlib]System.Guid scaleGroupId)
0x6a6b  stloc.s  8
0x6a6d  ldloc.1
0x6a6e  ldstr    aLocalizedusern// "LocalizedUserNotification"
0x6a73  ldc.i4.1
0x6a74  newarr   [mscorlib]System.String
0x6a79  dup
0x6a7a  ldc.i4.0
0x6a7b  ldstr    aId// "Id"
0x6a80  stelem.ref
0x6a81  ldc.i4.2
0x6a82  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x6a87  dup
0x6a88  ldc.i4.0
0x6a89  ldloc.s  7
0x6a8b  stelem.ref
0x6a8c  dup
0x6a8d  ldc.i4.1
0x6a8e  ldloc.s  8
0x6a90  stelem.ref
0x6a91  ldc.i4   0x44E
0x6a96  ldstr    aRetrieveallact// "RetrieveAllActiveNotifications"
0x6a9b  ldstr    aDA1SSrcCrmlive_9// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x6aa0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x6aa5  stloc.0
0x6aa6  leave.s  loc_6AEF
0x6aa8  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildSiteWideConidtion()
0x6aad  stloc.s  9
0x6aaf  ldloc.1
0x6ab0  ldstr    aLocalizedusern// "LocalizedUserNotification"
0x6ab5  ldc.i4.1
0x6ab6  newarr   [mscorlib]System.String
0x6abb  dup
0x6abc  ldc.i4.0
0x6abd  ldstr    aId// "Id"
0x6ac2  stelem.ref
0x6ac3  ldc.i4.1
0x6ac4  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x6ac9  dup
0x6aca  ldc.i4.0
0x6acb  ldloc.s  9
0x6acd  stelem.ref
0x6ace  ldc.i4   0x454
0x6ad3  ldstr    aRetrieveallact// "RetrieveAllActiveNotifications"
0x6ad8  ldstr    aDA1SSrcCrmlive_9// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\EndUs"...
0x6add  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x6ae2  stloc.0
0x6ae3  leave.s  loc_6AEF
0x6ae5  ldloc.1
0x6ae6  brfalse.s loc_6AEE
0x6ae8  ldloc.1
0x6ae9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6aee  endfinally
0x6aef  ldloc.0
0x6af0  brfalse  loc_6BE6
0x6af5  newobj   instance void <>c__DisplayClass40_0::.ctor()
0x6afa  stloc.s  0xA
0x6afc  ldloc.s  0xA
0x6afe  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x6b03  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass40_0::present
0x6b08  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::.ctor()
0x6b0d  stloc.s  0xB
0x6b0f  ldloc.0
0x6b10  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>> <>c::<>9__40_0
0x6b15  dup
0x6b16  brtrue.s loc_6B2F
0x6b18  pop
0x6b19  ldsfld   class <>c <>c::<>9
0x6b1e  ldftn    instance class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object> <>c::<RetrieveAllActiveNotifications>b__40_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> collectionItem)
0x6b24  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>>::.ctor(object, native int)
0x6b29  dup
0x6b2a  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>> <>c::<>9__40_0
0x6b2f  call     T0x2B000016
0x6b34  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>, class <>f__AnonymousType1`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>, object>> <>c::<>9__40_1
0x6b39  dup
0x6b3a  brtrue.s loc_6B53
0x6b3c  pop
0x6b3d  ldsfld   class <>c <>c::<>9
0x6b42  ldftn    instance class <>f__AnonymousType1`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>, object> <>c::<RetrieveAllActiveNotifications>b__40_1(class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object> <>h__TransparentIdentifier0)
0x6b48  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>, class <>f__AnonymousType1`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>, object>>::.ctor(object, native int)
0x6b4d  dup
0x6b4e  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>, class <>f__AnonymousType1`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>, object>> <>c::<>9__40_1
0x6b53  call     T0x2B000017
0x6b58  ldloc.s  0xA
0x6b5a  ldfld    class [mscorlib]System.Func`2<class <>f__AnonymousType1`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>, object>, bool> <>c__DisplayClass40_0::<>9__2
0x6b5f  dup
0x6b60  brtrue.s loc_6B7C
0x6b62  pop
0x6b63  ldloc.s  0xA
0x6b65  ldloc.s  0xA
0x6b67  ldftn    instance bool <>c__DisplayClass40_0::<RetrieveAllActiveNotifications>b__2(class <>f__AnonymousType1`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>, object> <>h__TransparentIdentifier1)
0x6b6d  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType1`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>, object>, bool>::.ctor(object, native int)
0x6b72  dup
0x6b73  stloc.s  0xD
0x6b75  stfld    class [mscorlib]System.Func`2<class <>f__AnonymousType1`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>, object>, bool> <>c__DisplayClass40_0::<>9__2
0x6b7a  ldloc.s  0xD
0x6b7c  call     T0x2B000018
0x6b81  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType1`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>, object>, valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>> <>c::<>9__40_3
0x6b86  dup
0x6b87  brtrue.s loc_6BA0
0x6b89  pop
0x6b8a  ldsfld   class <>c <>c::<>9
0x6b8f  ldftn    instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> <>c::<RetrieveAllActiveNotifications>b__40_3(class <>f__AnonymousType1`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>, object> <>h__TransparentIdentifier1)
0x6b95  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType1`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>, object>, valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>>::.ctor(object, native int)
0x6b9a  dup
0x6b9b  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType1`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, object>, object>, valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>> <>c::<>9__40_3
0x6ba0  call     T0x2B000019
0x6ba5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>>::GetEnumerator()
0x6baa  stloc.s  0xC
0x6bac  br.s     loc_6BCC
0x6bae  ldloc.s  0xC
0x6bb0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>>::get_Current()
0x6bb5  stloc.s  0xE
0x6bb7  ldloc.s  0xB
0x6bb9  ldloca.s 0xE
0x6bbb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Key()
0x6bc0  ldloca.s 0xE
0x6bc2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x6bc7  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>, !!T0)
0x6bcc  ldloc.s  0xC
0x6bce  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6bd3  brtrue.s loc_6BAE
0x6bd5  leave.s  loc_6BE3
0x6bd7  ldloc.s  0xC
0x6bd9  brfalse.s loc_6BE2
0x6bdb  ldloc.s  0xC
0x6bdd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6be2  endfinally
0x6be3  ldloc.s  0xB
0x6be5  ret
0x6be6  ldnull
0x6be7  ret
```
