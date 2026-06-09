# Microsoft.Crm.ServerLocatorService::GetEnabledOrganizationsIds

- ea: `0x6de0`
- end: `0x6ee6`
- name: `Microsoft.Crm.ServerLocatorService::GetEnabledOrganizationsIds`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x3100`
- `0x3120`
- `0x6de0`
- `0x94f0`
- `0x9620`
- `0x43b10`
- `0x44400`
- `0x44510`

## string_xrefs

- `0x6e17`: `GetEnabledOrganizationsIds`
- `0x6ed6`: `GetEnabledOrganizationsIds`
- `0x6e1c`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x6edb`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x6de0  ldstr    aOrganization// "Organization"
0x6de5  stloc.0
0x6de6  ldarg.0
0x6de7  ldfld    bool Microsoft.Crm.ServerLocatorService::_isRetrieveConditionCacheEnabled
0x6dec  brfalse  loc_6EA0
0x6df1  ldarg.0
0x6df2  ldfld    class Microsoft.Crm.ILocatorCache Microsoft.Crm.ServerLocatorService::_cache
0x6df7  ldc.i4.s 0x16
0x6df9  ldc.i4.0
0x6dfa  newarr   [mscorlib]System.Object
0x6dff  callvirt instance object Microsoft.Crm.ILocatorCache::LookupEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object[] keys)
0x6e04  isinst   Microsoft.Crm.Data.PropertyBagCollection
0x6e09  stloc.2
0x6e0a  ldloc.2
0x6e0b  brtrue   loc_6E9E
0x6e10  ldarg.0
0x6e11  ldloc.0
0x6e12  ldc.i4   0x10C
0x6e17  ldstr    aGetenabledorga// "GetEnabledOrganizationsIds"
0x6e1c  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x6e21  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x6e26  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>, bool> <>c::<>9__22_0
0x6e2b  dup
0x6e2c  brtrue.s loc_6E45
0x6e2e  pop
0x6e2f  ldsfld   class <>c <>c::<>9
0x6e34  ldftn    instance bool <>c::<GetEnabledOrganizationsIds>b__22_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag> x)
0x6e3a  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>, bool>::.ctor(object, native int)
0x6e3f  dup
0x6e40  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>, bool> <>c::<>9__22_0
0x6e45  call     T0x2B000029
0x6e4a  newobj   instance void Microsoft.Crm.Data.PropertyBagCollection::.ctor()
0x6e4f  stloc.2
0x6e50  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>>::GetEnumerator()
0x6e55  stloc.3
0x6e56  br.s     loc_6E74
0x6e58  ldloc.3
0x6e59  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>>::get_Current()
0x6e5e  stloc.s  4
0x6e60  ldloc.2
0x6e61  ldloca.s 4
0x6e63  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Key()
0x6e68  ldloca.s 4
0x6e6a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0x6e6f  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::Add(var<u1>, !!T0)
0x6e74  ldloc.3
0x6e75  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6e7a  brtrue.s loc_6E58
0x6e7c  leave.s  loc_6E88
0x6e7e  ldloc.3
0x6e7f  brfalse.s loc_6E87
0x6e81  ldloc.3
0x6e82  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6e87  endfinally
0x6e88  ldarg.0
0x6e89  ldfld    class Microsoft.Crm.ILocatorCache Microsoft.Crm.ServerLocatorService::_cache
0x6e8e  ldc.i4.s 0x16
0x6e90  ldloc.2
0x6e91  ldc.i4.0
0x6e92  newarr   [mscorlib]System.Object
0x6e97  callvirt instance void Microsoft.Crm.ILocatorCache::AddEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object value, object[] keys)
0x6e9c  ldloc.2
0x6e9d  ret
0x6e9e  ldloc.2
0x6e9f  ret
0x6ea0  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x6ea5  stloc.1
0x6ea6  ldloc.1
0x6ea7  ldstr    aState// "State"
0x6eac  ldc.i4.1
0x6ead  box      [mscorlib]System.Int32
0x6eb2  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x6eb7  ldarg.0
0x6eb8  ldloc.0
0x6eb9  ldc.i4.1
0x6eba  newarr   [mscorlib]System.String
0x6ebf  dup
0x6ec0  ldc.i4.0
0x6ec1  ldstr    aId// "Id"
0x6ec6  stelem.ref
0x6ec7  ldc.i4.1
0x6ec8  newarr   Microsoft.Crm.Data.PropertyBag
0x6ecd  dup
0x6ece  ldc.i4.0
0x6ecf  ldloc.1
0x6ed0  stelem.ref
0x6ed1  ldc.i4   0x11F
0x6ed6  ldstr    aGetenabledorga// "GetEnabledOrganizationsIds"
0x6edb  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x6ee0  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x6ee5  ret
```
