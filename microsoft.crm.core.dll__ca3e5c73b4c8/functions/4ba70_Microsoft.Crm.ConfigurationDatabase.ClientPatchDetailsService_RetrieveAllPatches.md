# Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::RetrieveAllPatches

- ea: `0x4ba70`
- end: `0x4bc9a`
- name: `Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::RetrieveAllPatches`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x4c060`

## callees

- `0x4640`
- `0x4c40`
- `0x444f0`
- `0x4b730`
- `0x4b860`
- `0x4b930`
- `0x4b940`
- `0x4b950`
- `0x4b960`
- `0x4ba70`

## string_xrefs

- `0x4ba84`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ClientPatchDetails.cs`
- `0x4baa3`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ClientPatchDetails.cs`
- `0x4bac2`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ClientPatchDetails.cs`

## pseudocode

```c

```

## disassembly

```asm
0x4ba70  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x4ba75  ldstr    aClientpatchdet// "ClientPatchDetails"
0x4ba7a  ldc.i4   0xFC
0x4ba7f  ldstr    aRetrieveallpat// "RetrieveAllPatches"
0x4ba84  ldstr    aDA1SSrcPlatfor_35// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4ba89  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.LocatorService::Retrieve(string tableName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4ba8e  stloc.0
0x4ba8f  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x4ba94  ldstr    aClientpatchreq// "ClientPatchRequiredInfo"
0x4ba99  ldc.i4   0xFD
0x4ba9e  ldstr    aRetrieveallpat// "RetrieveAllPatches"
0x4baa3  ldstr    aDA1SSrcPlatfor_35// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4baa8  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.LocatorService::Retrieve(string tableName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4baad  stloc.1
0x4baae  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x4bab3  ldstr    aClientpatchcon// "ClientPatchContainedInfo"
0x4bab8  ldc.i4   0xFE
0x4babd  ldstr    aRetrieveallpat// "RetrieveAllPatches"
0x4bac2  ldstr    aDA1SSrcPlatfor_35// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4bac7  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.LocatorService::Retrieve(string tableName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4bacc  stloc.2
0x4bacd  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.ConfigurationDatabase.ClientPatch>::.ctor()
0x4bad2  stloc.3
0x4bad3  ldloc.0
0x4bad4  brfalse  loc_4BC98
0x4bad9  ldloc.0
0x4bada  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x4badf  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x4bae4  stloc.s  4
0x4bae6  br.s     loc_4BB05
0x4bae8  ldloca.s 4
0x4baea  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x4baef  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ClientPatch::.ctor(class Microsoft.Crm.Data.PropertyBag propertyBag)
0x4baf4  stloc.s  5
0x4baf6  ldloc.3
0x4baf7  ldloc.s  5
0x4baf9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ConfigurationDatabase.ClientPatch::get_PatchId()
0x4bafe  ldloc.s  5
0x4bb00  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.ConfigurationDatabase.ClientPatch>::Add(var<u1>, !!T0)
0x4bb05  ldloca.s 4
0x4bb07  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x4bb0c  brtrue.s loc_4BAE8
0x4bb0e  leave.s  loc_4BB1E
0x4bb10  ldloca.s 4
0x4bb12  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x4bb18  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4bb1d  endfinally
0x4bb1e  ldloc.1
0x4bb1f  brfalse  loc_4BBDB
0x4bb24  ldloc.1
0x4bb25  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x4bb2a  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x4bb2f  stloc.s  4
0x4bb31  br       loc_4BBBF
0x4bb36  ldloca.s 4
0x4bb38  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x4bb3d  stloc.s  6
0x4bb3f  ldloc.3
0x4bb40  ldloc.s  6
0x4bb42  ldstr    aPatchid// "PatchId"
0x4bb47  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4bb4c  unbox.any [mscorlib]System.Guid
0x4bb51  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.ConfigurationDatabase.ClientPatch>::ContainsKey(var<u1>)
0x4bb56  brfalse.s loc_4BBBF
0x4bb58  ldloc.3
0x4bb59  ldloc.s  6
0x4bb5b  ldstr    aRequiredpatchi// "RequiredPatchId"
0x4bb60  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4bb65  unbox.any [mscorlib]System.Guid
0x4bb6a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.ConfigurationDatabase.ClientPatch>::ContainsKey(var<u1>)
0x4bb6f  brfalse.s loc_4BBBF
0x4bb71  ldloc.3
0x4bb72  ldloc.s  6
0x4bb74  ldstr    aPatchid// "PatchId"
0x4bb79  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4bb7e  unbox.any [mscorlib]System.Guid
0x4bb83  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.ConfigurationDatabase.ClientPatch>::get_Item(void)
0x4bb88  stloc.s  7
0x4bb8a  ldloc.3
0x4bb8b  ldloc.s  6
0x4bb8d  ldstr    aRequiredpatchi// "RequiredPatchId"
0x4bb92  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4bb97  unbox.any [mscorlib]System.Guid
0x4bb9c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.ConfigurationDatabase.ClientPatch>::get_Item(void)
0x4bba1  stloc.s  8
0x4bba3  ldloc.s  7
0x4bba5  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ConfigurationDatabase.ClientPatch> Microsoft.Crm.ConfigurationDatabase.ClientPatch::get_RequiresPatches()
0x4bbaa  ldloc.s  8
0x4bbac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ConfigurationDatabase.ClientPatch>::Add(var<u1>)
0x4bbb1  ldloc.s  8
0x4bbb3  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ConfigurationDatabase.ClientPatch> Microsoft.Crm.ConfigurationDatabase.ClientPatch::get_RequiredByPatches()
0x4bbb8  ldloc.s  7
0x4bbba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ConfigurationDatabase.ClientPatch>::Add(var<u1>)
0x4bbbf  ldloca.s 4
0x4bbc1  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x4bbc6  brtrue   loc_4BB36
0x4bbcb  leave.s  loc_4BBDB
0x4bbcd  ldloca.s 4
0x4bbcf  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x4bbd5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4bbda  endfinally
0x4bbdb  ldloc.2
0x4bbdc  brfalse  loc_4BC98
0x4bbe1  ldloc.2
0x4bbe2  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x4bbe7  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x4bbec  stloc.s  4
0x4bbee  br       loc_4BC7C
0x4bbf3  ldloca.s 4
0x4bbf5  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x4bbfa  stloc.s  9
0x4bbfc  ldloc.3
0x4bbfd  ldloc.s  9
0x4bbff  ldstr    aPatchid// "PatchId"
0x4bc04  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4bc09  unbox.any [mscorlib]System.Guid
0x4bc0e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.ConfigurationDatabase.ClientPatch>::ContainsKey(var<u1>)
0x4bc13  brfalse.s loc_4BC7C
0x4bc15  ldloc.3
0x4bc16  ldloc.s  9
0x4bc18  ldstr    aContainedpatch// "ContainedPatchId"
0x4bc1d  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4bc22  unbox.any [mscorlib]System.Guid
0x4bc27  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.ConfigurationDatabase.ClientPatch>::ContainsKey(var<u1>)
0x4bc2c  brfalse.s loc_4BC7C
0x4bc2e  ldloc.3
0x4bc2f  ldloc.s  9
0x4bc31  ldstr    aPatchid// "PatchId"
0x4bc36  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4bc3b  unbox.any [mscorlib]System.Guid
0x4bc40  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.ConfigurationDatabase.ClientPatch>::get_Item(void)
0x4bc45  stloc.s  0xA
0x4bc47  ldloc.3
0x4bc48  ldloc.s  9
0x4bc4a  ldstr    aContainedpatch// "ContainedPatchId"
0x4bc4f  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4bc54  unbox.any [mscorlib]System.Guid
0x4bc59  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.ConfigurationDatabase.ClientPatch>::get_Item(void)
0x4bc5e  stloc.s  0xB
0x4bc60  ldloc.s  0xA
0x4bc62  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ConfigurationDatabase.ClientPatch> Microsoft.Crm.ConfigurationDatabase.ClientPatch::get_ContainsPatches()
0x4bc67  ldloc.s  0xB
0x4bc69  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ConfigurationDatabase.ClientPatch>::Add(var<u1>)
0x4bc6e  ldloc.s  0xB
0x4bc70  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ConfigurationDatabase.ClientPatch> Microsoft.Crm.ConfigurationDatabase.ClientPatch::get_ContainedByPatches()
0x4bc75  ldloc.s  0xA
0x4bc77  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ConfigurationDatabase.ClientPatch>::Add(var<u1>)
0x4bc7c  ldloca.s 4
0x4bc7e  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x4bc83  brtrue   loc_4BBF3
0x4bc88  leave.s  loc_4BC98
0x4bc8a  ldloca.s 4
0x4bc8c  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x4bc92  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4bc97  endfinally
0x4bc98  ldloc.3
0x4bc99  ret
```
