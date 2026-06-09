# Microsoft.Crm.ServerLocatorService::GetLastAccessTime

- ea: `0x8b10`
- end: `0x8bf7`
- name: `Microsoft.Crm.ServerLocatorService::GetLastAccessTime`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x3090`
- `0x8b10`
- `0x94f0`
- `0x44400`
- `0x444f0`
- `0x44510`

## string_xrefs

- `0x8b60`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x8b46`: `LastAccessTime`
- `0x8b85`: `LastAccessTime`
- `0x8b9b`: `LastAccessTime`
- `0x8b5b`: `GetLastAccessTime`

## pseudocode

```c

```

## disassembly

```asm
0x8b10  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x8b15  stloc.0
0x8b16  ldloc.0
0x8b17  ldstr    aOrganizationid_1// "OrganizationId"
0x8b1c  ldarg.1
0x8b1d  box      [mscorlib]System.Guid
0x8b22  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8b27  ldloc.0
0x8b28  ldstr    aCrmuserid// "CrmUserId"
0x8b2d  ldarg.2
0x8b2e  box      [mscorlib]System.Guid
0x8b33  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8b38  ldarg.0
0x8b39  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x8b3e  ldc.i4.1
0x8b3f  newarr   [mscorlib]System.String
0x8b44  dup
0x8b45  ldc.i4.0
0x8b46  ldstr    aLastaccesstime// "LastAccessTime"
0x8b4b  stelem.ref
0x8b4c  ldc.i4.1
0x8b4d  newarr   Microsoft.Crm.Data.PropertyBag
0x8b52  dup
0x8b53  ldc.i4.0
0x8b54  ldloc.0
0x8b55  stelem.ref
0x8b56  ldc.i4   0x56B
0x8b5b  ldstr    aGetlastaccesst// "GetLastAccessTime"
0x8b60  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x8b65  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x8b6a  stloc.1
0x8b6b  ldloc.1
0x8b6c  brfalse.s loc_8BC7
0x8b6e  ldloc.1
0x8b6f  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x8b74  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x8b79  stloc.2
0x8b7a  br.s     loc_8BAE
0x8b7c  ldloca.s 2
0x8b7e  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x8b83  stloc.3
0x8b84  ldloc.3
0x8b85  ldstr    aLastaccesstime// "LastAccessTime"
0x8b8a  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x8b8f  brtrue.s loc_8B9A
0x8b91  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x8b96  stloc.s  4
0x8b98  leave.s  loc_8BF4
0x8b9a  ldloc.3
0x8b9b  ldstr    aLastaccesstime// "LastAccessTime"
0x8ba0  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x8ba5  unbox.any [mscorlib]System.DateTime
0x8baa  stloc.s  4
0x8bac  leave.s  loc_8BF4
0x8bae  ldloca.s 2
0x8bb0  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x8bb5  brtrue.s loc_8B7C
0x8bb7  leave.s  loc_8BC7
0x8bb9  ldloca.s 2
0x8bbb  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x8bc1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8bc6  endfinally
0x8bc7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8bcc  ldstr    aCrmUserWithId0// "Crm User with id {0} in org {1} was not"...
0x8bd1  ldc.i4.2
0x8bd2  newarr   [mscorlib]System.Object
0x8bd7  dup
0x8bd8  ldc.i4.0
0x8bd9  ldarg.2
0x8bda  box      [mscorlib]System.Guid
0x8bdf  stelem.ref
0x8be0  dup
0x8be1  ldc.i4.1
0x8be2  ldarg.1
0x8be3  box      [mscorlib]System.Guid
0x8be8  stelem.ref
0x8be9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8bee  newobj   instance void Microsoft.Crm.CrmConfigObjectNotFoundException::.ctor(string message)
0x8bf3  throw
0x8bf4  ldloc.s  4
0x8bf6  ret
```
