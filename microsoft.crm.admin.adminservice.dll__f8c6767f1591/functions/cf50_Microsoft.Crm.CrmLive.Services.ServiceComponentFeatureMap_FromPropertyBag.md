# Microsoft.Crm.CrmLive.Services.ServiceComponentFeatureMap::FromPropertyBag

- ea: `0xcf50`
- end: `0xd054`
- name: `Microsoft.Crm.CrmLive.Services.ServiceComponentFeatureMap::FromPropertyBag`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0xd170`

## callees

- `0xce40`
- `0xce80`
- `0xcea0`
- `0xcec0`
- `0xcee0`
- `0xcf50`

## string_xrefs

- `0xcfab`: `ServiceComponentId`
- `0xcfc4`: `ServiceComponentId`
- `0xd029`: `ServiceComponentId`

## pseudocode

```c

```

## disassembly

```asm
0xcf50  ldarg.0
0xcf51  ldnull
0xcf52  cgt.un
0xcf54  ldstr    aPropbagIsNull// "propBag is null."
0xcf59  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xcf5e  ldarg.0
0xcf5f  ldstr    aId// "Id"
0xcf64  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0xcf69  brtrue.s loc_CF84
0xcf6b  ldc.i4   0x8004B028
0xcf70  ldc.i4.1
0xcf71  newarr   [mscorlib]System.Object
0xcf76  dup
0xcf77  ldc.i4.0
0xcf78  ldstr    aId// "Id"
0xcf7d  stelem.ref
0xcf7e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLiveException::.ctor(int32, object[])
0xcf83  throw
0xcf84  ldarg.0
0xcf85  ldstr    aFeatureid// "FeatureId"
0xcf8a  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0xcf8f  brtrue.s loc_CFAA
0xcf91  ldc.i4   0x8004B028
0xcf96  ldc.i4.1
0xcf97  newarr   [mscorlib]System.Object
0xcf9c  dup
0xcf9d  ldc.i4.0
0xcf9e  ldstr    aFeatureid// "FeatureId"
0xcfa3  stelem.ref
0xcfa4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLiveException::.ctor(int32, object[])
0xcfa9  throw
0xcfaa  ldarg.0
0xcfab  ldstr    aServicecompone// "ServiceComponentId"
0xcfb0  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0xcfb5  brtrue.s loc_CFD0
0xcfb7  ldc.i4   0x8004B028
0xcfbc  ldc.i4.1
0xcfbd  newarr   [mscorlib]System.Object
0xcfc2  dup
0xcfc3  ldc.i4.0
0xcfc4  ldstr    aServicecompone// "ServiceComponentId"
0xcfc9  stelem.ref
0xcfca  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLiveException::.ctor(int32, object[])
0xcfcf  throw
0xcfd0  ldarg.0
0xcfd1  ldstr    aEnabled// "Enabled"
0xcfd6  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0xcfdb  brtrue.s loc_CFF6
0xcfdd  ldc.i4   0x8004B028
0xcfe2  ldc.i4.1
0xcfe3  newarr   [mscorlib]System.Object
0xcfe8  dup
0xcfe9  ldc.i4.0
0xcfea  ldstr    aEnabled// "Enabled"
0xcfef  stelem.ref
0xcff0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLiveException::.ctor(int32, object[])
0xcff5  throw
0xcff6  newobj   instance void Microsoft.Crm.CrmLive.Services.ServiceComponentFeatureMap::.ctor()
0xcffb  dup
0xcffc  ldarg.0
0xcffd  ldstr    aId// "Id"
0xd002  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xd007  unbox.any [mscorlib]System.Guid
0xd00c  callvirt instance void Microsoft.Crm.CrmLive.Services.ServiceComponentFeatureMap::set_Id(valuetype [mscorlib]System.Guid value)
0xd011  dup
0xd012  ldarg.0
0xd013  ldstr    aFeatureid// "FeatureId"
0xd018  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xd01d  unbox.any [mscorlib]System.Guid
0xd022  callvirt instance void Microsoft.Crm.CrmLive.Services.ServiceComponentFeatureMap::set_FeatureId(valuetype [mscorlib]System.Guid value)
0xd027  dup
0xd028  ldarg.0
0xd029  ldstr    aServicecompone// "ServiceComponentId"
0xd02e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xd033  castclass [mscorlib]System.String
0xd038  callvirt instance void Microsoft.Crm.CrmLive.Services.ServiceComponentFeatureMap::set_ServiceComponentId(string value)
0xd03d  dup
0xd03e  ldarg.0
0xd03f  ldstr    aEnabled// "Enabled"
0xd044  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xd049  unbox.any [mscorlib]System.Boolean
0xd04e  callvirt instance void Microsoft.Crm.CrmLive.Services.ServiceComponentFeatureMap::set_Enabled(bool value)
0xd053  ret
```
