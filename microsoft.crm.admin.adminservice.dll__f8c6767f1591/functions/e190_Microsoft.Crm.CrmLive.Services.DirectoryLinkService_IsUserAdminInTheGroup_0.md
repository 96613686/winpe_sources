# Microsoft.Crm.CrmLive.Services.DirectoryLinkService::IsUserAdminInTheGroup_0

- ea: `0xe190`
- end: `0xe380`
- name: `Microsoft.Crm.CrmLive.Services.DirectoryLinkService::IsUserAdminInTheGroup_0`
- size: `496`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xe170`
- `0x3d4c0`

## callees

- `0xe190`
- `0xe380`
- `0xf1b0`
- `0xf7e0`
- `0xf950`

## string_xrefs

- `0xe238`: `D:\a\1\s\src\CrmLive\Admin\MicrosoftOnline\DirectoryLinkService.cs`
- `0xe2fb`: `D:\a\1\s\src\CrmLive\Admin\MicrosoftOnline\DirectoryLinkService.cs`
- `0xe2e9`: `DirectoryObjectState`
- `0xe211`: `DirectoryLink`
- `0xe205`: `DeletedOn`

## pseudocode

```c

```

## disassembly

```asm
0xe190  ldarg.1
0xe191  ldstr    aContextid_0// "contextId"
0xe196  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xe19b  ldarg.2
0xe19c  ldstr    aUserobjectid// "userObjectId"
0xe1a1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xe1a6  ldarg.3
0xe1a7  ldstr    aAdmingroups// "adminGroups"
0xe1ac  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xe1b1  ldarg.0
0xe1b2  ldarg.2
0xe1b3  call     instance bool Microsoft.Crm.CrmLive.Services.DirectoryLinkService::IsUserAccountEnabled(valuetype [mscorlib]System.Guid objectId)
0xe1b8  brtrue.s loc_E1BC
0xe1ba  ldc.i4.0
0xe1bb  ret
0xe1bc  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xe1c1  stloc.0
0xe1c2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xe1c7  stloc.1
0xe1c8  ldloc.1
0xe1c9  ldstr    aSourceclass// "SourceClass"
0xe1ce  ldtoken  [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Group
0xe1d3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xe1d8  call     string [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObjectSerializer::GetStringFromType(class [mscorlib]System.Type)
0xe1dd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe1e2  ldloc.1
0xe1e3  ldstr    aTargetid_0// "TargetId"
0xe1e8  ldarg.2
0xe1e9  box      [mscorlib]System.Guid
0xe1ee  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe1f3  ldloc.1
0xe1f4  ldstr    aContextid// "ContextId"
0xe1f9  ldarg.1
0xe1fa  box      [mscorlib]System.Guid
0xe1ff  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe204  ldloc.1
0xe205  ldstr    aDeletedon// "DeletedOn"
0xe20a  ldnull
0xe20b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe210  ldloc.0
0xe211  ldstr    aDirectorylink// "DirectoryLink"
0xe216  ldc.i4.1
0xe217  newarr   [mscorlib]System.String
0xe21c  dup
0xe21d  ldc.i4.0
0xe21e  ldstr    aSourceid// "SourceId"
0xe223  stelem.ref
0xe224  ldc.i4.1
0xe225  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xe22a  dup
0xe22b  ldc.i4.0
0xe22c  ldloc.1
0xe22d  stelem.ref
0xe22e  ldc.i4   0x18A
0xe233  ldstr    aIsuseradminint// "IsUserAdminInTheGroup"
0xe238  ldstr    aDA1SSrcCrmlive_18// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Micro"...
0xe23d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0xe242  stloc.2
0xe243  ldloc.2
0xe244  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0xe249  brfalse.s loc_E253
0xe24b  ldc.i4.0
0xe24c  stloc.s  4
0xe24e  leave    loc_E37D
0xe253  ldloc.2
0xe254  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0xe259  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, bool> <>c::<>9__15_0
0xe25e  dup
0xe25f  brtrue.s loc_E278
0xe261  pop
0xe262  ldsfld   class <>c <>c::<>9
0xe267  ldftn    instance bool <>c::<IsUserAdminInTheGroup>b__15_0(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag groupBag)
0xe26d  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, bool>::.ctor(object, native int)
0xe272  dup
0xe273  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, bool> <>c::<>9__15_0
0xe278  call     T0x2B000040
0xe27d  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid> <>c::<>9__15_1
0xe282  dup
0xe283  brtrue.s loc_E29C
0xe285  pop
0xe286  ldsfld   class <>c <>c::<>9
0xe28b  ldftn    instance valuetype [mscorlib]System.Guid <>c::<IsUserAdminInTheGroup>b__15_1(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag groupBag)
0xe291  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0xe296  dup
0xe297  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid> <>c::<>9__15_1
0xe29c  call     T0x2B000041
0xe2a1  newobj   instance void Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::.ctor()
0xe2a6  stloc.3
0xe2a7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0xe2ac  stloc.s  5
0xe2ae  br       loc_E357
0xe2b3  ldloc.s  5
0xe2b5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0xe2ba  stloc.s  6
0xe2bc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xe2c1  stloc.s  7
0xe2c3  ldloc.s  7
0xe2c5  ldstr    aObjectid_0// "ObjectId"
0xe2ca  ldloc.s  6
0xe2cc  box      [mscorlib]System.Guid
0xe2d1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe2d6  ldloc.s  7
0xe2d8  ldstr    aContextid// "ContextId"
0xe2dd  ldarg.1
0xe2de  box      [mscorlib]System.Guid
0xe2e3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe2e8  ldloc.0
0xe2e9  ldstr    aDirectoryobjec// "DirectoryObjectState"
0xe2ee  ldnull
0xe2ef  ldloc.s  7
0xe2f1  ldc.i4   0x19E
0xe2f6  ldstr    aIsuseradminint// "IsUserAdminInTheGroup"
0xe2fb  ldstr    aDA1SSrcCrmlive_18// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Micro"...
0xe300  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xe305  stloc.s  8
0xe307  ldloc.s  8
0xe309  brfalse.s loc_E357
0xe30b  ldloc.3
0xe30c  ldloc.s  8
0xe30e  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::ConvertToDirectoryObject(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0xe313  castclass [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.Group
0xe318  stloc.s  9
0xe31a  ldloc.3
0xe31b  ldloc.s  9
0xe31d  ldstr    aWellknownobjec// "WellKnownObject"
0xe322  callvirt instance string Microsoft.Crm.CrmLive.Services.DirectoryObjectStateService::RetrieveStringPropertyValue(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject directoryObject, string propertyName)
0xe327  stloc.s  0xA
0xe329  ldarg.3
0xe32a  stloc.s  0xB
0xe32c  ldc.i4.0
0xe32d  stloc.s  0xC
0xe32f  br.s     loc_E34F
0xe331  ldloc.s  0xB
0xe333  ldloc.s  0xC
0xe335  ldelem.ref
0xe336  stloc.s  0xD
0xe338  ldloc.s  0xA
0xe33a  ldloc.s  0xD
0xe33c  ldc.i4.5
0xe33d  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xe342  brfalse.s loc_E349
0xe344  ldc.i4.1
0xe345  stloc.s  4
0xe347  leave.s  loc_E37D
0xe349  ldloc.s  0xC
0xe34b  ldc.i4.1
0xe34c  add
0xe34d  stloc.s  0xC
0xe34f  ldloc.s  0xC
0xe351  ldloc.s  0xB
0xe353  ldlen
0xe354  conv.i4
0xe355  blt.s    loc_E331
0xe357  ldloc.s  5
0xe359  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe35e  brtrue   loc_E2B3
0xe363  leave.s  loc_E37B
0xe365  ldloc.s  5
0xe367  brfalse.s loc_E370
0xe369  ldloc.s  5
0xe36b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe370  endfinally
0xe371  ldloc.0
0xe372  brfalse.s loc_E37A
0xe374  ldloc.0
0xe375  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe37a  endfinally
0xe37b  ldc.i4.0
0xe37c  ret
0xe37d  ldloc.s  4
0xe37f  ret
```
