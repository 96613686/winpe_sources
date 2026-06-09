# Microsoft.Crm.ServerLocatorService::GetScaleGroupDeploymentIdPrivate

- ea: `0xbcd0`
- end: `0xbdef`
- name: `Microsoft.Crm.ServerLocatorService::GetScaleGroupDeploymentIdPrivate`
- size: `287`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x70b0`
- `0x7120`
- `0xadc0`
- `0xadd0`

## callees

- `0x8370`
- `0x94f0`
- `0x9620`
- `0xbcd0`
- `0x1af80`
- `0x43b10`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x44670`

## string_xrefs

- `0xbcff`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xbdb6`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xbcd0  ldc.i4.2
0xbcd1  ldarg.0
0xbcd2  call     instance valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.ServerLocatorService::GetSku()
0xbcd7  ceq
0xbcd9  ldstr    aLiveMethodCall// "Live method called out of context"
0xbcde  call     void Microsoft.Crm.CrmException::Assert(bool condition, string message)
0xbce3  ldc.i4.2
0xbce4  stloc.3
0xbce5  ldloca.s 3
0xbce7  constrained. Microsoft.Crm.CrmConfigDatabaseTable
0xbced  callvirt instance string [mscorlib]System.Object::ToString()
0xbcf2  stloc.0
0xbcf3  ldarg.0
0xbcf4  ldloc.0
0xbcf5  ldc.i4   0xD1D
0xbcfa  ldstr    aGetscalegroupd// "GetScaleGroupDeploymentIdPrivate"
0xbcff  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xbd04  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xbd09  dup
0xbd0a  brtrue.s loc_BD12
0xbd0c  pop
0xbd0d  newobj   instance void Microsoft.Crm.Data.PropertyBagCollection::.ctor()
0xbd12  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0xbd17  stloc.s  4
0xbd19  br.s     loc_BD6F
0xbd1b  ldloca.s 4
0xbd1d  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0xbd22  stloc.s  5
0xbd24  ldloca.s 5
0xbd26  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0xbd2b  ldstr    aScalegroupid_0// "ScaleGroupId"
0xbd30  callvirt instance bool Microsoft.Crm.Data.PropertyBag::Contains(string propertyName)
0xbd35  brfalse.s loc_BD6F
0xbd37  ldloca.s 5
0xbd39  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0xbd3e  ldstr    aScalegroupid_0// "ScaleGroupId"
0xbd43  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xbd48  unbox.any [mscorlib]System.Guid
0xbd4d  ldarg.1
0xbd4e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xbd53  brfalse.s loc_BD6F
0xbd55  ldloca.s 5
0xbd57  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0xbd5c  ldstr    aDeploymentid// "DeploymentId"
0xbd61  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xbd66  unbox.any [mscorlib]System.Guid
0xbd6b  stloc.s  6
0xbd6d  leave.s  loc_BDEC
0xbd6f  ldloca.s 4
0xbd71  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0xbd76  brtrue.s loc_BD1B
0xbd78  leave.s  loc_BD88
0xbd7a  ldloca.s 4
0xbd7c  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0xbd82  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbd87  endfinally
0xbd88  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xbd8d  dup
0xbd8e  ldstr    aScalegroupid_0// "ScaleGroupId"
0xbd93  ldarg.1
0xbd94  box      [mscorlib]System.Guid
0xbd99  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xbd9e  stloc.1
0xbd9f  ldarg.0
0xbda0  ldloc.0
0xbda1  ldnull
0xbda2  ldc.i4.1
0xbda3  newarr   Microsoft.Crm.Data.PropertyBag
0xbda8  dup
0xbda9  ldc.i4.0
0xbdaa  ldloc.1
0xbdab  stelem.ref
0xbdac  ldc.i4   0xD28
0xbdb1  ldstr    aGetscalegroupd// "GetScaleGroupDeploymentIdPrivate"
0xbdb6  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xbdbb  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xbdc0  dup
0xbdc1  brtrue.s loc_BDC7
0xbdc3  pop
0xbdc4  ldnull
0xbdc5  br.s     loc_BDD1
0xbdc7  call     instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0xbdcc  call     T0x2B00002A
0xbdd1  stloc.2
0xbdd2  ldloc.2
0xbdd3  brfalse.s loc_BDE6
0xbdd5  ldloc.2
0xbdd6  ldstr    aDeploymentid// "DeploymentId"
0xbddb  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xbde0  unbox.any [mscorlib]System.Guid
0xbde5  ret
0xbde6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xbdeb  ret
0xbdec  ldloc.s  6
0xbdee  ret
```
