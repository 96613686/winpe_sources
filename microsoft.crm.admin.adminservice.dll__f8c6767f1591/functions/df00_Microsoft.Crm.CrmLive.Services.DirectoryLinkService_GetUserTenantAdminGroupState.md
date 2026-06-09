# Microsoft.Crm.CrmLive.Services.DirectoryLinkService::GetUserTenantAdminGroupState

- ea: `0xdf00`
- end: `0xe151`
- name: `Microsoft.Crm.CrmLive.Services.DirectoryLinkService::GetUserTenantAdminGroupState`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xe160`

## callees

- `0xdd80`
- `0xdf00`
- `0xf1b0`
- `0xf7e0`
- `0xf950`

## string_xrefs

- `0xdf72`: `D:\a\1\s\src\CrmLive\Admin\MicrosoftOnline\DirectoryLinkService.cs`
- `0xe012`: `D:\a\1\s\src\CrmLive\Admin\MicrosoftOnline\DirectoryLinkService.cs`
- `0xe0ba`: `D:\a\1\s\src\CrmLive\Admin\MicrosoftOnline\DirectoryLinkService.cs`
- `0xdf54`: `DirectoryObjectState`
- `0xe0a8`: `DirectoryObjectState`
- `0xdfe2`: `DirectoryLink`
- `0xdf42`: `DeletedOn`
- `0xdff7`: `DeletedOn`
- `0xe0fb`: `CRMServiceAdmins`

## pseudocode

```c

