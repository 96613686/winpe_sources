# Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::ThrowIfContainmentLoopExists

- ea: `0x4c380`
- end: `0x4c5ca`
- name: `Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::ThrowIfContainmentLoopExists`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x4be10`

## callees

- `0x1b340`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x4c140`
- `0x4c380`
- `0x4c5d0`
- `0x61520`

## string_xrefs

- `0x4c3f7`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ClientPatchDetails.cs`
- `0x4c4a0`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ClientPatchDetails.cs`
- `0x4c555`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ClientPatchDetails.cs`
- `0x4c3a4`: `Cannot create a containment relationship that leads to a cycle`

## pseudocode

```c

```

## disassembly

```asm
0x4c380  newobj   instance void class [System]System.Collections.Generic.Queue`1<valuetype [mscorlib]System.Guid>::.ctor()
0x4c385  stloc.0
0x4c386  ldloc.0
0x4c387  ldarg.1
0x4c388  callvirt instance void class [System]System.Collections.Generic.Queue`1<valuetype [mscorlib]System.Guid>::Enqueue(var<u1>)
0x4c38d  br       loc_4C450
0x4c392  ldloc.0
0x4c393  callvirt instance var<u1> class [System]System.Collections.Generic.Queue`1<valuetype [mscorlib]System.Guid>::Dequeue()
0x4c398  stloc.s  5
0x4c39a  ldloc.s  5
0x4c39c  ldarg.2
0x4c39d  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4c3a2  brfalse.s loc_4C3AF
0x4c3a4  ldstr    aCannotCreateAC// "Cannot create a containment relationshi"...
0x4c3a9  newobj   instance void Microsoft.Crm.CrmArgumentException::.ctor(string message)
0x4c3ae  throw
0x4c3af  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4c3b4  stloc.s  6
0x4c3b6  ldloc.s  6
0x4c3b8  ldstr    aPatchid// "PatchId"
0x4c3bd  ldloc.s  5
0x4c3bf  box      [mscorlib]System.Guid
0x4c3c4  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4c3c9  ldarg.0
0x4c3ca  ldfld    class Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::_configService
0x4c3cf  ldstr    aClientpatchcon// "ClientPatchContainedInfo"
0x4c3d4  ldc.i4.1
0x4c3d5  newarr   [mscorlib]System.String
0x4c3da  dup
0x4c3db  ldc.i4.0
0x4c3dc  ldstr    aContainedpatch// "ContainedPatchId"
0x4c3e1  stelem.ref
0x4c3e2  ldc.i4.1
0x4c3e3  newarr   Microsoft.Crm.Data.PropertyBag
0x4c3e8  dup
0x4c3e9  ldc.i4.0
0x4c3ea  ldloc.s  6
0x4c3ec  stelem.ref
0x4c3ed  ldc.i4   0x254
0x4c3f2  ldstr    aThrowifcontain// "ThrowIfContainmentLoopExists"
0x4c3f7  ldstr    aDA1SSrcPlatfor_35// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4c3fc  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4c401  stloc.s  7
0x4c403  ldloc.s  7
0x4c405  brfalse.s loc_4C450
0x4c407  ldloc.s  7
0x4c409  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x4c40e  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x4c413  stloc.s  8
0x4c415  br.s     loc_4C437
0x4c417  ldloca.s 8
0x4c419  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x4c41e  stloc.s  9
0x4c420  ldloc.0
0x4c421  ldloc.s  9
0x4c423  ldstr    aContainedpatch// "ContainedPatchId"
0x4c428  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4c42d  unbox.any [mscorlib]System.Guid
0x4c432  callvirt instance void class [System]System.Collections.Generic.Queue`1<valuetype [mscorlib]System.Guid>::Enqueue(var<u1>)
0x4c437  ldloca.s 8
0x4c439  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x4c43e  brtrue.s loc_4C417
0x4c440  leave.s  loc_4C450
0x4c442  ldloca.s 8
0x4c444  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x4c44a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c44f  endfinally
0x4c450  ldc.i4.0
0x4c451  ldloc.0
0x4c452  callvirt instance int32 class [System]System.Collections.Generic.Queue`1<valuetype [mscorlib]System.Guid>::get_Count()
0x4c457  blt      loc_4C392
0x4c45c  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4c461  stloc.1
0x4c462  ldloc.1
0x4c463  ldstr    aPatchid// "PatchId"
0x4c468  ldarg.1
0x4c469  box      [mscorlib]System.Guid
0x4c46e  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4c473  ldarg.0
0x4c474  ldfld    class Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::_configService
0x4c479  ldstr    aClientpatchreq// "ClientPatchRequiredInfo"
0x4c47e  ldc.i4.1
0x4c47f  newarr   [mscorlib]System.String
0x4c484  dup
0x4c485  ldc.i4.0
0x4c486  ldstr    aRequiredpatchi// "RequiredPatchId"
0x4c48b  stelem.ref
0x4c48c  ldc.i4.1
0x4c48d  newarr   Microsoft.Crm.Data.PropertyBag
0x4c492  dup
0x4c493  ldc.i4.0
0x4c494  ldloc.1
0x4c495  stelem.ref
0x4c496  ldc.i4   0x261
0x4c49b  ldstr    aThrowifcontain// "ThrowIfContainmentLoopExists"
0x4c4a0  ldstr    aDA1SSrcPlatfor_35// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4c4a5  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4c4aa  stloc.2
0x4c4ab  ldloc.2
0x4c4ac  brfalse.s loc_4C511
0x4c4ae  ldloc.2
0x4c4af  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x4c4b4  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x4c4b9  stloc.s  8
0x4c4bb  br.s     loc_4C4F8
0x4c4bd  ldloca.s 8
0x4c4bf  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x4c4c4  stloc.s  0xA
0x4c4c6  ldarg.0
0x4c4c7  ldloc.s  0xA
0x4c4c9  ldstr    aRequiredpatchi// "RequiredPatchId"
0x4c4ce  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4c4d3  unbox.any [mscorlib]System.Guid
0x4c4d8  ldarg.2
0x4c4d9  call     instance bool Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::Contains(valuetype [mscorlib]System.Guid sourcePatchId, valuetype [mscorlib]System.Guid destinationPatchId)
0x4c4de  brtrue.s loc_4C4F8
0x4c4e0  ldarg.0
0x4c4e1  ldloc.s  0xA
0x4c4e3  ldstr    aRequiredpatchi// "RequiredPatchId"
0x4c4e8  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4c4ed  unbox.any [mscorlib]System.Guid
0x4c4f2  ldarg.2
0x4c4f3  call     instance void Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::ThrowIfRequirementLoopExists(valuetype [mscorlib]System.Guid sourcePatchId, valuetype [mscorlib]System.Guid destinationPatchId)
0x4c4f8  ldloca.s 8
0x4c4fa  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x4c4ff  brtrue.s loc_4C4BD
0x4c501  leave.s  loc_4C511
0x4c503  ldloca.s 8
0x4c505  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x4c50b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c510  endfinally
0x4c511  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4c516  stloc.3
0x4c517  ldloc.3
0x4c518  ldstr    aRequiredpatchi// "RequiredPatchId"
0x4c51d  ldarg.1
0x4c51e  box      [mscorlib]System.Guid
0x4c523  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4c528  ldarg.0
0x4c529  ldfld    class Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::_configService
0x4c52e  ldstr    aClientpatchreq// "ClientPatchRequiredInfo"
0x4c533  ldc.i4.1
0x4c534  newarr   [mscorlib]System.String
0x4c539  dup
0x4c53a  ldc.i4.0
0x4c53b  ldstr    aPatchid// "PatchId"
0x4c540  stelem.ref
0x4c541  ldc.i4.1
0x4c542  newarr   Microsoft.Crm.Data.PropertyBag
0x4c547  dup
0x4c548  ldc.i4.0
0x4c549  ldloc.3
0x4c54a  stelem.ref
0x4c54b  ldc.i4   0x271
0x4c550  ldstr    aThrowifcontain// "ThrowIfContainmentLoopExists"
0x4c555  ldstr    aDA1SSrcPlatfor_35// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4c55a  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4c55f  stloc.s  4
0x4c561  ldloc.s  4
0x4c563  brfalse.s loc_4C5C9
0x4c565  ldloc.s  4
0x4c567  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x4c56c  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x4c571  stloc.s  8
0x4c573  br.s     loc_4C5B0
0x4c575  ldloca.s 8
0x4c577  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x4c57c  stloc.s  0xB
0x4c57e  ldarg.0
0x4c57f  ldarg.2
0x4c580  ldloc.s  0xB
0x4c582  ldstr    aPatchid// "PatchId"
0x4c587  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4c58c  unbox.any [mscorlib]System.Guid
0x4c591  call     instance bool Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::Contains(valuetype [mscorlib]System.Guid sourcePatchId, valuetype [mscorlib]System.Guid destinationPatchId)
0x4c596  brtrue.s loc_4C5B0
0x4c598  ldarg.0
0x4c599  ldarg.2
0x4c59a  ldloc.s  0xB
0x4c59c  ldstr    aPatchid// "PatchId"
0x4c5a1  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4c5a6  unbox.any [mscorlib]System.Guid
0x4c5ab  call     instance void Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::ThrowIfRequirementLoopExists(valuetype [mscorlib]System.Guid sourcePatchId, valuetype [mscorlib]System.Guid destinationPatchId)
0x4c5b0  ldloca.s 8
0x4c5b2  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x4c5b7  brtrue.s loc_4C575
0x4c5b9  leave.s  loc_4C5C9
0x4c5bb  ldloca.s 8
0x4c5bd  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x4c5c3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c5c8  endfinally
0x4c5c9  ret
```
