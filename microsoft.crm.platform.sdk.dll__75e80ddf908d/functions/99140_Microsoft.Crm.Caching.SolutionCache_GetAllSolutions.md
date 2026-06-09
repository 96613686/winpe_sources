# Microsoft.Crm.Caching.SolutionCache::GetAllSolutions

- ea: `0x99140`
- end: `0x9928a`
- name: `Microsoft.Crm.Caching.SolutionCache::GetAllSolutions`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3210`

## callees

- `0x30c0`
- `0x99140`

## string_xrefs

- `0x991a5`: `index _orgToSolutionIdList for Organization {0} in SolutionCache is created during GetAllSolutions`
- `0x99254`: `index _orgToSolutionIdList for Organization {0} in SolutionCache is removed during LookupEntries exception`

## pseudocode

```c

```

## disassembly

```asm
0x99140  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.ISolution>>::.ctor()
0x99145  stloc.0
0x99146  ldarg.0
0x99147  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, object> Microsoft.Crm.Caching.SolutionCache::_orgIdLockObjects
0x9914c  ldarg.1
0x9914d  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, object> <>c::<>9__8_0
0x99152  dup
0x99153  brtrue.s loc_9916C
0x99155  pop
0x99156  ldsfld   class <>c <>c::<>9
0x9915b  ldftn    instance object <>c::<GetAllSolutions>b__8_0(valuetype [mscorlib]System.Guid guid)
0x99161  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, object>::.ctor(object, native int)
0x99166  dup
0x99167  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, object> <>c::<>9__8_0
0x9916c  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, object>::GetOrAdd(void, var<u1>)
0x99171  stloc.1
0x99172  ldc.i4.0
0x99173  stloc.2
0x99174  ldloc.1
0x99175  ldloca.s 2
0x99177  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x9917c  ldnull
0x9917d  stloc.3
0x9917e  ldarg.0
0x9917f  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>> Microsoft.Crm.Caching.SolutionCache::_orgToSolutionIdList
0x99184  ldarg.1
0x99185  ldloca.s 3
0x99187  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::TryGetValue(var<u1>, !!T0)
0x9918c  pop
0x9918d  ldloc.3
0x9918e  brtrue.s loc_991D9
0x99190  ldarg.1
0x99191  ldc.i4.0
0x99192  ldc.i4.0
0x99193  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x99198  stloc.s  4
0x9919a  ldloc.s  4
0x9919c  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.SolutionHelper::GetAllSolutionIdsForAnOrg(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x991a1  stloc.3
0x991a2  ldarg.1
0x991a3  ldc.i4.s 0x1A
0x991a5  ldstr    aIndexOrgtosolu// "index _orgToSolutionIdList for Organiza"...
0x991aa  ldc.i4.1
0x991ab  newarr   [mscorlib]System.Object
0x991b0  dup
0x991b1  ldc.i4.0
0x991b2  ldarg.1
0x991b3  box      [mscorlib]System.Guid
0x991b8  stelem.ref
0x991b9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x991be  ldarg.0
0x991bf  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>> Microsoft.Crm.Caching.SolutionCache::_orgToSolutionIdList
0x991c4  ldarg.1
0x991c5  ldloc.3
0x991c6  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::set_Item(var<u1>, !!T0)
0x991cb  leave.s  loc_991D9
0x991cd  ldloc.s  4
0x991cf  brfalse.s loc_991D8
0x991d1  ldloc.s  4
0x991d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x991d8  endfinally
0x991d9  ldloc.3
0x991da  brfalse  loc_9927C
0x991df  ldloc.3
0x991e0  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x991e5  ldc.i4.0
0x991e6  ble      loc_9927C
0x991eb  ldarg.0
0x991ec  ldloc.3
0x991ed  ldarg.1
0x991ee  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x991f3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.ISolution>::LookupEntries(var<u1>, void)
0x991f8  stloc.0
0x991f9  leave    loc_99288
0x991fe  stloc.s  5
0x99200  ldloc.s  5
0x99202  ldarg.1
0x99203  ldc.i4.s 0x1A
0x99205  ldstr    aFailedToLookup// "Failed to lookup solutionIds: {0}, with"...
0x9920a  ldc.i4.2
0x9920b  newarr   [mscorlib]System.Object
0x99210  dup
0x99211  ldc.i4.0
0x99212  ldstr    asc_B8554// ","
0x99217  ldloc.3
0x99218  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, string> <>c::<>9__8_1
0x9921d  dup
0x9921e  brtrue.s loc_99237
0x99220  pop
0x99221  ldsfld   class <>c <>c::<>9
0x99226  ldftn    instance string <>c::<GetAllSolutions>b__8_1(valuetype [mscorlib]System.Guid x)
0x9922c  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, string>::.ctor(object, native int)
0x99231  dup
0x99232  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, string> <>c::<>9__8_1
0x99237  call     T0x2B0000D9
0x9923c  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x99241  stelem.ref
0x99242  dup
0x99243  ldc.i4.1
0x99244  ldloc.s  5
0x99246  callvirt instance string [mscorlib]System.Object::ToString()
0x9924b  stelem.ref
0x9924c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x99251  ldarg.1
0x99252  ldc.i4.s 0x1A
0x99254  ldstr    aIndexOrgtosolu_0// "index _orgToSolutionIdList for Organiza"...
0x99259  ldc.i4.1
0x9925a  newarr   [mscorlib]System.Object
0x9925f  dup
0x99260  ldc.i4.0
0x99261  ldarg.1
0x99262  box      [mscorlib]System.Guid
0x99267  stelem.ref
0x99268  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9926d  ldarg.0
0x9926e  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>> Microsoft.Crm.Caching.SolutionCache::_orgToSolutionIdList
0x99273  ldarg.1
0x99274  call     T0x2B0000E2
0x99279  pop
0x9927a  rethrow
0x9927c  leave.s  loc_99288
0x9927e  ldloc.2
0x9927f  brfalse.s loc_99287
0x99281  ldloc.1
0x99282  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x99287  endfinally
0x99288  ldloc.0
0x99289  ret
```