```

## disassembly

```asm
0xdf00  ldarg.1
0xdf01  ldstr    aUserprincipaln// "userPrincipalName"
0xdf06  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xdf0b  ldarg.2
0xdf0c  ldstr    aContextid_0// "contextId"
0xdf11  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xdf16  ldc.i4.0
0xdf17  stloc.0
0xdf18  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xdf1d  stloc.1
0xdf1e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xdf23  stloc.2
0xdf24  ldloc.2
0xdf25  ldstr    aUserprincipaln_0// "UserPrincipalName"
0xdf2a  ldarg.1
0xdf2b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xdf30  ldloc.2
0xdf31  ldstr    aContextid// "ContextId"
0xdf36  ldarg.2
0xdf37  box      [mscorlib]System.Guid
0xdf3c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xdf41  ldloc.2
0xdf42  ldstr    aDeletedon// "DeletedOn"
0xdf47  ldc.i4.0
0xdf48  ldnull
0xdf49  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0xdf4e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xdf53  ldloc.1
0xdf54  ldstr    aDirectoryobjec// "DirectoryObjectState"
0xdf59  ldc.i4.1
0xdf5a  newarr   [mscorlib]System.String
0xdf5f  dup
0xdf60  ldc.i4.0
0xdf61  ldstr    aObjectid_0// "ObjectId"
0xdf66  stelem.ref
0xdf67  ldloc.2
0xdf68  ldc.i4   0x131
0xdf6d  ldstr    aGetusertenanta// "GetUserTenantAdminGroupState"
0xdf72  ldstr    aDA1SSrcCrmlive_18// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Micro"...
0xdf77  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xdf7c  stloc.3
0xdf7d  ldloc.3
0xdf7e  brtrue.s loc_DF88
0xdf80  ldloc.0
0xdf81  stloc.s  8
0xdf83  leave    loc_E14E
0xdf88  ldloc.3
0xdf89  ldstr    aObjectid_0// "ObjectId"
0xdf8e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xdf93  unbox.any [mscorlib]System.Guid
0xdf98  stloc.s  4
0xdf9a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xdf9f  stloc.s  5
0xdfa1  ldloc.s  5
0xdfa3  ldstr    aSourceclass// "SourceClass"
0xdfa8  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Group
0xdfad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xdfb2  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0xdfb7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xdfbc  ldloc.s  5
0xdfbe  ldstr    aTargetid_0// "TargetId"
0xdfc3  ldloc.s  4
0xdfc5  box      [mscorlib]System.Guid
0xdfca  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xdfcf  ldloc.s  5
0xdfd1  ldstr    aContextid// "ContextId"
0xdfd6  ldarg.2
0xdfd7  box      [mscorlib]System.Guid
0xdfdc  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xdfe1  ldloc.1
0xdfe2  ldstr    aDirectorylink// "DirectoryLink"
0xdfe7  ldc.i4.2
0xdfe8  newarr   [mscorlib]System.String
0xdfed  dup
0xdfee  ldc.i4.0
0xdfef  ldstr    aSourceid// "SourceId"
0xdff4  stelem.ref
0xdff5  dup
0xdff6  ldc.i4.1
0xdff7  ldstr    aDeletedon// "DeletedOn"
0xdffc  stelem.ref
0xdffd  ldc.i4.1
0xdffe  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xe003  dup
0xe004  ldc.i4.0
0xe005  ldloc.s  5
0xe007  stelem.ref
0xe008  ldc.i4   0x13E
0xe00d  ldstr    aGetusertenanta// "GetUserTenantAdminGroupState"
0xe012  ldstr    aDA1SSrcCrmlive_18// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Micro"...
0xe017  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0xe01c  stloc.s  6
0xe01e  ldloc.s  6
0xe020  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0xe025  brfalse.s loc_E02F
0xe027  ldloc.0
0xe028  stloc.s  8
0xe02a  leave    loc_E14E
0xe02f  ldloc.s  6
0xe031  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0xe036  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>> <>c::<>9__12_0
0xe03b  dup
0xe03c  brtrue.s loc_E055
0xe03e  pop
0xe03f  ldsfld   class <>c <>c::<>9
0xe044  ldftn    instance class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> <>c::<GetUserTenantAdminGroupState>b__12_0(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag groupBag)
0xe04a  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>>::.ctor(object, native int)
0xe04f  dup
0xe050  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>> <>c::<>9__12_0
0xe055  call     T0x2B00003F
0xe05a  newobj   instance void Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::.ctor()
0xe05f  stloc.s  7
0xe061  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>>::GetEnumerator()
0xe066  stloc.s  9
0xe068  br       loc_E125
0xe06d  ldloc.s  9
0xe06f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>>::get_Current()
0xe074  stloc.s  0xA
0xe076  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xe07b  stloc.s  0xB
0xe07d  ldloc.s  0xB
0xe07f  ldstr    aObjectid_0// "ObjectId"
0xe084  ldloc.s  0xA
0xe086  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::get_Item1()
0xe08b  box      [mscorlib]System.Guid
0xe090  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe095  ldloc.s  0xB
0xe097  ldstr    aContextid// "ContextId"
0xe09c  ldarg.2
0xe09d  box      [mscorlib]System.Guid
0xe0a2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe0a7  ldloc.1
0xe0a8  ldstr    aDirectoryobjec// "DirectoryObjectState"
0xe0ad  ldnull
0xe0ae  ldloc.s  0xB
0xe0b0  ldc.i4   0x14F
0xe0b5  ldstr    aGetusertenanta// "GetUserTenantAdminGroupState"
0xe0ba  ldstr    aDA1SSrcCrmlive_18// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Micro"...
0xe0bf  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xe0c4  stloc.s  0xC
0xe0c6  ldloc.s  0xC
0xe0c8  brfalse.s loc_E125
0xe0ca  ldloc.s  7
0xe0cc  ldloc.s  0xC
0xe0ce  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::ConvertToDirectoryObject(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0xe0d3  castclass [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Group
0xe0d8  stloc.s  0xD
0xe0da  ldloc.s  7
0xe0dc  ldloc.s  0xD
0xe0de  ldstr    aWellknownobjec// "WellKnownObject"
0xe0e3  callvirt instance string Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::RetrieveStringPropertyValue(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject directoryObject, string propertyName)
0xe0e8  stloc.s  0xE
0xe0ea  ldloc.s  0xE
0xe0ec  ldstr    aTenantadmins// "TenantAdmins"
0xe0f1  ldc.i4.5
0xe0f2  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xe0f7  brtrue.s loc_E108
0xe0f9  ldloc.s  0xE
0xe0fb  ldstr    aCrmserviceadmi// "CRMServiceAdmins"
0xe100  ldc.i4.5
0xe101  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xe106  brfalse.s loc_E125
0xe108  ldloc.0
0xe109  ldloc.s  0xA
0xe10b  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::get_Item2()
0xe110  stloc.s  0xF
0xe112  ldloca.s 0xF
0xe114  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0xe119  brfalse.s loc_E11E
0xe11b  ldc.i4.2
0xe11c  br.s     loc_E11F
0xe11e  ldc.i4.1
0xe11f  call     valuetype Microsoft.Crm.CrmLive.Services.AdminGroupState Microsoft.Crm.CrmLive.Services.DirectoryLinkService::BestOfStates(valuetype Microsoft.Crm.CrmLive.Services.AdminGroupState state1, valuetype Microsoft.Crm.CrmLive.Services.AdminGroupState state2)
0xe124  stloc.0
0xe125  ldloc.s  9
0xe127  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe12c  brtrue   loc_E06D
0xe131  leave.s  loc_E13F
0xe133  ldloc.s  9
0xe135  brfalse.s loc_E13E
0xe137  ldloc.s  9
0xe139  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe13e  endfinally
0xe13f  ldloc.0
0xe140  stloc.s  8
0xe142  leave.s  loc_E14E
0xe144  ldloc.1
0xe145  brfalse.s loc_E14D
0xe147  ldloc.1
0xe148  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe14d  endfinally
0xe14e  ldloc.s  8
0xe150  ret
```
