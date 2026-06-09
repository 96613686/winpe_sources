# Microsoft.Crm.ServerLocatorService::RetrieveOrganizationsForScaleGroupAndDataCenter

- ea: `0xa440`
- end: `0xa565`
- name: `Microsoft.Crm.ServerLocatorService::RetrieveOrganizationsForScaleGroupAndDataCenter`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xa420`

## callees

- `0x3100`
- `0x8370`
- `0x94f0`
- `0x9620`
- `0xa440`
- `0x43b10`
- `0x43b40`
- `0x44400`
- `0x44510`
- `0x65630`

## string_xrefs

- `0xa476`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xa55a`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xa440  newobj   instance void <>c__DisplayClass111_0::.ctor()
0xa445  stloc.0
0xa446  ldloc.0
0xa447  ldarg.2
0xa448  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass111_0::scaleGroupId
0xa44d  ldloc.0
0xa44e  ldarg.3
0xa44f  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass111_0::datacenterId
0xa454  ldstr    aOrganization// "Organization"
0xa459  stloc.1
0xa45a  ldnull
0xa45b  stloc.2
0xa45c  ldarg.0
0xa45d  ldfld    bool Microsoft.Crm.ServerLocatorService::_isRetrieveConditionCacheEnabled
0xa462  brfalse.s loc_A4E3
0xa464  newobj   instance void Microsoft.Crm.Data.PropertyBagCollection::.ctor()
0xa469  stloc.3
0xa46a  ldarg.0
0xa46b  ldloc.1
0xa46c  ldc.i4   0x95A
0xa471  ldstr    aRetrieveorgani// "RetrieveOrganizationsForScaleGroupAndDa"...
0xa476  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xa47b  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xa480  ldloc.0
0xa481  ldftn    instance bool <>c__DisplayClass111_0::<RetrieveOrganizationsForScaleGroupAndDataCenter>b__0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag> x)
0xa487  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>, bool>::.ctor(object, native int)
0xa48c  call     T0x2B000029
0xa491  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>>::GetEnumerator()
0xa496  stloc.s  4
0xa498  br.s     loc_A4B7
0xa49a  ldloc.s  4
0xa49c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>>::get_Current()
0xa4a1  stloc.s  5
0xa4a3  ldloc.3
0xa4a4  ldloca.s 5
0xa4a6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Key()
0xa4ab  ldloca.s 5
0xa4ad  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0xa4b2  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::Add(var<u1>, !!T0)
0xa4b7  ldloc.s  4
0xa4b9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa4be  brtrue.s loc_A49A
0xa4c0  leave.s  loc_A4CE
0xa4c2  ldloc.s  4
0xa4c4  brfalse.s loc_A4CD
0xa4c6  ldloc.s  4
0xa4c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa4cd  endfinally
0xa4ce  ldarg.0
0xa4cf  ldfld    class Microsoft.Crm.ILocatorCache Microsoft.Crm.ServerLocatorService::_cache
0xa4d4  ldc.i4.6
0xa4d5  ldloc.3
0xa4d6  ldc.i4.0
0xa4d7  newarr   [mscorlib]System.Object
0xa4dc  callvirt instance void Microsoft.Crm.ILocatorCache::AddEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object value, object[] keys)
0xa4e1  ldloc.3
0xa4e2  ret
0xa4e3  ldc.i4.2
0xa4e4  ldarg.0
0xa4e5  call     instance valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.ServerLocatorService::GetSku()
0xa4ea  bne.un.s loc_A54C
0xa4ec  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xa4f1  stloc.s  6
0xa4f3  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xa4f8  stloc.s  6
0xa4fa  ldloc.s  6
0xa4fc  ldstr    aScalegroupid_0// "ScaleGroupId"
0xa501  ldloc.0
0xa502  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass111_0::scaleGroupId
0xa507  box      [mscorlib]System.Guid
0xa50c  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xa511  ldloc.s  6
0xa513  ldstr    aDatacenterid// "DatacenterId"
0xa518  ldloc.0
0xa519  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass111_0::datacenterId
0xa51e  box      [mscorlib]System.Guid
0xa523  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xa528  ldloc.s  6
0xa52a  ldstr    aState// "State"
0xa52f  ldc.i4.5
0xa530  ldc.i4.2
0xa531  box      [mscorlib]System.Int32
0xa536  newobj   instance void Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype Microsoft.Crm.Data.ConditionalOperator op, object value)
0xa53b  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xa540  ldc.i4.1
0xa541  newarr   Microsoft.Crm.Data.PropertyBag
0xa546  dup
0xa547  ldc.i4.0
0xa548  ldloc.s  6
0xa54a  stelem.ref
0xa54b  stloc.2
0xa54c  ldarg.0
0xa54d  ldloc.1
0xa54e  ldarg.1
0xa54f  ldloc.2
0xa550  ldc.i4   0x975
0xa555  ldstr    aRetrieveorgani// "RetrieveOrganizationsForScaleGroupAndDa"...
0xa55a  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xa55f  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xa564  ret
```
