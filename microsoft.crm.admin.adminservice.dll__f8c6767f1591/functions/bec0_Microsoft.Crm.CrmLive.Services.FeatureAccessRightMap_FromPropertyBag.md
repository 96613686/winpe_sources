# Microsoft.Crm.CrmLive.Services.FeatureAccessRightMap::FromPropertyBag

- ea: `0xbec0`
- end: `0xbf88`
- name: `Microsoft.Crm.CrmLive.Services.FeatureAccessRightMap::FromPropertyBag`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xc010`
- `0xc060`

## callees

- `0xbde0`
- `0xbe20`
- `0xbe40`
- `0xbe60`
- `0xbec0`

## string_xrefs

- `0xbf1b`: `AccessRight`
- `0xbf34`: `AccessRight`
- `0xbf73`: `AccessRight`

## pseudocode

```c

```

## disassembly

```asm
0xbec0  ldarg.0
0xbec1  ldnull
0xbec2  cgt.un
0xbec4  ldstr    aPropbagIsNull// "propBag is null."
0xbec9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xbece  ldarg.0
0xbecf  ldstr    aId// "Id"
0xbed4  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0xbed9  brtrue.s loc_BEF4
0xbedb  ldc.i4   0x8004B028
0xbee0  ldc.i4.1
0xbee1  newarr   [mscorlib]System.Object
0xbee6  dup
0xbee7  ldc.i4.0
0xbee8  ldstr    aId// "Id"
0xbeed  stelem.ref
0xbeee  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLiveException::.ctor(int32, object[])
0xbef3  throw
0xbef4  ldarg.0
0xbef5  ldstr    aFeatureid// "FeatureId"
0xbefa  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0xbeff  brtrue.s loc_BF1A
0xbf01  ldc.i4   0x8004B028
0xbf06  ldc.i4.1
0xbf07  newarr   [mscorlib]System.Object
0xbf0c  dup
0xbf0d  ldc.i4.0
0xbf0e  ldstr    aFeatureid// "FeatureId"
0xbf13  stelem.ref
0xbf14  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLiveException::.ctor(int32, object[])
0xbf19  throw
0xbf1a  ldarg.0
0xbf1b  ldstr    aAccessright// "AccessRight"
0xbf20  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0xbf25  brtrue.s loc_BF40
0xbf27  ldc.i4   0x8004B028
0xbf2c  ldc.i4.1
0xbf2d  newarr   [mscorlib]System.Object
0xbf32  dup
0xbf33  ldc.i4.0
0xbf34  ldstr    aAccessright// "AccessRight"
0xbf39  stelem.ref
0xbf3a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLiveException::.ctor(int32, object[])
0xbf3f  throw
0xbf40  newobj   instance void Microsoft.Crm.CrmLive.Services.FeatureAccessRightMap::.ctor()
0xbf45  dup
0xbf46  ldarg.0
0xbf47  ldstr    aId// "Id"
0xbf4c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xbf51  unbox.any [mscorlib]System.Guid
0xbf56  callvirt instance void Microsoft.Crm.CrmLive.Services.FeatureAccessRightMap::set_Id(valuetype [mscorlib]System.Guid value)
0xbf5b  dup
0xbf5c  ldarg.0
0xbf5d  ldstr    aFeatureid// "FeatureId"
0xbf62  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xbf67  unbox.any [mscorlib]System.Guid
0xbf6c  callvirt instance void Microsoft.Crm.CrmLive.Services.FeatureAccessRightMap::set_FeatureId(valuetype [mscorlib]System.Guid value)
0xbf71  dup
0xbf72  ldarg.0
0xbf73  ldstr    aAccessright// "AccessRight"
0xbf78  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xbf7d  unbox.any [mscorlib]System.Int32
0xbf82  callvirt instance void Microsoft.Crm.CrmLive.Services.FeatureAccessRightMap::set_AccessRight(int32 value)
0xbf87  ret
```
