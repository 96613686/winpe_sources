# Microsoft.Crm.CrmLive.Services.DirectoryLinkService::RetrieveNewObjectsForOrganization

- ea: `0xe3b0`
- end: `0xe668`
- name: `Microsoft.Crm.CrmLive.Services.DirectoryLinkService::RetrieveNewObjectsForOrganization`
- size: `696`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xe3b0`
- `0xe7c0`

## string_xrefs

- `0xe412`: `D:\a\1\s\src\CrmLive\Admin\MicrosoftOnline\DirectoryLinkService.cs`
- `0xe538`: `D:\a\1\s\src\CrmLive\Admin\MicrosoftOnline\DirectoryLinkService.cs`
- `0xe466`: `DirectoryLink`
- `0xe3f9`: `DirectoryLinkRevision`
- `0xe42b`: `DirectoryLinkRevision`
- `0xe439`: `DirectoryLinkRevision`
- `0xe447`: `DirectoryLinkRevision`

## pseudocode

```c

```

## disassembly

```asm
0xe3b0  ldarg.1
0xe3b1  ldstr    aOrganizationid// "organizationId"
0xe3b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xe3bb  ldarg.2
0xe3bc  ldstr    aBatchSizeMustB// "Batch size must be positive"
0xe3c1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNotPositive(int32, string)
0xe3c6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::.ctor()
0xe3cb  stloc.0
0xe3cc  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xe3d1  stloc.1
0xe3d2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xe3d7  stloc.2
0xe3d8  ldloc.2
0xe3d9  ldstr    aCrmorganizatio// "CrmOrganizationId"
0xe3de  ldarg.1
0xe3df  box      [mscorlib]System.Guid
0xe3e4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe3e9  ldc.i4.2
0xe3ea  newarr   [mscorlib]System.String
0xe3ef  dup
0xe3f0  ldc.i4.0
0xe3f1  ldstr    aContextid// "ContextId"
0xe3f6  stelem.ref
0xe3f7  dup
0xe3f8  ldc.i4.1
0xe3f9  ldstr    aDirectorylinkr// "DirectoryLinkRevision"
0xe3fe  stelem.ref
0xe3ff  stloc.3
0xe400  ldloc.1
0xe401  ldstr    aOrganizationli// "OrganizationLifecycle"
0xe406  ldloc.3
0xe407  ldloc.2
0xe408  ldc.i4   0x1D4
0xe40d  ldstr    aRetrievenewobj// "RetrieveNewObjectsForOrganization"
0xe412  ldstr    aDA1SSrcCrmlive_18// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Micro"...
0xe417  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xe41c  stloc.s  4
0xe41e  ldloc.s  4
0xe420  brfalse  loc_E632
0xe425  ldc.i4.0
0xe426  conv.i8
0xe427  stloc.s  5
0xe429  ldloc.s  4
0xe42b  ldstr    aDirectorylinkr// "DirectoryLinkRevision"
0xe430  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0xe435  brfalse.s loc_E458
0xe437  ldloc.s  4
0xe439  ldstr    aDirectorylinkr// "DirectoryLinkRevision"
0xe43e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xe443  brfalse.s loc_E458
0xe445  ldloc.s  4
0xe447  ldstr    aDirectorylinkr// "DirectoryLinkRevision"
0xe44c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xe451  unbox.any [mscorlib]System.Int64
0xe456  stloc.s  5
0xe458  ldloc.s  4
0xe45a  ldstr    aContextid// "ContextId"
0xe45f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xe464  stloc.s  6
0xe466  ldstr    aDirectorylink// "DirectoryLink"
0xe46b  ldc.i4.2
0xe46c  newarr   [mscorlib]System.String
0xe471  dup
0xe472  ldc.i4.0
0xe473  ldstr    aTargetid_0// "TargetId"
0xe478  stelem.ref
0xe479  dup
0xe47a  ldc.i4.1
0xe47b  ldstr    aRevision// "Revision"
0xe480  stelem.ref
0xe481  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::.ctor(string, string[])
0xe486  stloc.s  7
0xe488  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xe48d  stloc.s  8
0xe48f  ldloc.s  8
0xe491  ldstr    aContextid// "ContextId"
0xe496  ldloc.s  6
0xe498  unbox.any [mscorlib]System.Guid
0xe49d  box      [mscorlib]System.Guid
0xe4a2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe4a7  ldloc.s  8
0xe4a9  ldstr    aModifiedon// "ModifiedOn"
0xe4ae  ldc.i4.5
0xe4af  ldnull
0xe4b0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0xe4b5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe4ba  ldloc.s  8
0xe4bc  ldstr    aRevision// "Revision"
0xe4c1  ldc.i4.1
0xe4c2  ldloc.s  5
0xe4c4  box      [mscorlib]System.UInt64
0xe4c9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0xe4ce  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe4d3  ldloc.s  8
0xe4d5  ldstr    aSourceclass// "SourceClass"
0xe4da  ldstr    aGroup// "Group"
0xe4df  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe4e4  ldloc.s  8
0xe4e6  ldstr    aTargetclass// "TargetClass"
0xe4eb  ldstr    aUser// "User"
0xe4f0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe4f5  ldloc.s  7
0xe4f7  ldc.i4.1
0xe4f8  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xe4fd  dup
0xe4fe  ldc.i4.0
0xe4ff  ldloc.s  8
0xe501  stelem.ref
0xe502  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::SetConditions(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[])
0xe507  ldloc.s  7
0xe509  ldarg.2
0xe50a  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xe50f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::set_Top(valuetype [mscorlib]System.Nullable`1<int32>)
0xe514  ldloc.s  7
0xe516  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering> [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery::get_OrderBy()
0xe51b  ldstr    aRevision// "Revision"
0xe520  ldc.i4.0
0xe521  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering::.ctor(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QuerySortOrder)
0xe526  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.QueryOrdering>::Add(var<u1>)
0xe52b  ldloc.1
0xe52c  ldloc.s  7
0xe52e  ldc.i4   0x1EC
0xe533  ldstr    aRetrievenewobj// "RetrieveNewObjectsForOrganization"
0xe538  ldstr    aDA1SSrcCrmlive_18// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Micro"...
0xe53d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.OrderedPropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.StructuredQuery, int32, string, string)
0xe542  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>>::.ctor()
0xe547  stloc.s  9
0xe549  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> [Microsoft.Crm.Core]Microsoft.Crm.Data.OrderedPropertyBagCollection::RetrievePropertyBags()
0xe54e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0xe553  stloc.s  0xA
0xe555  br.s     loc_E592
0xe557  ldloc.s  0xA
0xe559  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0xe55e  stloc.s  0xB
0xe560  ldloc.s  0xB
0xe562  ldstr    aTargetid_0// "TargetId"
0xe567  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xe56c  unbox.any [mscorlib]System.Guid
0xe571  stloc.s  0xC
0xe573  ldloc.s  9
0xe575  ldloc.s  0xC
0xe577  ldloc.s  0xB
0xe579  ldstr    aRevision// "Revision"
0xe57e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xe583  unbox.any [mscorlib]System.UInt64
0xe588  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>::.ctor(var<u1>, !!T0)
0xe58d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>>::Add(var<u1>)
0xe592  ldloc.s  0xA
0xe594  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe599  brtrue.s loc_E557
0xe59b  leave.s  loc_E5A9
0xe59d  ldloc.s  0xA
0xe59f  brfalse.s loc_E5A8
0xe5a1  ldloc.s  0xA
0xe5a3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe5a8  endfinally
0xe5a9  ldloc.s  9
0xe5ab  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>, valuetype [mscorlib]System.Guid> <>c::<>9__17_1
0xe5b0  dup
0xe5b1  brtrue.s loc_E5CA
0xe5b3  pop
0xe5b4  ldsfld   class <>c <>c::<>9
0xe5b9  ldftn    instance valuetype [mscorlib]System.Guid <>c::<RetrieveNewObjectsForOrganization>b__17_1(class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64> x)
0xe5bf  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0xe5c4  dup
0xe5c5  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>, valuetype [mscorlib]System.Guid> <>c::<>9__17_1
0xe5ca  call     T0x2B000042
0xe5cf  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Core]System.Linq.IGrouping`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>>>::GetEnumerator()
0xe5d4  stloc.s  0xD
0xe5d6  br.s     loc_E61B
0xe5d8  ldloc.s  0xD
0xe5da  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Core]System.Linq.IGrouping`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>>>::get_Current()
0xe5df  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>, int64> <>c::<>9__17_2
0xe5e4  dup
0xe5e5  brtrue.s loc_E5FE
0xe5e7  pop
0xe5e8  ldsfld   class <>c <>c::<>9
0xe5ed  ldftn    instance int64 <>c::<RetrieveNewObjectsForOrganization>b__17_2(class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64> item)
0xe5f3  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>, int64>::.ctor(object, native int)
0xe5f8  dup
0xe5f9  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>, int64> <>c::<>9__17_2
0xe5fe  call     T0x2B000043
0xe603  stloc.s  0xE
0xe605  ldloc.1
0xe606  ldloc.s  0xE
0xe608  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.CrmLive.Services.DirectoryLinkService::MergeObjects(class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService service, class [System.Core]System.Linq.IOrderedEnumerable`1<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int64>> sortedObjectsAndRevisions)
0xe60d  stloc.s  0xF
0xe60f  ldloc.s  0xF
0xe611  brfalse.s loc_E61B
0xe613  ldloc.0
0xe614  ldloc.s  0xF
0xe616  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>)
0xe61b  ldloc.s  0xD
0xe61d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe622  brtrue.s loc_E5D8
0xe624  leave.s  loc_E632
0xe626  ldloc.s  0xD
0xe628  brfalse.s loc_E631
0xe62a  ldloc.s  0xD
0xe62c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe631  endfinally
0xe632  ldloc.0
0xe633  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, object> <>c::<>9__17_0
0xe638  dup
0xe639  brtrue.s loc_E652
0xe63b  pop
0xe63c  ldsfld   class <>c <>c::<>9
0xe641  ldftn    instance object <>c::<RetrieveNewObjectsForOrganization>b__17_0(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag record)
0xe647  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, object>::.ctor(object, native int)
0xe64c  dup
0xe64d  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, object> <>c::<>9__17_0
0xe652  call     T0x2B000044
0xe657  stloc.s  0x10
0xe659  leave.s  loc_E665
0xe65b  ldloc.1
0xe65c  brfalse.s loc_E664
0xe65e  ldloc.1
0xe65f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe664  endfinally
0xe665  ldloc.s  0x10
0xe667  ret
```
