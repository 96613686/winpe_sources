# Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::ThrowIfRequirementLoopExists

- ea: `0x4c140`
- end: `0x4c371`
- name: `Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::ThrowIfRequirementLoopExists`
- size: `561`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x4bd10`
- `0x4c380`

## callees

- `0x1b340`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x4c140`
- `0x61520`

## string_xrefs

- `0x4c1cb`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ClientPatchDetails.cs`
- `0x4c26b`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ClientPatchDetails.cs`
- `0x4c30b`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ClientPatchDetails.cs`
- `0x4c168`: `Cannot create a requirement between two patches that leads to a cycle`

## pseudocode

```c

```

## disassembly

```asm
0x4c140  newobj   instance void class [System]System.Collections.Generic.Queue`1<valuetype [mscorlib]System.Guid>::.ctor()
0x4c145  stloc.0
0x4c146  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::.ctor()
0x4c14b  stloc.1
0x4c14c  ldloc.0
0x4c14d  ldarg.1
0x4c14e  callvirt instance void class [System]System.Collections.Generic.Queue`1<valuetype [mscorlib]System.Guid>::Enqueue(var<u1>)
0x4c153  br       loc_4C364
0x4c158  ldloc.0
0x4c159  callvirt instance var<u1> class [System]System.Collections.Generic.Queue`1<valuetype [mscorlib]System.Guid>::Dequeue()
0x4c15e  stloc.2
0x4c15f  ldarg.2
0x4c160  ldloc.2
0x4c161  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4c166  brfalse.s loc_4C173
0x4c168  ldstr    aCannotCreateAR// "Cannot create a requirement between two"...
0x4c16d  newobj   instance void Microsoft.Crm.CrmArgumentException::.ctor(string message)
0x4c172  throw
0x4c173  ldloc.1
0x4c174  ldloc.2
0x4c175  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::ContainsKey(var<u1>)
0x4c17a  brtrue   loc_4C364
0x4c17f  ldloc.1
0x4c180  ldloc.2
0x4c181  ldloc.2
0x4c182  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x4c187  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4c18c  stloc.3
0x4c18d  ldloc.3
0x4c18e  ldstr    aPatchid// "PatchId"
0x4c193  ldloc.2
0x4c194  box      [mscorlib]System.Guid
0x4c199  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4c19e  ldarg.0
0x4c19f  ldfld    class Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::_configService
0x4c1a4  ldstr    aClientpatchreq// "ClientPatchRequiredInfo"
0x4c1a9  ldc.i4.1
0x4c1aa  newarr   [mscorlib]System.String
0x4c1af  dup
0x4c1b0  ldc.i4.0
0x4c1b1  ldstr    aRequiredpatchi// "RequiredPatchId"
0x4c1b6  stelem.ref
0x4c1b7  ldc.i4.1
0x4c1b8  newarr   Microsoft.Crm.Data.PropertyBag
0x4c1bd  dup
0x4c1be  ldc.i4.0
0x4c1bf  ldloc.3
0x4c1c0  stelem.ref
0x4c1c1  ldc.i4   0x219
0x4c1c6  ldstr    aThrowifrequire// "ThrowIfRequirementLoopExists"
0x4c1cb  ldstr    aDA1SSrcPlatfor_35// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4c1d0  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4c1d5  stloc.s  4
0x4c1d7  ldloc.s  4
0x4c1d9  brfalse.s loc_4C224
0x4c1db  ldloc.s  4
0x4c1dd  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x4c1e2  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x4c1e7  stloc.s  9
0x4c1e9  br.s     loc_4C20B
0x4c1eb  ldloca.s 9
0x4c1ed  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x4c1f2  stloc.s  0xA
0x4c1f4  ldloc.0
0x4c1f5  ldloc.s  0xA
0x4c1f7  ldstr    aRequiredpatchi// "RequiredPatchId"
0x4c1fc  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4c201  unbox.any [mscorlib]System.Guid
0x4c206  callvirt instance void class [System]System.Collections.Generic.Queue`1<valuetype [mscorlib]System.Guid>::Enqueue(var<u1>)
0x4c20b  ldloca.s 9
0x4c20d  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x4c212  brtrue.s loc_4C1EB
0x4c214  leave.s  loc_4C224
0x4c216  ldloca.s 9
0x4c218  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x4c21e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c223  endfinally
0x4c224  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4c229  stloc.s  5
0x4c22b  ldloc.s  5
0x4c22d  ldstr    aContainedpatch// "ContainedPatchId"
0x4c232  ldloc.2
0x4c233  box      [mscorlib]System.Guid
0x4c238  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4c23d  ldarg.0
0x4c23e  ldfld    class Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::_configService
0x4c243  ldstr    aClientpatchcon// "ClientPatchContainedInfo"
0x4c248  ldc.i4.1
0x4c249  newarr   [mscorlib]System.String
0x4c24e  dup
0x4c24f  ldc.i4.0
0x4c250  ldstr    aPatchid// "PatchId"
0x4c255  stelem.ref
0x4c256  ldc.i4.1
0x4c257  newarr   Microsoft.Crm.Data.PropertyBag
0x4c25c  dup
0x4c25d  ldc.i4.0
0x4c25e  ldloc.s  5
0x4c260  stelem.ref
0x4c261  ldc.i4   0x226
0x4c266  ldstr    aThrowifrequire// "ThrowIfRequirementLoopExists"
0x4c26b  ldstr    aDA1SSrcPlatfor_35// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4c270  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4c275  stloc.s  6
0x4c277  ldloc.s  6
0x4c279  brfalse.s loc_4C2C4
0x4c27b  ldloc.s  6
0x4c27d  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x4c282  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x4c287  stloc.s  9
0x4c289  br.s     loc_4C2AB
0x4c28b  ldloca.s 9
0x4c28d  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x4c292  stloc.s  0xB
0x4c294  ldloc.0
0x4c295  ldloc.s  0xB
0x4c297  ldstr    aPatchid// "PatchId"
0x4c29c  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4c2a1  unbox.any [mscorlib]System.Guid
0x4c2a6  callvirt instance void class [System]System.Collections.Generic.Queue`1<valuetype [mscorlib]System.Guid>::Enqueue(var<u1>)
0x4c2ab  ldloca.s 9
0x4c2ad  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x4c2b2  brtrue.s loc_4C28B
0x4c2b4  leave.s  loc_4C2C4
0x4c2b6  ldloca.s 9
0x4c2b8  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x4c2be  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c2c3  endfinally
0x4c2c4  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x4c2c9  stloc.s  7
0x4c2cb  ldloc.s  7
0x4c2cd  ldstr    aPatchid// "PatchId"
0x4c2d2  ldloc.2
0x4c2d3  box      [mscorlib]System.Guid
0x4c2d8  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x4c2dd  ldarg.0
0x4c2de  ldfld    class Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService Microsoft.Crm.ConfigurationDatabase.ClientPatchDetailsService::_configService
0x4c2e3  ldstr    aClientpatchcon// "ClientPatchContainedInfo"
0x4c2e8  ldc.i4.1
0x4c2e9  newarr   [mscorlib]System.String
0x4c2ee  dup
0x4c2ef  ldc.i4.0
0x4c2f0  ldstr    aContainedpatch// "ContainedPatchId"
0x4c2f5  stelem.ref
0x4c2f6  ldc.i4.1
0x4c2f7  newarr   Microsoft.Crm.Data.PropertyBag
0x4c2fc  dup
0x4c2fd  ldc.i4.0
0x4c2fe  ldloc.s  7
0x4c300  stelem.ref
0x4c301  ldc.i4   0x233
0x4c306  ldstr    aThrowifrequire// "ThrowIfRequirementLoopExists"
0x4c30b  ldstr    aDA1SSrcPlatfor_35// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4c310  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4c315  stloc.s  8
0x4c317  ldloc.s  8
0x4c319  brfalse.s loc_4C364
0x4c31b  ldloc.s  8
0x4c31d  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x4c322  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x4c327  stloc.s  9
0x4c329  br.s     loc_4C34B
0x4c32b  ldloca.s 9
0x4c32d  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x4c332  stloc.s  0xC
0x4c334  ldloc.0
0x4c335  ldloc.s  0xC
0x4c337  ldstr    aContainedpatch// "ContainedPatchId"
0x4c33c  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4c341  unbox.any [mscorlib]System.Guid
0x4c346  callvirt instance void class [System]System.Collections.Generic.Queue`1<valuetype [mscorlib]System.Guid>::Enqueue(var<u1>)
0x4c34b  ldloca.s 9
0x4c34d  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x4c352  brtrue.s loc_4C32B
0x4c354  leave.s  loc_4C364
0x4c356  ldloca.s 9
0x4c358  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x4c35e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c363  endfinally
0x4c364  ldc.i4.0
0x4c365  ldloc.0
0x4c366  callvirt instance int32 class [System]System.Collections.Generic.Queue`1<valuetype [mscorlib]System.Guid>::get_Count()
0x4c36b  blt      loc_4C158
0x4c370  ret
```
